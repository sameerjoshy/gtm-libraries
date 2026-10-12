---
name: gtm-data-architecture
version: 1.0.0
status: draft-for-review
description: "Use to design the data layer behind revenue operations for a team that is not made of data engineers. Covers warehouse-centred architecture, transformation layers, the three queries every RevOps lead should read, reverse activation of computed scores, identity resolution, a unified customer health score, staged roadmap, and data readiness for AI agents. Use when the CRM cannot answer cross-system questions, when metrics differ between teams, or before any AI agent is pointed at customer data. Not for CRM data quality rules (see revops-data-governance) or vendor selection (see revops-tech-stack)."
sources:
  - "GTM data architecture (MIT, Rutger Katz / Neon Triforce): the warehouse-centred reference architecture, the three operator queries, ELT over ETL, versioned transformations, reverse activation with reconciliation, identity resolution, the unified health score, the stage patterns, the phased roadmap, the anti-patterns, and when not to go warehouse-native"
  - "Removed as unverified: the cost and speed claims attributed to a data institute and a data vendor, the 50% enterprise migration figure, the composable vendor growth rate, the 'Hightouch synced 7.3 trillion records' figure, the CAC reduction and conversion uplift ranges, and the identity-matching accuracy anecdote"
  - "Corrected: the source cited a directive number for the EU Data Act that does not match the regulation (Regulation (EU) 2023/2854 is the Data Act). The source cited a GDPR notification window of one month for enrichment, which is kept as the statutory default for counsel to confirm. Deletion timing is also for counsel"
  - "Adapted for GTM-360: the stage size bands, the freshness targets (under two hours for activation, under one percent reconciliation variance), and the roadmap durations are author defaults to calibrate"
---

# GTM data architecture

## Purpose

This skill designs the data foundation for a revenue team. It does not build pipelines, which is engineering work, but it sets the shape the pipelines must take, so the numbers leadership sees come from one place and can be traced to their definitions.

The core rule: keep one authoritative copy of customer data, define each metric once in code, and let every tool read from that copy. Where that is not yet possible, say so, and name the copy that is canonical for now.

## When to use

- The CRM cannot answer a question that spans product usage, billing, and support.
- Two teams report different numbers for the same metric.
- A forecast, health score, or routing rule depends on data from several systems.
- Someone proposes a data platform, a customer data platform, or reverse ETL.
- AI agents are about to be pointed at customer data.

Route elsewhere when:

- The question is CRM field rules, duplicate handling, or data stewardship. Use `revops-data-governance`.
- The question is which vendor to choose. Use `revops-tech-stack`.
- The question is the commercial strategy the data should serve. Use `revops-strategy`.

## Inputs

- The list of systems that hold customer or revenue data: CRM, product analytics, billing, support, and conversation recordings.
- The reports leadership uses, and the owner of each metric.
- Current data freshness, and how often each system syncs.
- Whether there is a data or analytics engineer, and their available hours.
- Regulatory constraints on where data may be stored and how it may be used.
- The AI use cases being considered, if any.

## Procedure

### Step 1: Choose the architecture pattern

Keep one authoritative copy, the warehouse, and let tools read from it or receive computed values from it. The alternative, where each tool holds its own copy, creates a stale copy per tool, a sync per pair, and definitions that drift.

```
SOURCES (CRM, product, billing, support)
   |  ELT: load raw data as it arrives (scheduled ingestion tool)
   v
WAREHOUSE (raw and staging layers)
   |  Transformation: versioned, tested SQL models (dbt or similar)
   v
MARTS (leads, deals, customers, health): one definition per metric
   |                         |
   |  BI tools read live     |  Reverse activation pushes scores back
   v                         v
DASHBOARDS                  CRM, messaging, customer success tools
```

In this pattern the warehouse is the hub. Tools do not keep their own copies of truth. They read live for dashboards or receive computed values for action.

**Why it has won.** Three forces drive it. Cost and sync delay fall when tools stop copying records. AI agents need one complete, current view, or they reason from stale fragments. And definitions updated in one place reach every downstream tool at once, instead of being changed five times in five systems.

### Step 2: Decide whether the team should go warehouse-native at all

Stay CRM-native when:
- The team is small, roughly under twenty people, and the CRM's automation is enough.
- The entire GTM runs in one CRM, with no separate product, billing, or support data to join.
- Data residency rules keep data on-premises, and no one can run the infrastructure.

Warehouse-native pays back when the team needs to join several sources, run the same metric in several tools, or activate computed scores. As a rough boundary to test: below about twenty seats or about $1M ARR, the cost often outweighs the benefit. Above about one hundred seats or several million ARR, staying CRM-native is usually a deliberate slowdown. Test these boundaries against the client's own costs.

### Step 3: Learn the three queries

A RevOps lead does not need to be an engineer. They do need to read SQL and write a few queries from memory. These three cover most pipeline questions.

**Query 1: coverage by segment and stage.** Shows whether each segment has enough pipeline, and where deals bunch up.

```sql
SELECT segment, stage, COUNT(*) AS deal_count, SUM(arr_value) AS total_arr
FROM marts_deals
WHERE close_date >= DATE_TRUNC('month', CURRENT_DATE)
GROUP BY segment, stage
ORDER BY segment, stage;
```

If one stage holds five deals and the next holds one, the conversion between them is the first thing to examine.

**Query 2: activity coverage per deal, keeping deals with no activity.** Uses a LEFT JOIN so that deals without activity still appear. An INNER JOIN silently drops them, and the pipeline looks healthier than it is.

```sql
SELECT
  d.created_month,
  d.stage,
  COUNT(DISTINCT d.id) AS deals,
  COUNT(DISTINCT CASE WHEN a.id IS NOT NULL THEN d.id END) AS deals_with_activity
FROM marts_deals d
LEFT JOIN marts_activities a
  ON d.id = a.deal_id
 AND a.activity_date >= d.stage_entry_date
 AND a.activity_date < DATEADD(MONTH, 1, d.stage_entry_date)
GROUP BY d.created_month, d.stage;
```

**Query 3: monthly activity and outcomes per rep, with a rolling average.** Aggregate first, then apply the window function, so each rep's row count and win count are clear.

```sql
WITH rep_month AS (
  SELECT
    d.rep_id,
    DATE_TRUNC('month', a.activity_date) AS activity_month,
    COUNT(a.id) AS activities,
    COUNT(DISTINCT CASE WHEN d.stage = 'Won' THEN d.id END) AS won_deals
  FROM marts_activities a
  LEFT JOIN marts_deals d ON a.deal_id = d.id
  GROUP BY d.rep_id, DATE_TRUNC('month', a.activity_date)
)
SELECT
  rep_id,
  activity_month,
  activities,
  won_deals,
  AVG(won_deals) OVER (
    PARTITION BY rep_id ORDER BY activity_month
    ROWS BETWEEN 2 PRECEDING AND CURRENT ROW
  ) AS rolling_3_month_avg_wins
FROM rep_month
ORDER BY rep_id, activity_month;
```

Note the definition of a won deal here. If the CRM's stage name differs, change it in one place, which is the point of the next step.

### Step 4: Put every metric in versioned transformations

Each of the queries above should live as a versioned, tested model, not as an ad hoc query in a dashboard. A version history answers the question "how did you calculate this?" with a link to the code. When a definition changes, every downstream report sees the change at once.

Use ELT by default: load raw data into the warehouse, transform inside it. The raw data is kept, so a changed definition can be applied to history without re-extracting from source systems.

Build three core marts first:
- **Leads:** MQL and SQL status, with stage history.
- **Deals:** pipeline, time in stage, and win and loss reasons.
- **Customers:** ARR, seat count, and health.

Start with staging (cleaned raw data), then the marts, then tests and documentation. Tests should enforce the data gates that matter: a stage exit requirement, a required source on every score, and an auditable stage history.

Standard tooling for the transformation layer is dbt Cloud for most teams and self-managed dbt Core for highly technical organisations. The choice is a vendor decision, see `revops-tech-stack`.

### Step 5: Activate computed values back into the tools

The warehouse may hold excellent data while the CRM is stale. Reverse activation pushes computed values, such as scores, routing decisions, and health flags, from the warehouse into the CRM, messaging, and alerting tools.

Each activation has five parts: a warehouse query as the source, an optional transformation, a destination, a sync schedule (hourly or event-driven), and a reconciliation process. The reconciliation is the step teams skip. Once a month, check that the numbers in the destination match the warehouse. If they diverge, the pipeline is broken, and the broken pipeline must be found before anyone trusts the score.

Targets to calibrate: activation from data event to downstream tool under two hours, and reconciliation variance under one percent.

Do not start activation with the most complex use case. Start with one: lead scoring to the CRM, or forecast accuracy. Extend to routing, expansion signals, and health only after the first one reconciles.

### Step 6: Resolve identity across systems

Identity resolution matches signals from different systems to one profile: an email signup, a professional profile, a CRM account, a support ticket, and a billing record may all belong to one buyer or one customer.

- **Deterministic matching** joins on exact keys, such as email, phone, or account identifier. It is reliable and limited.
- **Probabilistic matching** scores likely matches from fuzzy fields such as name, company, and title. It catches more and needs tuning and review.

Start with deterministic matching in the warehouse. Add probabilistic matching only for the gaps it leaves, and buy it from a vendor before building it, unless the matching rules are specific to the business.

Consent and legal basis matter here. Where contacts are enriched from external sources, a notification duty may apply, and a per-contact record of the source is needed. Keep that source trail in a dedicated model. The notification timing and the basis for enrichment are for counsel to confirm.

### Step 7: Build one health score from several sources

A unified customer health score combines signals from the CRM, product usage, support, billing, and call content into one number. Each component is a model in the warehouse, and the combined score is computed in the warehouse and then activated back into the CRM.

```
HEALTH SCORE = weighted combination of:
  CRM signals:          deal progression, multi-threading, champion status
  Product signals:      feature adoption, login frequency, seats in use
  Support signals:      ticket volume, sentiment, time to resolution
  Billing signals:      payment timeliness, renewal timing, expansion readiness
  Conversation signals: sentiment, risk mentions, value statements
```

Weights are defaults. Set them by testing against the client's own churn and expansion history, not by intuition. Publish the components alongside the score, so a customer success manager can see why an account went red.

### Step 8: Follow the roadmap

A six to twelve month path, adjusted to the team's size and data:

**Phase 1, foundations (weeks 1 to 4).** Name the sources. Choose the warehouse and the ingestion tool. Load CRM and product events on a nightly schedule. Milestone: raw data is flowing, and a SQL query can join CRM and product data.

**Phase 2, transformation governance (weeks 5 to 12).** Set up versioned transformations. Build the three core marts. Write each metric definition as code. Add tests and documentation. Milestone: leadership can trace any number to its definition.

**Phase 3, activation (weeks 13 to 24).** Activate one score into the CRM. Set the monthly reconciliation and its alert threshold. Extend activation to routing, expansion, or health as each one reconciles. Milestone: the warehouse is the source of truth, and drift is detected.

**Phase 4, AI readiness and governance (weeks 25 to 52).** Complete identity resolution. Build the unified health score. Add data contracts, audit trails, and a documented process for handling deletion requests. Only then consider agent integration. Milestone: decisions can be traced, and governance runs without manual effort where possible.

Staffing guide: a small team can run the early phases with part of one analyst's time. Mid-sized teams need a data engineer and an analytics engineer. Enterprise-scale agent programmes need a governance lead on top. Counts are planning assumptions.

## Anti-patterns

**Transformation sprawl.** Models multiply, nobody knows what feeds which dashboard, and breakage goes unnoticed for weeks. Fix: every model has a named owner and at least one known consumer. Retire orphaned models on a schedule.

**Real-time obsession.** Refresh intervals are shortened without evidence that the delay costs deals. A correct score that is an hour old is usually enough. Fix: start with nightly or six-hourly refreshes, and speed up only when a latency gap is shown to lose revenue.

**Identity bikeshedding.** Months go into a custom matching algorithm that a vendor could have delivered faster. Fix: buy first, build only for rules the vendor cannot handle.

**Data quality later.** The warehouse goes live and bad data is accepted, with the promise to fix it later. Fix: define the gates early, as stage exit tests and required fields that must be present before a lead can route.

## Regulatory checks for counsel

These are points for counsel to confirm, not legal advice.

- **Enrichment notices.** Where external data is added to contact records, confirm the notification duty and its timing. Build a model that records the source of each enrichment, and automate the notice if counsel requires it.
- **Deletion requests.** Confirm the timeframe that applies, and design the pipeline so a deletion reaches the warehouse, every activation destination, and downstream systems. Automate it. Manual deletion across many systems is slow and error-prone.
- **Automated decisions.** Where a routing or scoring decision triggers automated contact, confirm the transparency duty and whether human review is needed for material decisions. Keep the logic explainable and the audit trail intact.
- **Data portability.** The EU Data Act (Regulation (EU) 2023/2854) gives business customers rights to access and port their data in some cases. Keep the warehouse schema export-friendly.
- **Residency.** Where data must stay in one jurisdiction, confirm the warehouse region and vendor sub-processors before setup, not after.

## How to use this skill

**"We are choosing a data platform for GTM."** Pick the pattern from the stage (Step 1 and Step 2). Then see `revops-tech-stack` for the vendor decision.

**"Our data quality is terrible."** Start with Phase 2. Poor data is usually a governance problem before it is a platform problem. Move the definitions into versioned models, and add gates. Use `revops-data-governance` for the CRM rules.

**"We want AI agents but do not trust the CRM."** Complete Phases 1 to 4 first, with emphasis on identity and the health score. Check the readiness prerequisites in `revops-tech-stack`.

**"The CRM is too complex to manage."** The team has reached the ceiling of CRM-native automation. Move to ELT plus versioned transformations, starting with the three core marts.

**"How do we know it is working?"** Track three things: time from data event to activation, monthly reconciliation variance, and the share of leadership metrics traced to a versioned model. Target the defaults in Step 5, and calibrate them.

**"Do we need a reverse activation tool?"** Only if computed values must reach the CRM or another operational tool. If dashboards are the only need, use BI tools and skip activation.

## Output

- The architecture pattern and its stage fit, with the reason for choosing it.
- The source inventory and the three core marts, with owners.
- The versioned transformation plan and the tests that enforce the data gates.
- The first activation use case, with its reconciliation process and thresholds.
- The identity approach: deterministic first, probabilistic only where needed.
- The health score components, with weights to be calibrated.
- The phased roadmap, and the list of counsel checks.

## Diagnostic questions

1. Which two teams report different numbers for the same metric, and where is each definition written?
2. If a metric changed tomorrow, how many places would need updating?
3. Does the monthly reconciliation exist, and when did it last find a difference?
4. Can a deal with no activity be counted in the pipeline query, or is it silently dropped?
5. Before an agent reads customer data, can its output be traced back to the source record?

## Quality bar

Each core metric is defined once, in versioned code, and every report traces back to it. Activation reconciles monthly. Identity is resolved deterministically before anything else. Counsel has signed off the enrichment, deletion, and automated decision points. Watch for metrics defined in dashboard filters, activation with no reconciliation, real-time refreshes with no latency case, and agents pointed at data nobody has validated.

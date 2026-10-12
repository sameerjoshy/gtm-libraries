---
name: revops-strategy
version: 1.0.0
status: draft-for-review
description: Use when designing or repairing a B2B revenue engine's pipeline architecture. Covers stage contracts, separating new and expansion motions, a three-tier KPI set that links activity to revenue, data hygiene as a discipline, the ICP-to-messaging chain, the operating model between governance, enablement, and value loops, and tech stack decisions. Also use to push back on vanity metrics and to decide whether a new tool is justified. Not for finding the binding constraint (see revops-diagnostic) or building the ICP itself (see icp-builder).
sources:
  - "RevOps strategy and pipeline architecture (MIT, Rutger Katz / Neon Triforce): bow tie model, stage contract template, separate motions, velocity over volume, three-tier KPI architecture, the iron rule for activity metrics, data hygiene system, ICP-to-messaging chain, vanity metric reframes, stack evaluation lenses, consolidation bias, stack evolution"
  - "Removed as unverified: median and top-quartile CAC payback, LTV:CAC, NRR, and win-rate benchmarks; coverage-to-quota percentages; AI forecast variance and churn reduction figures; reverse ETL vendor counts; tool-count and savings figures; the 'compounding flywheel' efficiency range; the 'winner-takes-all' claim. Benchmarks are replaced with the instruction to calibrate against the client's own history"
  - "Corrected: the source's section on AI-era pipeline architecture described the coverage formula as 1 divided by win rate. That is correct only if deals are created at the same rate they are won and the target is set in the same period. The formula is kept, with that condition stated"
  - "Adapted for GTM-360: stage contract fields, the SLA and red-flag structure, and the vanity-metric scripts are author defaults for the client to adopt or replace"
---

# RevOps strategy and pipeline architecture

## Purpose

Revenue is a production line. Marketing, sales, and customer success are stations on it. A bottleneck at one station limits the output of all of them, and optimising a station while ignoring the handoff to the next one is waste.

This skill sets out how to structure the pipeline, the metrics, the data, and the tooling so that the line can be measured and improved. It answers "how should this engine be built?" For the question "what is limiting it right now?", use `revops-diagnostic` first.

## Operating principles

1. **Measure what creates signal, not noise.** Every metric needs a causal chain to revenue: metric, then behaviour change, then revenue impact. If the chain cannot be drawn, the metric is vanity.
2. **Process before technology.** Automating a broken process makes it break faster. The sequence is define, document, operationalise, then automate.
3. **Data quality is a discipline.** Prevent bad data at entry, detect it early, and correct it before it compounds.
4. **Align incentives, not dashboards.** Shared dashboards without shared definitions and accountability are theatre. Marketing is judged on pipeline quality, sales on customer outcomes, and customer success on expansion and retention.
5. **Separate motions.** New and expansion business, enterprise and SMB, and inbound and outbound each have their own stages, velocities, and economics. Blending them produces averages that describe nobody.

## Pipeline architecture

The bow tie model extends the funnel past the close. The left side is acquisition, the knot is the conversion point, and the right side is onboarding, adoption, expansion, and advocacy.

```
LEFT (acquisition):   Awareness > Education > Evaluation > Decision > Close
RIGHT (retention):    Onboarding > Adoption > Expansion > Advocacy
```

The model matters because post-sale revenue gets the same rigour as pre-sale pipeline. Where the business earns most of its growth from existing accounts, the right side is where most of the money is. Measure it as a funnel with its own stages.

### Stage contract

Every stage needs a contract with the next one. Define:

- **Entry criteria:** observable conditions to enter. Not "the rep thinks it is ready".
- **Exit criteria:** what must be true to advance.
- **Required data:** fields that must be populated at this stage.
- **Owner:** the accountable team or role.
- **SLA:** maximum time in stage, with the escalation trigger.
- **Red flags:** signals that a record is stuck or degrading.
- **Handoff:** how the record passes to the next owner.

Enforce required fields at stage transitions, not at record creation. Asking for ten fields at creation produces junk data and rep resistance.

### Velocity over volume

Volume says how much is in the system. Velocity says how fast it moves. Time in stage is often more diagnostic than conversion rate. A smaller pipeline moving quickly is usually healthier than a larger one that stalls. Track time in stage per stage, per segment, per motion.

## KPI architecture

Three tiers. This prevents the two-hundred-metric dashboard and gives every problem a clear escalation path.

**Tier 1: board-level.** Answers "is the engine healthy?" Reviewed monthly or quarterly.
- Revenue growth rate and net new ARR.
- Net revenue retention and gross revenue retention, reported separately.
- CAC payback, by segment.
- Unit economics on a lifetime basis, using a method that holds when retention is high (see below).

**Tier 2: management-level.** Answers "where is the problem?" Reviewed weekly.
- Conversion rates between each stage.
- Average deal velocity, creation to close.
- Pipeline coverage against the target.
- Win rate by segment, source, and rep.
- Sales cycle length by deal size.
- Time to first value for new customers.
- Churn rate and its leading indicators.

**Tier 3: activity and leading indicators.** Predicts Tier 2 movement. Reviewed daily or weekly.
- Qualified meetings booked, by source.
- Proposals sent, with the stage they reached.
- Onboarding milestones completed.
- Product adoption on the activation milestone.
- Engagement and health signals.

**The iron rule.** Every Tier 3 metric needs a stated path to a Tier 1 metric: activity to Tier 2 outcome to revenue. If the chain cannot be stated in two sentences, delete the metric.

### Calibrating the numbers

Do not adopt external benchmarks as targets. Methods differ, and the segment mix differs more. Set the target from the client's own trailing history, then test whether it predicts outcomes.

Two formulas to get right:

- **Coverage.** Coverage needed to hit target is roughly 1 divided by win rate, when deals are created and won in the same period at the same rate. A 25% win rate needs about 4x. If deal creation is seasonal or lagged, use a trailing window instead.
- **Lifetime value.** The common shortcut, ARPA times gross margin divided by one minus net retention, breaks when net retention is at or above 100%, because the denominator goes to zero or negative. Use a discounted model with a horizon cap for high-retention customers, and state the horizon.

## Vanity metric reframes

When a stakeholder fixates on a metric that does not connect to revenue, respond in this order: name the real question, then ask for the conversion that sits underneath.

- **"We need more MQLs."** Ask for MQL-to-SQL conversion. Doubling MQLs at the current conversion doubles SDR load, not necessarily revenue. First find out why most current MQLs do not convert: scoring, handoff speed, or content attracting the wrong audience. Each has a different fix.
- **"We hit the MQL target but pipeline is flat."** The MQL definition has drifted. Pull the recent non-converting MQLs and look for shared content, titles, or company profiles. That shows where scoring leaks.
- **"We need more leads."** Count the existing leads untouched for more than 90 days. Ask why they are not being worked, and what conversion the worked leads produce. More leads at the same quality on a leaking process adds cost without output.
- **"We need a new tool."** Audit utilisation of the current stack. Adoption below the level the team needs is a process or enablement issue, and a new tool inherits it. Add tools only after the current stack is exhausted for the use case.
- **"Our open rates are dropping."** Open rates are unreliable since mailbox privacy features changed what counts as an open. Track reply rate, meetings booked per sequence, and qualified conversations instead.

## Stakeholder response pattern

For a difficult internal conversation, run this sequence:

1. **Identify the real problem.** "We need a new CRM" often means the data is broken and the tool is being blamed. "Marketing is not generating pipeline" often means there is no shared definition of a qualified lead.
2. **Validate.** Acknowledge the frustration without agreeing with the diagnosis.
3. **Reframe to the system.** Connect the pain to the chain it sits in. "We cannot trace a lead from first touch to closed-won, so we cannot tell what works."
4. **Propose a diagnostic before a fix.** Name the data to pull: conversion by source, time in stage by segment, and the last thirty days of handoffs.
5. **Recommend with the arithmetic.** Show what changes if one conversion improves by a stated amount, and what it costs.

## Data hygiene

Data quality compounds in both directions. Good data enriches downstream work. Bad data corrupts reports, triggers wrong automations, and erodes trust in the system.

**Prevention.** Enforce required fields at stage transitions. Use constrained picklists for anything that will be filtered or reported on. Standardise naming for campaigns, sources, and stages, and write them down. Gate automations behind data checks, so a workflow does not fire on empty critical fields.

**Detection.** Run a weekly audit for duplicates, missing required fields, stale records (no activity for 90 days by default), and impossible values such as close dates in the past on open deals. Track a completeness score per record on critical fields and report it like pipeline. Watch the lifecycle distribution: if most contacts sit in the earliest stage and few reach the qualified stage, something upstream is broken.

**Correction.** Triage by revenue: clean active pipeline first, then active customers, then history. Automate formatting. Keep human review for merges and complex deduplication. Log every bulk change, because someone will ask why hundreds of records changed overnight.

## Upstream chain: ICP, positioning, messaging

Pipeline architecture serves an ICP. Before designing stages or KPIs, confirm the ICP is grounded in evidence, not a guess.

| Stage | Input | Output |
|---|---|---|
| ICP | Interviews, win and loss data | Who the customer is and what they struggle with |
| Positioning | ICP and competitive context | Where the company sits in the buyer's mind |
| Messaging framework | Positioning and use cases | What to say, in a reusable form |
| Copy | Messaging framework | Channel output |

The diagnostic question: can every seller state, in one sentence, who the ideal customer is and why they should choose the company? If not, the ICP and positioning work comes first.

**Use case messaging canvas.** For each use case, list the current way (the problem, three specific pains from interviews, the limits of the current approach, and what customers do today) and the new way (the capability that reverses each limit, the feature that powers it, the benefit that resolves a pain, and the outcome). Write the right side as the opposite of the left. Messaging is then extracted from the contrast, not invented.

Flag ICP work as a prerequisite when pipeline conversion varies widely by segment, when cycle length varies without explanation, when marketing and sales disagree on who they sell to, or when the company cannot name a set of comparable customers it would want more of.

## Operating model

The company runs on three rings:

- **Governance (outer).** Strategy, priorities, KPIs, and rhythm. Gap analysis between current and desired state is the real roadmap.
- **Enablement (middle).** People, processes, platforms, and the data spine (definitions, flows, quality, one agreed version of the numbers).
- **Value creation (core).** The product engine and the revenue engine. Product flows out to customers; customer learning flows back.

Problems usually sit one ring out from where they appear. If pipeline is weak, look at process and data. If reps underperform, look at platform configuration and coaching. If the forecast is unreliable, look at cadence and KPI definitions. When the constraint sits outside revenue operations, such as in product or governance, name that and work with the owning function.

## Tech stack

Evaluate the stack through two lenses.

**Operational lens.**
1. Map the current state: every tool, its users, what it connects to, the data it holds, its cost, and its contract owner. Most companies cannot produce this list, and that is itself a finding.
2. Measure adoption from usage data, not licence counts. Shelfware is spend with no output.
3. Check integration health: what flows, in real time or in batch, what happens when a sync breaks, and who is alerted. "Nobody" is the biggest risk.
4. Identify overlaps and gaps. Two tools doing one job fragment the data. No tool for a critical function creates workarounds.
5. Test the stack against the real process. If reps work around the CRM instead of in it, the implementation is the problem, not the tool.

**Activation lens.** The question is how data moves and activates, not which tools exist. Batch syncs between systems create lag and inconsistency. Where the company has the data maturity to run it, a shared warehouse feeding both sales and marketing tools removes much of the integration burden. Without that maturity, it adds risk.

**Consolidation bias.** Every extra tool adds integration work, fragmentation, onboarding cost, and vendor management. Add one only when the current stack cannot do the use case, and the new tool either replaces functionality, enables real-time activation, or reduces the number of vendors. If none of those hold, it is debt, not capability.

**Stack evolution.** Early stage usually runs on one platform. Growth brings best-of-breed point solutions and integration complexity. Scale can move toward a shared data layer. Know which stage the client is in before recommending a change, because the current architecture constrains what is achievable.

## Flywheel

Revenue systems compound in one direction or decay in the other. Systematise the capabilities that repeat: lead routing, deal scoring, forecast accuracy, handoffs. Each systematised capability frees capacity, which funds the next. The diagnostic question is whether growth is linear or compounding year on year. If linear, the flywheel is broken and needs redesign.

## Output

- The pipeline architecture: stages with their contracts, owners, SLAs, and red flags.
- The three-tier KPI set, with each Tier 3 metric's path to revenue written out.
- The calibration method for each target, from client history.
- The data hygiene rules: prevention, detection, correction.
- The upstream chain status: is the ICP grounded, and is messaging consistent?
- The stack decision, with the operational and activation lens applied.

## Diagnostic questions

1. If pipeline doubled tomorrow, would revenue double? If not, where is the constraint?
2. For each dashboard metric, can someone draw the chain to revenue in two sentences?
3. How long do deals sit in each stage, and which stage holds the most time?
4. Can every seller state the ideal customer and the reason to buy in one sentence?
5. What share of the stack's capability is in use, and what is the cost of the tools reps do not use?

## Quality bar

Every stage has an entry, an exit, an owner, and a time limit. Every metric has a path to revenue. Targets come from the client's own history, not an external table. Watch for dashboards without definitions, activity metrics with no revenue link, new tools bought to solve process problems, and external benchmarks treated as targets.

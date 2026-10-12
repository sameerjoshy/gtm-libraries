---
name: expansion-revenue-architect
version: 1.0.0
status: draft-for-review
description: Use to diagnose and build the expansion engine for B2B SaaS: fix gross retention first, then design the expansion motion (ownership by deal size, the CS-to-Sales handback, whitespace analysis across five dimensions, a readiness score with action bands), signal rules wired into the cadence, and a 90-day net revenue retention programme. Use when NRR is below target, GRR is below about 90%, expansion is accidental, or CS does not own revenue. Not for CS operations or health scoring (see cs-operations), pricing mechanics (see pricing-monetisation-ops), or handoff mechanics (see revenue-handoffs).
sources:
  - "Expansion revenue architecture (MIT, Rutger Katz / Neon Triforce), GRR-first principle, GRR bands and lever map, five NRR levers, ownership model by expansion size, CS-to-Sales handback steps, whitespace methodology, expansion readiness score and action bands, signal rules, 90-day NRR programme, usage-based pricing discussion, time-to-value, advocacy"
  - "Removed as unverified or vendor-sourced: valuation-uplift claims, NRR ranges by pricing model, in-app conversion benchmarks, usage-based pricing NRR and growth figures from a 2023 study, AI-platform pricing and capability claims, and survey medians presented as targets. Context only where kept"
  - "Corrected: the source's worked example of the cost of a 102% versus 115% NRR gap is removed because it depends on undisclosed assumptions. A method for building the calculation is given instead"
  - "Adapted for GTM-360: score weights, bands and thresholds are author defaults. Data protection points are flagged for counsel. Reference files in the source are not in this library and are not relied on"
---

# Expansion revenue architecture

## Purpose

Expansion revenue is the most profitable growth a SaaS company has, because the customer already exists. Most companies still leave it to chance: expansion happens when a good CSM happens to notice a need. This skill designs expansion as a system with signals, owners, handoffs, and a cadence that makes someone act.

Retention comes before expansion. Expansion layered on weak retention hides the problem rather than solving it.

## When to use

- Net revenue retention is below the client's target, or below about 110% for a company at growth stage.
- Gross revenue retention is below about 90%.
- Expansion happens by accident, with no owner and no signal.
- CS and sales disagree about who owns an upsell.
- Discounts keep appearing at renewal.

Route elsewhere when:

- The question is the health score, renewal timeline, or CS coverage. Use `cs-operations`.
- The question is the handoff mechanics. Use `revenue-handoffs`.
- The question is pricing structure or metering. Use `pricing-monetisation-ops`, which is not yet in this library.
- The question is metric definitions. Use `revenue-metrics`.

## Inputs

- Revenue by cohort for the last 12 to 24 months: starting ARR, expansion, contraction, and churn.
- Churn reasons for the last 12 months, and the churn autopsies if they exist.
- Product usage by account, including seats or consumption against plan limits.
- Account list with ARR, health, renewal date, and CSM.
- Current expansion pipeline and how it is sourced.
- Segment definitions and the sales and CS team structure.

## Procedure

### Step 1: Diagnose gross retention first

Net retention can look healthy while gross retention is weak. An account base with high net retention and low gross retention is relying on the surviving customers to grow, which is a structural risk, not a strength.

Use gross retention as the first filter:

| Gross retention | Reading | Action |
|---|---|---|
| Below 85% | Critical. Product fit or onboarding is failing. | Stop investing in expansion. Run churn autopsies on the last ten churned accounts. Fix product, onboarding, or ICP tightness. |
| 85 to 90% | Concerning. Churn is hidden by expansion. | Identify the top three churn drivers and fix the largest. Work on health scoring, the renewal process, and champion management. |
| 90 to 95% | Healthy. Ready to layer expansion. | Start the expansion architecture: signals, whitespace, and the handback. |
| Above 95% | Strong. Expansion is the growth lever. | Maximise expansion velocity, coverage, and product-led expansion. |

These bands are practice-based defaults. Check them against the client's segment and deal size.

**Lever order for fixing gross retention.** Start with the highest-impact lever that the client controls:

1. ICP tightness: stop selling to customers who will not succeed. This shows in gross retention only after one to two quarters.
2. Onboarding and time to first value: the first 90 days shape most renewal outcomes. Use `onboarding-activation`.
3. Champion management: losing the champion is a common churn predictor.
4. Health scoring and intervention plays: `cs-operations`.
5. Product gaps blocking adoption: a cross-functional fix that takes longer.
6. Pricing architecture: discount sunset and value alignment, through pricing governance.

### Step 2: Choose the expansion levers

Net retention equals gross retention plus expansion. Once gross retention is at or above about 90%, five levers drive expansion:

**Lever 1, pricing architecture.** Expansion happens automatically when the price metric grows with the customer's value. Usage-based and hybrid models can do this, but only where the product has a natural consumption metric. Check the design:

- A value metric that scales with customer success, such as seats, usage, or records processed.
- Tier thresholds with clear upgrade triggers.
- Automated alerts as usage nears plan limits.
- In-app upgrade prompts at a set utilisation level, such as 80%.
- Annual price escalation written into contracts, sized to what the client can defend.

Do not recommend a pricing model because a benchmark says it raises NRR. Check whether the client's product has a metric that grows with value.

**Lever 2, product-led expansion.** Build expansion into the product: premium features visible but locked, usage warnings with an upgrade path, team invitations that add seats, and usage patterns that show value in another department. Measure the conversion rate of each prompt on the client's own traffic.

**Lever 3, CS-led expansion.** The CS team identifies, qualifies, and either closes or hands off expansion. Step 3 covers the signals and ownership.

**Lever 4, sales-led expansion.** Large expansions, usually above about 30% of current ARR, or new product lines. Sales leads, with CS support.

**Lever 5, partner-led expansion.** Partners identify opportunities in shared accounts. Use the partner channel skill once it is written.

### Step 3: Wire the expansion signals and assign owners

**Signals the system should watch:**

- **Usage:** seats or usage approaching plan limits (above about 80%), adoption of premium features, active users rising for several months, new user groups appearing in other departments.
- **Relationship:** a champion promoted, a new executive sponsor engaged, positive survey trend across three readings, customers joining references or events.
- **Commercial:** headcount growth, a new budget cycle, a multi-year renewal coming up, interest from another business unit.
- **Outcomes:** value achieved ahead of plan, return on the original business case exceeded, new use cases raised by the customer.

Automated detection works for the usage signals. Relationship and outcome signals depend on CSM notes and need a required field in the CRM. Do not assume a signal is captured because it exists.

**Ownership by size.** Set the owner by the size of the expansion, measured as a share of current ARR:

| Expansion | Owner | Support | Handoff trigger |
|---|---|---|---|
| Seat growth, under about 10% | CS, automated | None | Product triggers |
| Small upsell, under about 20% | CS | None | CSM closes directly |
| Medium, about 20 to 50% | CS sources | Sales closes | CS packages the opportunity |
| Large, above about 50% | Sales | CS supports | CS introduces the sales lead to the champion, and stays involved |
| New product line | Sales | CS and product | CS identifies the need, sales runs the evaluation |
| Cross-sell to a new business unit | Sales | CS and CSM | A different buying group means a new sale |

These thresholds are defaults. Set them from the client's deal sizes.

### Step 4: Run the CS-to-Sales handback

For medium and large expansions, use this sequence:

1. **CS packages the opportunity.** Who is the champion? What has changed? Why now? What is the expansion need? What context came from the original sale?
2. **CS introduces sales to the champion.** A warm handoff, with CS on the first call.
3. **Sales runs a discovery,** not a price quote. There may be new stakeholders, new pain, and new budget dynamics.
4. **CS stays involved through close,** which keeps the relationship continuous and avoids the "you sold us and disappeared" reaction.
5. **CS owns post-expansion onboarding.** New features follow the same activation rigour as a new customer.

Credit model: decide and write down how sourced and closed revenue are credited. CS sourcing should be credited, and sales should be credited for the close. If expansion pipeline is not sourced by CS, the system is not working. Record the credit rule as a design decision, because it changes behaviour.

### Step 5: Map whitespace across five dimensions

Whitespace is the gap between what a customer uses and what they could use. It is the expansion pipeline that has not been created yet.

Map it per account across five dimensions:

- Products the customer owns, against the products relevant to them.
- Seats or users, against the users who could be licensed.
- Departments using the product, against those that could.
- Features in use, against those that solve their problems.
- Stakeholders engaged, against the decision-makers involved.

For each dimension, score current penetration from 0 to 100, then average the five scores into a total. Low penetration means high whitespace. Prioritise accounts by whitespace, health, and contract timing together. Multiplying the three is one heuristic, not a proven method, and the client should test whether it ranks accounts sensibly. Present the result in business reviews as a joint growth plan.

Run this for the top 20 accounts first.

### Step 6: Score expansion readiness

Score each account from 0 to 100 on five components. Default weights:

| Component | Default weight | What it measures |
|---|---|---|
| Usage growth | 30% | Trend in active use and consumption |
| Stakeholder breadth | 25% | Number and seniority of engaged stakeholders |
| Feature depth | 20% | Use of core and premium features |
| Health trajectory | 15% | Direction of the health score |
| Contract headroom | 10% | Room between current spend and the plan's limits |

Map scores to actions:

- **0 to 30, monitor.** No active pursuit. Focus on adoption and value.
- **31 to 50, seed.** The CSM plants ideas and shares relevant content.
- **51 to 70, qualify.** The CSM opens an expansion conversation and confirms interest and timing.
- **71 to 100, pursue.** An active opportunity. If it is above about 30% of ARR, hand it to sales.

Calibrate the weights after two quarters, by checking which scores preceded closed expansions.

### Step 7: Install signal rules in the cadence

A signal that fires must have an owner and a deadline. Use these defaults:

| Signal | Action | Owner | Forum |
|---|---|---|---|
| Expansion score crosses 70 | CSM starts the conversation within five business days | CSM | CS review |
| Usage above 80% of plan for two months | CSM contacts the customer before overage | CSM | Weekly revenue review |
| Champion promoted to a senior executive | Executive alignment meeting within two weeks | CSM | CS review |
| Healthy for six months, whitespace above 50% | Growth plan presented in the next business review | CSM and sales | Quarterly expansion review |
| Expansion above 30% of ARR created | Handback package within three days | CS manager | Pipeline review |
| Segment NRR falls below target | Strategic review: churn or lack of expansion? | CS leader and CRO | Monthly strategy review |
| Segment GRR falls below 90% | Pause expansion focus and diagnose retention | CEO and CRO | Quarterly reset |

### Step 8: Run the 90-day NRR programme

When NRR needs improving, run three phases:

- **Weeks 1 to 3, diagnose.** Audit the data, the systems, and the whitespace and pipeline. Output: an expansion diagnostic report, covering gross retention by segment, the churn reasons, the expansion sources, and the data gaps.
- **Weeks 4 to 6, design.** Design the motion: ownership, signals, handback, whitespace, and scoring. Enable the people who will run it. Output: an expansion system blueprint.
- **Weeks 7 to 12, install and measure.** Switch on the signals and the cadence, run the first handbacks, and report against the baseline each week. Output: the handback package in use, the business review framework, and results against the baseline at 90 days and six months.

The diagnostic usually points to one of three causes. Gross retention is too low, so fix retention first. Pricing creates no natural expansion path. Or expansion is accidental, with no signals, owners, or process. Name the cause before designing anything.

### Step 9: Build the NRR calculation for the client's business

Do not quote a gap in revenue without building it. Use the client's own numbers:

1. Take current ARR, and the current NRR.
2. Model two scenarios for NRR over three years, with the assumptions written out, such as the expansion rate and the churn rate.
3. Compound the ARR under each scenario, and show the difference by year.
4. Label the assumptions, and test the sensitivity of the result to each.

The difference between scenarios is only as good as the assumptions. Present it as a range, not a point estimate.

### Step 10: Use advocacy and time to value as multipliers

Customers who reach value quickly retain better and expand more, so time to first value is the foundation for everything above. See `onboarding-activation`.

Advocacy adds second-order revenue through references, referrals, and case studies. Wire the triggers into the expansion system: a promoter response triggers a reference request, and a closed expansion triggers a case study request. Ask before asking, and never make a reference request a condition of support.

### Step 11: Use AI and automation with review

AI-assisted tools can scan call notes and transcripts for expansion language, and some platforms score next-best actions. Two conditions apply:

- Start with a small pilot on the top 20 to 50 accounts, and compare the signals it finds with what CSMs find manually.
- Keep a human decision before any customer-visible action. Expansion scoring that drives material decisions about how an account is treated may need human review under data protection rules, including GDPR Article 22 in Europe. Where scores only feed a CSM's own judgement, the review is built in. Document the lawful basis for processing engagement data, typically legitimate interest with a balancing test, and check with counsel.

Platform features and vendor claims about AI are not evidence of what will work for this client. Decide on the pilot's results.

## Output

- The gross retention diagnosis, by segment, with the band and the lever order.
- The expansion levers the client should use, with the reason for each.
- The ownership model by expansion size, with the thresholds.
- The handback steps and the credit rule.
- The whitespace template and the first top-20 map.
- The readiness score, its weights, and the action bands.
- The signal rules, with owners and forums.
- The 90-day programme, with the baseline and the targets.

## Quality bar

Gross retention is diagnosed before expansion is designed. Every expansion has an owner by size. Signals are captured as fields that someone must fill, not assumed. Handbacks are written, with CS on the first call. Targets come from the client's baseline, and any external benchmark is labelled as context. Watch for expansion built on weak retention, expansion pipeline with no CS sourcing, revenue gaps quoted without assumptions, and scores that were never calibrated against closed deals.

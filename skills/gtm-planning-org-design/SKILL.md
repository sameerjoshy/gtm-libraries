---
name: gtm-planning-org-design
version: 1.0.0
status: draft-for-review
description: Use for go-to-market planning, choosing a motion and touch model, territory design, bottoms-up capacity and headcount planning, revenue org structure, and the RevOps function's staffing. Use when the sales team structure does not fit the deal size, territories look unfair, a revenue target has no capacity behind it, or a hiring plan is being built. Produces a motion decision, territory and capacity model, headcount and hiring plan, and efficiency checks, with assumptions labelled. Not for comp plans, ICP definition, or forecasting.
sources:
  - "GTM planning and org design (MIT, Rutger Katz / Neon Triforce), touch models by ACV and buyer, motion selection from product and buyer, growth-stage org patterns, territory models and sizing, team ratios, headcount model, ramp curves, efficiency ratios, expansion phases, retention math kept separate from acquisition math"
  - "RevOps org chart and team design (MIT, Rutger Katz / Neon Triforce), RevOps team size by stage, four role archetypes, hiring sequence, Systems Architect engagement modes"
  - "RevOps revenue planning, bottoms-up build recipe (MIT, Rutger Katz / Neon Triforce), segment the business, locked baseline, capacity formula with ramp and pipeline haircut, productivity assumptions with sources, scenario analysis"
---

# GTM planning and org design

Works out whether the revenue team is built for the product, the buyer, and the company's stage, and whether the revenue target has the capacity behind it. Builds the plan from capacity up, so a target is tested rather than assumed.

## Purpose

Give leadership a motion decision, a territory and capacity model, a headcount and hiring plan, and efficiency checks, all built from stated assumptions that someone can challenge. The plan should show what the team can produce at its current productivity, what each investment adds, and when hiring must start to be productive on time.

## Principles

- **Match the motion to the sale.** The touch model follows deal size, buyer seniority, and decision complexity. A high-touch team on a small deal does not pay back. A self-serve motion on a large complex deal leaves money on the table.
- **Start from capacity, not the target.** Build what the team can produce at current productivity first. Then show the gap to the target, and what closes it.
- **Lock the baseline.** Set the current-year baseline from actual data and do not adjust it during planning.
- **Ramp is capacity.** A new rep is a fraction of a rep until ramped. Count ramped-equivalents, not heads.
- **Hire ahead of need.** Hiring lead time plus ramp time decides when a role must be opened. Hiring is almost always later than the plan assumes.
- **Keep acquisition and retention math separate.** New-logo planning runs on conversion rates. Retention planning runs on retention rates over time. Small retention changes compound.
- **Sequence motions.** Prove one motion before adding another. Do not run two new motions at once, or the team cannot learn which one worked.
- **Label every benchmark.** Most published figures come from vendor reports, podcasts, or surveys. Treat them as unverified and use the client's own data where it exists.

## Inputs

1. Revenue target and period. Current ARR, bookings by segment, and the locked baseline.
2. Product and pricing: average deal size by segment, pricing model, and the product's complexity.
3. Buyer map: who buys, who decides, and how many stakeholders are involved.
4. Historical data for the last 12 months where possible: closed-won and closed-lost deals, cycle length, win rate, quota attainment, and ramp by hire cohort.
5. Current headcount by role, budget, and approved hiring plan.
6. Account and territory data: accounts by segment, revenue by account, pipeline by territory, and rep productivity.
7. Retention data: gross and net retention by segment, and churn causes.
8. Go-to-market cost: spend by function, and loaded cost per head.

If historical data is missing, say so and mark every affected assumption as provisional.

## Procedure

### Step 1: Choose the motion

Start with the product and the buyer, not the team you want to build.

| Touch model | Typical ACV | Buyer | Sales involvement | Typical org model |
|---|---|---|---|---|
| No touch (self-serve) | Under $1K | Individual contributor | None; product and marketing drive conversion | Product-led |
| Low touch | $1K to $10K | Team lead | Inbound response, demo on request | Small inside sales, product specialists |
| Medium touch | $10K to $50K | Director | Full cycle, mostly virtual | SDR to AE, inside sales |
| High touch | $50K to $250K | VP or C-level, committee | Consultative, multi-meeting | SDR to AE to SE, territories |
| Dedicated touch | $250K and above | C-suite, formal procurement | Full account team over quarters | Named account AE, SE, CSM pod |

These ACV bands are one framework's defaults. Set them from the client's own price points.

Check the choice with three questions:
1. Does the average deal size support the cost of the motion? At $5K ACV, a $200K OTE rep needs about 40 deals to cover their cost. At $100K ACV, self-serve is too thin for a complex decision.
2. Who buys, and how? Individual buyers point to low touch or self-serve. Department buyers point to medium touch. Executive buyers point to high touch or dedicated.
3. How complex is the decision? A single user with simple pricing suits no touch. A cross-functional decision with integration suits high touch.

Hybrid motions are normal above roughly $10M ARR. Keep each motion operationally separate, with its own funnel, metrics, and team.

By growth stage:
- Early (under about $5M ARR): founder-led sales, moving to the first AE hires. The motion is still being discovered. Do not over-specialise.
- Scale-up ($5M to $50M): specialise SDR, AE, and customer success. Formalise stages and playbooks. Motion choice is most expensive to get wrong here.
- Growth ($50M and above): multi-segment, multi-motion. Focus on territory and coverage efficiency.

### Step 2: Segment the business and lock the baseline

Divide the revenue into segments with different unit economics. Typical dimensions: revenue type (new business, expansion, renewal, services), customer size, go-to-market motion, and product line.

For each segment, lock the prior-year actual or current run-rate, with its data source. Do not adjust this baseline during planning. It is the anchor.

Use separate retention and acquisition math:
- Acquisition planning: how many leads at what conversion, to produce how much pipeline.
- Retention planning: what gross and net retention the base needs to hit the target without new logos. At 80 percent gross retention, a fifth of ARR must be replaced each year. At 95 percent gross retention with 110 percent net retention, the base grows on its own.

### Step 3: Design territories

Principles:
1. **Equal opportunity, not equal accounts.** Territories should offer roughly equal earning potential, weighted by addressable market, not account count.
2. **Start simple, add complexity as data improves.** First pass: geographic. Second pass: named accounts for enterprise, geographic for mid-market. Third pass: vertical overlays.
3. **Minimise disruption.** Territory changes break relationships. Design so territories can scale by splitting, not by reshuffling each year.

Models:
- **Geographic:** for mid-market and below, where volume matters. Watch for unequal market density.
- **Named accounts:** for enterprise, typically 20 to 50 accounts per AE, and 5 to 15 for strategic. Watch for account hoarding.
- **Vertical:** where the value proposition is industry-specific. Add verticals only after repeatable success in each.
- **Hybrid** (common at scale): named accounts plus verticals for enterprise, geographic for mid-market, pooled for SMB.

Sizing, for each potential territory:
1. Count addressable accounts that meet the ICP.
2. Estimate pipeline potential: accounts times historical conversion times average deal size.
3. Calculate pipeline needed per rep: quota divided by close rate.
4. Territories needed: total pipeline potential divided by pipeline needed per rep.

Validation: each territory should have roughly three to four times its quota in pipeline potential. Existing open deals and active customers should be distributed fairly. There should be enough new-account headroom for growth.

Rebalancing cadence: annual by default. Some sources argue for quarterly with current tools. Treat that as an option to test, not a standard.

### Step 4: Build the capacity model (bottoms-up)

The capacity question: if the team does what it did last year, how much revenue should it produce?

For each segment:

1. **Capacity:** effective headcount times annual quota, where effective headcount counts ramp. Example: 5 tenured AEs at full productivity, plus 2 new hires averaging 50 percent over a six-month ramp, gives 6.0 effective AEs.

2. **Ramp curve** for each role (defaults from one source; calibrate to the client's ramp data):
   - Account executive, six-month ramp: 0 percent in month 1, 25 percent in month 2, 50 percent in month 3, 70 percent in month 4, 85 percent in month 5, 100 percent from month 6.
   - SDR, three-month ramp: 20 percent, 60 percent, then 100 percent of pipeline target.
   - Sales engineer, two-month ramp: 50 percent, then 100 percent of typical deal-support load.

   Effective contribution of a new hire in the first year is computed from the curve, not assumed. A simpler and more conservative approach is to count a new hire at about 80 percent of a tenured rep for the year.

3. **Quota:** set from historical attainment, not from the board target. If last year's AEs achieved $800K at a given attach rate, the quota is around $800K, not $1M. Adjust for known market changes. Do not set quotas to match a top-down target until the bottoms-up is complete.

4. **Pipeline constraint:** if pipeline generation is the bottleneck, apply a haircut equal to the historical fill rate of capacity by pipeline. Apply a further haircut for territory overlap or allocation inefficiency.

5. **Slippage:** apply the historical slip rate to pipeline before counting it as bookings.

6. **Productivity assumptions:** record each assumption with its value and its source. Close rate, average deal size, cycle length, pipeline velocity, self-sourced share, marketing-sourced share, channel share, and pipeline coverage per AE. Mark any that come from outside the client's own data.

7. **Check the math connects.** Compare the pipeline available per AE with win rate and quota. If pipeline times win rate is well above quota, the gap between them is the question to answer: is the rest of the pipeline low-quality, stale, or delayed? If pipeline times win rate is below quota, the target cannot be met by the current team.

8. **Scenarios:** run a base case with no new investment, then each investment separately. For example: an extra marketing spend that adds pipeline, or a new AE hire that adds capacity only if pipeline exists to fill it.

Retention sensitivity, in the expansion segment: model the renewal base at current gross retention, plus expansion at current net expansion, plus new expansion from customers ready to expand. Then test the downside if retention falls by a few points, and the upside if more of the base becomes ready to expand.

### Step 5: Design the revenue org

**Team ratios** (vendor and survey sources, labelled as such; test against the client's own data):

| Ratio | Inbound-heavy | Balanced | Outbound-heavy | Enterprise |
|---|---|---|---|---|
| SDR to AE | 1 to 2 or 3 AEs | 1 to 1 or 2 AEs | 2 SDRs to 1 AE | 1 to 1 (dedicated) |

| Ratio | Guidance |
|---|---|
| AE to SE | SMB and mid-market: no dedicated SE. Mid-market to enterprise: 3 or 4 AEs per SE. Strategic: 2 AEs per SE, or 1 to 1 for complex products. |
| AE to CSM | High touch: 1 CSM per 20 to 40 accounts. Mid touch: 1 per 40 to 80. Low touch: 1 per 100 to 200 with automation. |
| Manager to rep | SDR: 6 to 8 per manager. SMB AE: 6 to 8. Enterprise AE: 4 to 6. CS: 6 to 10. |

**Org pattern by stage** (illustrative, not prescriptive):
- Early (about $1M to $5M ARR, 5 to 15 people): Head of Sales as player-coach, 2 to 4 AEs, 1 or 2 SDRs, one customer success person. RevOps is part-time or contracted.
- Growth (about $5M to $25M, 20 to 60 people): VP Sales with SDR, mid-market AE, and enterprise AE managers. Head of CS. A small RevOps team of 1 to 3.
- Scale (about $25M to $100M, 60 to 200 people): CRO with VP Sales, VP Customer Success, and VP Revenue Operations. Partnerships if channel exceeds about 15 percent of revenue.

**When to hire the first RevOps person:** at roughly $3M to $5M ARR, or earlier if the GTM is complex. Triggers: the CRM is not trusted, the leader cannot produce a reliable pipeline report, or comp administration takes several hours a month.

**RevOps function staffing** (from the RevOps org source; team sizes are guidance from practice):

| ARR stage | Team size | First hire | Next additions |
|---|---|---|---|
| Under $5M | 0 to 1 | Generalist consultant or fractional | None |
| $5M to $15M | 1 | RevOps manager (generalist) | CRM admin |
| $15M to $30M | 2 to 3 | Analyst | More ops |
| $30M to $75M | 4 to 6 | Business partners | BI or insights manager |
| $75M to $150M | 7 to 10 | Systems architect (FTE) | Marketing ops, CS ops leads |

Four archetypes, never confused: a generalist manager (connective tissue, never edits fields directly), a business partner (embedded in one GTM function), a systems architect (designs the stack for scale; not an admin), and an analyst (data and reporting, hired after the generalist).

Systems architect engagement comes in three modes: advisory at any stage, especially during platform launches; fractional when the team is junior; FTE when the team has 3 to 6 or more RevOps people, 10 or more integrated tools, and architecture decisions are a weekly bottleneck.

Structure evolves in four stages: siloed (ops reports to department heads), departmental (one RevOps manager, organised by function), functional (systems team and insights team, the critical transition), and evolved (enablement joins, cross-functional product-style teams).

### Step 6: Build the headcount and hiring plan

| Role | Current | Hiring (year 1) | Ramp (months) | Open by |
|---|---|---|---|---|
| Account executive | | | | |
| SDR | | | | |
| SE | | | | |
| Manager | | | | |

For each hire, the open date is the target productive date minus ramp time minus hiring lead time. Use the client's own time-to-hire and ramp data. Flag any role whose open date has already passed.

Fully-loaded cost per head: on-target earnings multiplied by roughly 1.3 to 1.5, to cover benefits, tools, and overhead. This is one planning convention, not a standard.

### Step 7: Check efficiency

Use the client's own data first. Published figures below are external and unverified.

- **GTM efficiency ratio:** total GTM spend divided by net new ARR. A common reading: under 1.0 is excellent, 1.0 to 1.5 is good, 1.5 to 2.0 is concerning, above 2.0 is broken.
- **Magic number:** net new ARR divided by prior-quarter GTM spend. A common reading: above 1.5 means under-investing, 1.0 to 1.5 is efficient, 0.5 to 1.0 needs optimisation, below 0.5 means cut spend and diagnose.
- **CAC payback:** CAC divided by (ARR times gross margin), in months. A common reading: under 12 for strong, 8 to 12 for SMB targets, 12 to 18 for mid-market, 18 to 24 for enterprise. Above 24 is a concern unless lifetime value is very high.
- **Sustainability check:** for each motion, CAC should be under about 20 percent of the lifetime revenue of the customers it acquires. A payback above 24 months means the motion can destroy value even while it grows ARR.

### Step 8: Decide and sequence

For each strategic option (move upmarket, add a segment, add a motion, hire a CRO):
- Describe the change in motion terms: cycle length, buyer personas, ACV, volume, SE investment, and territory model.
- Quantify the investment and the capacity it adds, using the capacity model.
- Name what must be true for it to pay back.

Hiring a CRO is usually premature before there are two or more distinct GTM motions and enough ARR for one leader to coordinate sales, customer success, and partnerships. A VP Sales is usually enough before that. The threshold in the source is roughly $15M ARR. Treat it as a guide, not a rule.

Never run two new motions at the same time. Add the adjacent motion only when the first produces consistent results.

### Step 9: Review cadence

- Monthly: actuals against the capacity model, ramp progress by cohort, and pipeline coverage.
- Quarterly: productivity assumptions, territory balance, and hiring plan.
- Annual: full re-baseline, territory redesign if needed, and the motion decision.
- After any material change: product launch, pricing change, acquisition, or a lost large customer.

## Output

1. **Motion decision:** the chosen touch model per segment, with the reasoning from deal size, buyer, and complexity.
2. **Segments and locked baseline:** with data sources.
3. **Territory design:** the model, the sizing, and the balance check.
4. **Capacity model:** effective headcount with ramp, quota basis, haircuts, and the productivity assumptions with sources.
5. **Gap to target:** what the current team produces, what is missing, and what closes it, with each lever's contribution.
6. **Headcount and hiring plan:** roles, numbers, ramp, and open dates.
7. **Org structure:** the stage pattern, the ratios, and the RevOps staffing decision.
8. **Efficiency checks:** using client data first, with external benchmarks labelled.
9. **Scenarios and sensitivity:** base case, each investment, and the retention downside.
10. **Open assumptions:** each provisional figure, its source, and who will confirm it.

## Quality bar

- The motion matches the deal size, buyer, and complexity.
- The baseline is locked and sourced.
- Capacity is built bottom-up, with ramp counted as effective headcount.
- Quota is based on historical attainment, not the top-down target.
- Pipeline is haircut for constraint and slippage before it counts as bookings.
- Every productivity assumption has a value and a source.
- Benchmarks from vendors, surveys, or podcasts are labelled as unverified.
- Hiring open dates are set from time-to-hire plus ramp.
- Acquisition and retention math are modelled separately.
- Scenarios show one change at a time.

## Rules

- MUST match the motion to deal size, buyer, and decision complexity, and say why.
- MUST build capacity from the team up before comparing it with the target.
- MUST lock the baseline and not adjust it during planning.
- MUST count ramp as effective capacity, not as headcount.
- MUST set quotas from historical attainment, not from a board target, until the bottoms-up is complete.
- MUST label every benchmark with its source, and mark it unverified where it is not the client's own data.
- MUST NOT present team ratios, efficiency thresholds, or ramp curves as industry standards.
- MUST NOT run two new motions at once.
- MUST show the investment and the capacity it adds before recommending a hire or a new motion.
- NEVER treat a provisional assumption as confirmed in the output.

## Boundaries

- Covers team structure, territories, capacity, and headcount. Compensation plans and quota design are a separate skill: `gtm-compensation`.
- Does not define the ICP. Use `icp-builder`.
- Does not forecast bookings period by period or set forecast categories. A forecasting skill is needed for that.
- Does not inspect the live pipeline. Use `pipeline-review`.
- Does not design the RevOps system or CRM configuration. Use `revops-data-governance` for data standards, and a platform skill for configuration.
- Does not set discount policy.
- Does not write outreach or messaging.

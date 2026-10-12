---
name: revenue-metrics
version: 1.0.0
status: draft-for-review
description: Use to define, calculate, and diagnose revenue metrics: the funnel and its conversion rates, pipeline velocity and its four levers, CAC, LTV, payback, NRR and GRR, Rule of 40, burn multiple, and cohorts. Provides the diagnostic sequence for when revenue is off track, the breakout method, and a cascade of scorecards by role. Covers what to measure and how to read it, not forecasting (see revops-forecasting) or meeting cadence (see the operating cadence skill).
sources:
  - "Revenue performance metrics (MIT, Rutger Katz / Neon Triforce), funnel stages and conversion rates, pipeline velocity formula and levers, unit economics formulas, retention metrics, revenue composition, Rule of 40, burn multiple, growth by stage, diagnostic sequence, breakout analysis, cohorts, role-based scorecards, deal health dimensions, conversation metrics, predictability tests"
  - "Benchmark tables in the source are drawn from vendor surveys, podcasts, and practice estimates of mixed vintage. They are context only. Each one must be checked against the client's own data before it is used as a target"
  - "Adapted for GTM-360: one formula error corrected (NRR-based LTV breaks when NRR is at or above 100%); a fourth deal-scoring scale flagged as a conflict; AI-product and AI-agent metrics kept as cautions, not targets"
---

# Revenue metrics

## Purpose

A metric is a diagnostic tool. Its value is the question it prompts. Revenue metrics form a chain from activity to revenue, and when revenue misses, the job is to find the broken link. Measure the right things at the right level of detail, and benchmark only against comparable companies.

## When to use

- Defining the metric set for a company or a team.
- Revenue is off track and the cause is unknown.
- Unit economics need checking before a budget or a hiring decision.
- A dashboard needs to be built for a particular audience.

Route elsewhere when:

- The question is the forecast number. Use `revops-forecasting`.
- The question is the meeting rhythm. Use the operating cadence skill.
- The question is data quality in the CRM. Use `revops-data-governance`.

## Inputs

- The revenue data by period: leads, qualified leads, opportunities, wins, deal values, cycle times, and cancellations.
- Customer-level revenue over time, with acquisition date and segment.
- Sales and marketing spend, and the headcount that supports it.
- Gross margin, to compute unit economics.
- The stage definitions in use, and whether they are applied consistently.

## Procedure

### Step 1: Build the minimum funnel

The minimum funnel that a B2B company needs to measure reliably has seven stages:

Leads, then marketing-qualified leads, then sales-qualified leads, then opportunities, then closed-won, then retained, then expanded.

Track the full twelve-stage version only where it adds a decision. Fix the seven before adding more.

Conversion rates between the stages show where the funnel breaks:

| Conversion | The question it answers |
|---|---|
| Lead to marketing-qualified | Is marketing attracting the right people? |
| Marketing-qualified to sales-qualified | Does the qualification definition match what sales needs? |
| Sales-qualified to opportunity | Is qualification working? |
| Opportunity to won | Is the sales process effective? |
| Won to onboarded | Is implementation working? |
| Retained to expanded | Are customers growing with the company? |

Benchmarks for each conversion vary widely by definition and source. Set the client's own baseline from the last four quarters, and compare against that.

### Step 2: Use pipeline velocity as the connecting formula

Revenue per period is the number of opportunities, times the win rate, times the average deal size, divided by the sales cycle length.

Worked example: 100 opportunities, a 25% win rate, and an average deal of 40,000 give 1,000,000 of pipeline value. If the cycle is 90 days, that is about 1,000,000 per quarter. Cut the cycle to 75 days and the same pipeline yields about 1,200,000 per quarter. Speed is a lever like any other.

The four levers, each with a diagnostic question:

- **Opportunities (volume).** Is enough qualified pipeline being created? Watch for volume that lowers quality, because it consumes selling capacity.
- **Win rate (conversion).** Are deals being won at a competitive rate? A rise from 25% to 30% is a 20% increase in revenue from the same pipeline.
- **Average deal size (value).** Is the full product being sold? Watch for larger deals that are the wrong fit, which inflate the average and then churn.
- **Sales cycle length (speed).** Are deals moving at the expected pace? Watch for compressed cycles that skip stages, because they lower win rate.

### Step 3: Calculate unit economics

**Customer acquisition cost.** Total sales and marketing cost divided by new customers. Fully loaded, it includes sales compensation and benefits, marketing programmes and headcount, the SDR team, sales engineering, the allocated cost of revenue operations, and sales tools. Segment it: inbound against outbound, enterprise against SMB, and new business against expansion. Expansion acquisition should cost materially less than new-business acquisition.

**Lifetime value.** Average revenue per account, times gross margin, times the average customer lifetime. The lifetime is one divided by the annual churn rate. For example, 30,000 at 80% margin with 10% annual churn gives 240,000.

Caution: when net revenue retention is at or above 100%, the simple formula breaks. A customer's revenue then grows, and the formula gives no finite lifetime. Use a discounted cash-flow model over five years, or cap the lifetime at five to seven years for planning.

**Lifetime value to acquisition cost.** Below 3 to 1 means growth is being bought unprofitably. Above 5 to 1 may mean the company is under-investing in growth. Read the ratio by segment, because enterprise, mid-market, and SMB economics differ.

**Payback period.** Acquisition cost divided by the monthly revenue per account, times gross margin. Example: 45,000 divided by (30,000 times 0.8, per year) is about 22.5 months. Most companies treat under 12 months as excellent and under 18 as healthy. Above 24 needs strong retention to justify it. These are common planning ranges, not standards.

### Step 4: Measure retention and expansion

**Net revenue retention.** Beginning recurring revenue, plus expansion, minus contraction, minus churn, divided by beginning recurring revenue.

Worked example: starting at 10 million, with 1.5 million expansion, 0.3 million contraction, and 0.7 million churn, the result is 105%.

**Gross revenue retention.** The same, without expansion. It cannot exceed 100%, and it shows how much revenue is kept before any expansion effort.

Read these as planning ranges, to be checked against the client's own history: net retention below 90% means the base is shrinking. Between 90 and 100% growth depends entirely on new customers. Between 100 and 110% the base is stable to growing. Above 110% the expansion engine is working.

**Why net retention matters more than growth.** A company growing 50% with 80% net retention must win new revenue equal to 70% of its base every year just to grow at that rate. A company growing 30% with 120% net retention needs new business equal to only about 10% of its base. The second company is more efficient and more durable.

**Revenue composition.** Split gross new recurring revenue into new business, expansion, and renewal, and track contraction and churn separately. At maturity, a healthy mix has new business and expansion each at a substantial share of gross new revenue. If expansion is under about a fifth, expansion is being left on the table. If new business is above about 70%, the company depends on acquisition.

Caution on AI-generated pipeline: a large share of intent signals now comes from automated research traffic, not buyers. Keep it out of the composition analysis, or track it as a separate source until it can be reliably identified in the CRM.

### Step 5: Track growth and efficiency

**Rule of 40.** Revenue growth rate plus profit margin. Above 40 is the usual target for later-stage companies. Early-stage companies, under about 25 million in revenue, are usually judged on growth first.

**Burn multiple.** Net cash burn divided by net new recurring revenue. Under 1 is exceptional. Between 1 and 1.5 is strong. Between 1.5 and 2 is acceptable at scale-up stage. Above 2 needs attention, and above 3 is a warning.

**Growth expectations by stage.** The common target trajectory is roughly tripling in the first years after product-market fit, then doubling. Planning ranges: 100 to 200% year on year at 1 to 5 million; 70 to 120% at 5 to 15 million; 40 to 80% at 15 to 50 million; and lower above that. These are heuristics, not standards.

### Step 6: Read cohorts

Group customers by the period they were acquired, and track revenue at each month from acquisition.

Questions a cohort table answers:

- Do cohorts grow over time? If not, the expansion engine is not working.
- How much is lost in the first six months? A large early loss points to onboarding.
- Do newer cohorts perform better? If yes, the product or the sales process is improving.

Track payback by cohort as well. If newer cohorts have lower acquisition cost, or higher revenue per account, payback is improving. It is one of the most useful signs of health.

### Step 7: Run the diagnostic sequence

When revenue is off track, check these in order, and stop at the first one that explains the miss.

1. **Volume.** Is enough entering the funnel? If not, the problem is demand generation: programmes, SDR output, and inbound channel health.
2. **Conversion.** Are the stages converting at the expected rate? Find the stage that breaks. Marketing-qualified to sales-qualified points to scoring or handoff. Sales-qualified to opportunity points to qualification. Opportunity to won points to the sales process or competition.
3. **Value.** Are deal sizes holding? Look at the trend, the discount rate, and the product mix. Falling values usually mean price pressure, the wrong segment mix, over-discounting, or narrower product selling.
4. **Velocity.** Is the pipeline moving at the expected pace? Look at days in each stage, cycle length, and stalled deals. Slowing usually means procurement delays, too many stakeholders, incomplete discovery, or no compelling event.
5. **Retention.** Are existing customers healthy? Look at gross and net retention, churn cohorts, health scores, and support trends.

### Step 8: Break the miss down

Once a metric is known to be off, slice it along four dimensions:

- **Who.** By rep or team. Is it systemic, or one person?
- **What.** By product. Is it the core product or one offering?
- **Where.** By segment, source, and territory. Is it one segment, one channel, or one region?
- **When.** By cohort or period. Is it recent, or a long-standing pattern? Did something change on a specific date?

Example: if win rate fell from 25% to 18%, and the drop sits in enterprise deals in one region, and most of those losses are to one competitor, the response is a competitive review for that region, not a company-wide change.

### Step 9: Build scorecards by role

Each role asks a different question, so each needs its own view. Cascade them, so that every rep metric rolls up to a manager metric, which rolls up to an executive one.

- **Executive** (weekly or monthly): recurring revenue and growth, net and gross retention, the Rule of 40, pipeline coverage, forecast accuracy, payback, lifetime-to-acquisition ratio, and burn multiple. Question: are we on track and efficient?
- **Manager** (weekly): pipeline created against target, by rep and by source; stage conversion against baseline; win rate by segment; average deal size; cycle length by stage; forecast against actual; speed to first contact. Question: where should I coach or intervene?
- **Rep** (daily or weekly): personal pipeline and coverage; deals by stage; quota attainment; deals at risk, meaning stalled, slipping, or without a next step. Question: what should I work on today?
- **Revenue operations** (weekly or monthly): data quality, process compliance, forecast accuracy trend, velocity trend, integration health, and field usage. Question: is the system working as designed?

If a rep metric does not ultimately connect to an executive metric, question why it is being tracked.

### Step 10: Score deal health

Score six dimensions from 0 to 3 for each open deal:

| Dimension | 0 | 1 | 2 | 3 |
|---|---|---|---|---|
| Next steps | None defined | Vague | Specific date and action | Shared plan with milestones |
| Activity | None for 14 or more days | Sporadic | Weekly | Several a week, across channels |
| Multi-threading | One contact | Two | Three or four | Five or more, including the decision-maker |
| Access to the economic buyer | None identified | Identified, no contact | Met once | Actively engaged in the process |
| Review | Never reviewed | Monthly | Fortnightly | Weekly with the manager |
| Methodology | No qualification data | Two or three fields | Complete | Used in the deal strategy |

Total from 0 to 18. Treat 13 to 18 as healthy, 10 to 12 as watch, and 9 or below as at risk for intervention. The thresholds are the author's defaults. Calibrate them against the client's won and lost deals.

Conflict to resolve: the library now has four deal-scoring scales. `deal-qualification-gates` uses 1 to 5 per dimension. `deal-blocker-maneuvers` uses -1 to +1. The six-dimension health score here uses 0 to 3. The `account-tier-scoring` skill uses signal weights. Pick one evidence scale per team, and do not average across them.

### Step 11: Measure conversations, with care

When call recording is in use, six measures give coaching signals:

- **Talk ratio.** The rep's share of speaking time. A typical target is 40 to 60%. Above 60% usually means the rep is pitching, not discovering.
- **Longest monologue.** Under about two and a half minutes.
- **Customer story.** The buyer tells a personal or organisational story, at least once in the call.
- **Interactivity.** Turns in the conversation at a steady pace, roughly every 30 to 60 seconds.
- **Patience.** Time the rep waits after a question before answering. At least about three seconds.
- **Discovery questions.** Eleven to fourteen per call is cited in the source. Below about eight suggests discovery is thin.

These are coaching signals, not scores. When AI agents conduct calls, separate their measures from the rep's, because the same measures mean different things for scripted calls.

### Step 12: Check predictability

Predictability is built from measurement:

- **Forecast variance** by period, as a coefficient of variation in close rates. Under about 10% is a good target.
- **Pipeline quality:** the share of pipeline that meets the team's evidence threshold.
- **Win rate by segment.** A large gap between segments usually means the ideal customer profile or the qualification is wrong for one of them.
- **Cycle time consistency:** the spread of days to close, by segment.
- **Stage conversion stability:** stable from one quarter to the next.

Before setting any quota, know these five: cost per meeting, conversion at each stage, sales cycle length, the number of meetings an account executive can run before quality drops, and whether there is pipeline to fill a new hire's calendar before hiring.

## Output

- The metric set for the audience, with each metric's definition and formula.
- The baseline for each conversion and each unit economic, from the client's own data.
- The diagnostic result: the stage where the funnel breaks, and the sliced view that explains it.
- The scorecards, one per role, and their cascade.
- The deal health scores for open deals, with those below 10 flagged.
- The list of benchmarks used, each with its source and whether it is validated against client data.

## Quality bar

Each metric has one definition, one owner, and one question it answers. Benchmarks are used only as comparisons, after they have been checked against the client's own data. Cascaded scorecards connect every rep metric to an executive one. The diagnostic runs in order and stops at the first real explanation. Watch for metrics with no question, benchmarks quoted as targets, deal scores that disagree across teams, and a dashboard that shows numbers but drives no decision.

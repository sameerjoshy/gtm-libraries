---
name: revops-forecasting
version: 1.0.0
status: draft-for-review
description: "Use when the revenue forecast is consistently wrong, when the team cannot predict its quarter number, when deals slip unexpectedly, or when a forecast call needs to inspect deals rather than read status. Sets forecast categories with written validation rules, reconciles the number from at least two independent methods, measures accuracy by rep and segment, checks pipeline coverage against win rate, and wires forecast breaches into an operating cadence. Not for deal truth scoring (see deal-qualification-gates)."
sources:
  - "Revenue forecasting (MIT, Rutger Katz / Neon Triforce), category-based forecasting with validation rules, conservative/expected/optimistic roll-up, triangulation of methods, the forecast call structure, accuracy formula and diagnosis, pipeline coverage from win rate, slippage haircut, evidence-based inputs, breach rules, revenue-type differences"
  - "Benchmark figures and probability weights in the source are vendor-reported or author defaults. They are labelled as starting points and must be calibrated per client before use"
  - "Adapted for GTM-360: platform-specific AI product claims removed, reference-file lookups replaced with the procedure itself, platform-agnostic"
---

# Revenue forecasting

## Purpose

A forecast is a commitment the business can plan against, not a prediction. The aim is a range narrow enough to act on. Most forecast misses come from one of three things: loose category rules, one method used alone, or deals that were never qualified. This skill fixes the method and the cadence. For whether each deal is real, use `deal-qualification-gates` first.

## When to use

- The forecast is consistently over or under the outcome.
- Deals slip out of the quarter without warning.
- The team cannot say what the quarter number will be, or why.
- A forecast call has become a status read-out.
- Pipeline coverage is being used to claim comfort without a basis.

Route elsewhere when:

- The question is whether a specific deal is real. Use `deal-qualification-gates`.
- The question is why a deal is slow. Use `deal-velocity`.
- The question is capacity planning for next year. Use `gtm-planning-org-design`.

## Principles

1. **Forecast the process, not the outcome.** Do not ask "will this close?" Ask what the next step is, when it is scheduled, who will be in the room, and what has to be true before the buyer moves. Forecast quality comes from deal inspection, not the seller's optimism.
2. **Use at least two methods and reconcile them.** When they agree, confidence rises. When they disagree, the gap is the diagnostic.
3. **Segment every conversion rate.** Enterprise and SMB convert differently. Inbound and outbound move at different speeds. New business and expansion differ in predictability. A blended average gives a blended, useless forecast.
4. **The forecast call manages risk.** Its purpose is to find deals at risk, move resources to committed deals, and check pipeline generation. A call where reps read out updates has no purpose.
5. **Measure accuracy by rep, segment, and quarter.** Patterns of who over-forecasts and who under-forecasts are themselves actionable.

## Inputs

- Forecast against outcome by period, rep and segment, from past quarters.
- Deal records with their category, stage, close date and last activity.
- Qualification evidence for each deal, from `deal-qualification-gates`.
- Pipeline coverage targets, and the segment definitions (enterprise and SMB, inbound and outbound, new and expansion).

## Procedure

Apply the methods in order, then reconcile them. Then run the cadence, accuracy, slippage, coverage and breach rules.

## Method 1: Category-based forecasting

Each deal is placed in one category by the rep and validated by management.

| Category | Meaning | Validation |
|---|---|---|
| Commit | The rep would stake their credibility that it closes this period. | See the Commit rule below. |
| Best case | Well progressed and likely, with one or more open risks, such as procurement, a competitor, or budget approval. | Named risks in writing, each with an owner. |
| Upside | Could close if things go right. Often a timing question. The deal is real and may slip. | A named condition that would move it. |
| Pipeline | Active but too early to call. | Being worked, with discovery still in progress. |

**The Commit rule.** A deal is Commit only if all of these are true:

- The buyer has explicitly confirmed intent for this period.
- The economic buyer is engaged.
- Commercial terms are agreed.
- A written close plan exists.
- Procurement or legal has started.
- The close date is inside the period.

If any item is unchecked, the deal is Best Case, not Commit.

Plain test: **if the rep cannot explain their Commit deal in two minutes, it is not a Commit.**

**Rolling up the number.** Present three figures, and keep them separate:

- Conservative: Commit at 90%.
- Expected: Commit at 90%, plus Best Case at 50%.
- Optimistic: the expected figure, plus Upside at 20%.

The 90, 50, and 20 weights are author defaults. Calibrate them from the client's own closed deals by category before using them in a board number. A wide gap between the conservative and optimistic figures means deal qualification needs work, not the arithmetic.

## Method 2: Stage-weighted pipeline

Weighted pipeline is the sum of deal value multiplied by the historical win probability at each deal's current stage. It removes rep judgement, so it works as a check on Method 1. Use the client's own stage conversion history. Segment it, and do not borrow an industry rate.

## Method 3: Historical run-rate

Project from past patterns: a simple run-rate, a trend-adjusted run-rate, or a seasonal one. It suits renewal and expansion revenue far better than variable new business.

## Method 4: Bottom-up capacity

Calculate what the team should produce, working from quota to deals to opportunities to meetings, adjusted for ramp. It is for annual planning and sanity checks, and it shows whether a gap is a capacity problem or a forecasting problem.

## Forecast cadence and the forecast call

A weekly rhythm keeps the forecast current:

- **Monday:** reps update the CRM and set categories.
- **Tuesday:** managers challenge the Commit deals.
- **Wednesday:** the director or VP rolls up and reviews variance.
- **Thursday:** the executive review, including a check on pipeline generation.

The forecast call runs in five parts:

1. **The number (two minutes):** Commit, Best Case, and the gap to target.
2. **At-risk Commits (most of the time):** what changed, the next step, the economic buyer, and what could block the close.
3. **Best Case deals that could become Commit (10 to 15 minutes).**
4. **Pipeline generation check (five minutes).**
5. **Actions (two minutes).**

Managers should listen for these red flags:

- A Commit whose close date has moved more than once.
- A Commit with no next step booked.
- An economic buyer who has not been engaged.
- A next step that is a status update, not a buyer action.
- A deal that changed category without a stated reason.

## Accuracy

Forecast accuracy for a period is:

`1 minus the absolute value of (actual minus forecast), divided by actual`

Example: a forecast of 1,000,000 with 900,000 closed gives 1 minus 100,000 divided by 900,000, which is about 88.9%.

Track it at three levels: company, segment, and rep.

Starting-point bands, to calibrate per client:

| Band | Variance |
|---|---|
| Elite | Within 5% |
| Strong | Within 10% |
| Average | 15 to 20% |
| Weak | 25% or more |

Read the direction of a miss first:

- **Consistent over-forecasting:** Commit criteria are loose, close dates are optimistic, or qualification is weak. Fix the categories and qualification.
- **Consistent under-forecasting:** reps are sandbagging, expansion is not captured, or late inbound is not in the forecast. Fix the capture and the incentives.
- **High variance:** deal volume is low, deal sizes are lumpy, or stage definitions differ between people. Fix the stage definitions, then the sizing.

## Slippage

Deals slip. Apply a haircut to Best Case and Upside rather than trusting their face value. Set the slip rate from the client's own history. Industry research cited in the source puts the figure near 36% in 2025. Use it only as a comparison point.

Example: if 36% slip, multiply Best Case by 0.64. Calibrate the slip rate before using the haircut in a number.

## Pipeline coverage

Coverage is qualified pipeline divided by the revenue target. It is a leading indicator of whether the target is reachable.

Do not use a flat 3x rule. Set the required coverage from the client's win rate:

- Required coverage is approximately one divided by the historical win rate.
- A 25% win rate needs about 4x coverage.
- A 15% win rate, typical for enterprise, needs about 5 to 6x.

Practical starting points: 3x minimum for mature teams, 3.5x healthy, 4x or more strong. Segment by deal size and win rate, then recalibrate.

Coverage by revenue type:

- New business: 3.5 to 4x, segmented by deal size.
- Expansion: 2.5 to 3x, using account health and usage as leading indicators.
- Renewal: a run-rate baseline at the client's gross retention, with named at-risk exceptions.

## Evidence-based inputs

The forecast should not depend only on rep-entered CRM fields. Build each deal's read from several sources, and treat the CRM field as the last of them:

1. **The CRM record:** stage, amount, dates. This is the claim.
2. **Conversation evidence:** call transcripts and email threads, read in full. What the buyer said about budget, timing, and process.
3. **Product usage:** for trials, pilots, and expansion, usage is the value signal. A Commit on a trial nobody uses is not a Commit.
4. **Account signals:** engagement from the buying committee outside the deal thread. Executives visiting the site, a sponsor engaging content, a champion going quiet.

If a category disagrees with the evidence beneath it, the evidence wins, and the category owner explains the difference on the forecast call. If the client uses evidence scores (see `deal-qualification-gates`), use them to validate Commit. For example: a Commit requires its critical event and decision-process scores to be at or above the client's threshold.

## Breach rules

Connect forecast signals to actions, so that each breach has an owner and a deadline. Starting thresholds, to calibrate:

| Signal | Starting threshold | Action |
|---|---|---|
| Coverage | Below the required multiple | Pipeline generation review this week |
| Commit | Below 0.9 times the target commit amount | Deal inspection of the Commit list |
| Accuracy | Variance trending above 20% | Investigate before the forecast call |
| Slippage | Above the client's normal rate | Review close dates and categories |

Severity levels, from informational to executive escalation, are set per client.

## Output

- The three-figure roll-up (conservative, expected, optimistic) with the method weights used.
- The accuracy measured for the last quarter, by rep, segment, and direction of miss.
- The list of Commit deals that fail the Commit rule, with the missing item named.
- The coverage calculation, with the required multiple shown.
- The breach rules that fired, with owners and dates.

## Quality bar

Categories have written definitions, and every rep applies them the same way. The quarter number comes from at least two methods that are reconciled, not one judgement call. Forecast calls inspect changed deals and red flags, not the full pipeline. Accuracy is measured every quarter, and it drives the next fix. Watch for Commit used as a hope category, coverage quoted with no win rate behind it, and a forecast that only ever goes up.

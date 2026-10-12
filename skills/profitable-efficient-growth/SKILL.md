---
name: profitable-efficient-growth
version: 1.0.0
description: "Use when a founder, revenue leader, or finance lead is planning for the year, preparing for a board or a raise, deciding whether to spend more on acquisition or fix the model first, or asks about unit economics such as CAC payback, net revenue retention, burn multiple, or magic number. Builds an efficiency scorecard from the company's own numbers, grades each metric against stated default thresholds, diagnoses whether growth is efficient or leaking, and suggests how to split the next dollar of go-to-market spend. Not for the pricing model itself (see pricing-monetisation-ops)."
---

# Profitable efficient growth

## Purpose

Growth that costs more than it returns is not growth. Teams often scale spend while acquisition payback stretches and churn eats the gains, and the cash runs out before the model is fixed. This skill asks the question that protects the company first: can this growth be done efficiently? It builds the efficiency picture from the company's own numbers, shows where the engine is sound and where it leaks, and recommends where the next dollar should go.

## When to use

- Annual planning, a board meeting, or a fundraise is coming up.
- The team is debating whether to add acquisition spend or fix retention and pricing first.
- Growth is strong on the top line, but cash is under pressure.
- Someone asks about payback, retention, or burn.

Route elsewhere when:

- The question is the price or packaging. Use `pricing-monetisation-ops`.
- The question is the revenue forecast. Use `revops-forecasting`.
- The question is the planning calendar. Use `revops-revenue-planning`.

## Inputs

- New customers, churned customers, and expansion revenue by month, for at least 12 months.
- Acquisition spend by channel, and the sales and marketing headcount cost.
- Gross margin, and the cost to serve.
- Net burn, if the company is not yet profitable.
- Stage and market, which set how the thresholds should be read.

## The metrics

- **Customer lifetime value to acquisition cost (LTV:CAC).** Lifetime value is gross margin per customer over a stated horizon, discounted for churn. Do not use a simple perpetual formula when net retention is at or above 100 percent, because it breaks down.
- **CAC payback.** Months of gross margin from a new customer needed to recover its acquisition cost.
- **Net revenue retention (NRR).** Revenue from a cohort a year later, including expansion and churn, as a share of its starting revenue.
- **Rule of 40.** Growth rate plus profit margin (or free-cash-flow margin).
- **Magic number.** Net new recurring revenue in a period, divided by the sales and marketing spend that produced it.
- **Burn multiple.** Net burn divided by net new recurring revenue.

Default thresholds to test against the company's own numbers: LTV to CAC of about 3 to 1 or better, payback under about 12 months, NRR above about 110 percent, rule of 40 at or above 40, magic number above about 0.75, and burn multiple under about 1.5. Stage changes what is reasonable. Label every threshold as a default.

## Procedure

1. **Compute each metric** from the company's own data, with the formula and the period shown.
2. **Grade each metric** against the defaults, and mark the grade as strong, borderline, or weak. Show the evidence.
3. **Diagnose the engine.** Is it scale-ready, where unit economics are sound and scaling adds value? Or is it leaking, where acquisition spend returns less than it costs and retention is the constraint? Name the one metric that drives the diagnosis.
4. **If scale-ready,** recommend where to add spend, by channel and by expected payback.
5. **If leaking,** recommend fixing the model first: retention, pricing, or the channel with the worst payback. Set the threshold that would justify resuming spend.
6. **Split the next dollar** across three tranches: proven uses (roughly 60 percent of the budget, with known payback), probable uses (about 30 percent, promising but less tested), and experimental uses (about 10 percent, with a stated test and a kill rule).

## Output

- The metric table: value, formula, period, grade, and evidence.
- The diagnosis: scale-ready or leaking, with the driving metric.
- The recommendation: where to add spend, or what to fix first, with the threshold for resuming.
- The tranche split, with the test and kill rule for each experimental use.

## Quality bar

Every metric shows its formula and period. Thresholds are labelled as defaults. The diagnosis names one driving metric. Spend is not increased on a channel with weak payback. Watch for lifetime value formulas applied where retention is above 100 percent, thresholds presented as industry standards, and a growth plan with no efficiency check.

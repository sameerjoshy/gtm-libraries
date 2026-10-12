---
name: paid-search-unit-economics
version: 1.2.0
description: "Use when someone asks what a paid search number implies before committing spend: a budget projection, a target cost per acquisition or return on spend, an impression-share opportunity, a break-even figure, or a \"what would happen if\" question. Works from numbers the team already has, derives the core rates (cost per acquisition, return on spend, click-through rate, cost per click, conversion rate), chains them forward explicitly, and shows the distance to target and a sensitivity check. No live account access is needed. Not for diagnosing a live account (see `paid-search-quality-diagnosis`)."
---

# Paid search unit economics

## Purpose

Many paid search questions are arithmetic dressed as strategy. Someone wants to know what a budget buys, what cost per acquisition is needed, or whether a target is reachable. This skill answers those with the work shown, so the assumptions are visible and can be challenged before money is committed.

## When to use

- A budget or conversion forecast is needed before a campaign is approved.
- A target cost per acquisition or return on spend has been set and needs checking.
- Someone asks what would happen if a rate changed.
- A break-even figure is needed for a bidding or pricing decision.

Route elsewhere when:

- The question is why a live campaign is underperforming. Use `paid-search-quality-diagnosis`.
- The question is where to move money inside the account. Use `paid-search-budget-reallocation`.
- The question is the cost per lead break-even for a campaign. Use `paid-optimization-signals`.

## Inputs

- Spend, clicks, impressions, conversions, and revenue, for a period the team trusts.
- Or the rates directly: cost per click, click-through rate, conversion rate, and average revenue per conversion.
- The target, if one exists: cost per acquisition or return on spend.
- The planning horizon, daily or monthly.

### The five core rates

Derive these first and state which inputs each came from:

- **Cost per acquisition** = spend ÷ conversions
- **Return on spend** = revenue ÷ spend
- **Click-through rate** = clicks ÷ impressions
- **Cost per click** = spend ÷ clicks
- **Conversion rate** = conversions ÷ clicks

Every projection below is built from these five.

## Procedure

1. **Derive the core rates** from the inputs, and state the source of each.
2. **Chain for a budget or conversion forecast:**
   - daily clicks = daily budget ÷ cost per click,
   - daily conversions = daily clicks × conversion rate,
   - monthly figures = daily figure × 30.4.
   Use the average month length rather than thirty days, because the difference compounds across a year of planning.
3. **Show the target gap three ways:** where the account is now, what it needs to reach the target, and the exact number of extra conversions or revenue needed to close the gap. Do not stop at "below target".
4. **Estimate an impression-share opportunity** by converting the lost share into an estimated number of additional clicks, then into conversions at the current rate. State the assumption that the lost share would convert at the same rate.
5. **Run a sensitivity check.** Change the most uncertain input by a reasonable amount in each direction and show how far the answer moves. A forecast that changes sharply with a small change in conversion rate needs a caveat.
6. **Present the table.** Show each step, each input, and each result. The reader should be able to change one input and recalculate.

## Output

- The core rates, with their sources.
- The projection, with each step shown, daily and monthly.
- The target gap, shown three ways.
- The sensitivity result, with the input that moves the answer most.

## Quality bar

Every number traces to a stated input. The month length is 30.4 days. The target gap is shown as a number of conversions or revenue, not as a phrase. The sensitivity check names the input that matters most. Watch for a forecast with no shown steps, a flat thirty-day month, and an impression-share opportunity that assumes a conversion rate for the lost share without saying so.

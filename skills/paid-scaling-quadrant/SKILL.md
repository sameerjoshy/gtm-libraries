---
name: paid-scaling-quadrant
version: 1.0.0
status: draft-for-review
description: "Use to decide how to scale paid spend when a campaign is working, based on whether the constraint is budget or effort. Plots four levers on two axes (audiences, geography, ads, and objectives and bids), maps each to a situation (no budget and time to test, budget but no time, and so on), and sets the order for pulling them. Not for setting the first budget (see paid-budget-by-stage) or for diagnosing a campaign that is not working (see paid-optimisation-signals)."
sources:
  - "The scaling quadrant (MIT, Ivan Falco): the two axes (effort for horizontal scaling across campaigns, budget for vertical scaling of existing campaigns), the four quadrants (audiences, geography, ads, and objectives and bids), and the two scenarios of no budget with time to test and budget with no time to test"
  - "Removed: the third and later scenarios, which are not in the portion of the source read for this skill, and the named platform terms for each lever"
  - "Adapted for GTM-360: the rule to scale only a campaign that has passed the measurement check is an author addition"
---

# Paid scaling quadrant

## Purpose

"Do more of what works" is an oversimplification. Scaling paid spend depends on what is constraining the team: money, time, or both. This skill maps the four ways to scale onto those two constraints, so the team pulls the right lever instead of simply raising budgets.

## When to use

- A paid campaign is performing and the team wants more volume.
- Budget is available but the team lacks time to build new campaigns.
- Budget is tight and the team still wants more results.
- Scaling has stalled, and the team cannot say why.

Route elsewhere when:

- The question is whether the campaign works at all. Use `paid-optimisation-signals`.
- The question is whether measurement is good enough to scale on. Use `paid-measurement-scorecard`.
- The question is the total budget and its split. Use `paid-budget-by-stage`.

## Inputs

- The campaign's results and whether they are stable.
- The team's budget available for new money.
- The team's capacity to build new campaigns.
- Whether measurement is reliable enough to scale on.

## The two axes

- **Effort** runs left to right. Low effort means scaling a single campaign. High effort means scaling across campaigns and markets.
- **Budget** runs bottom to top. Low budget means little new money. High budget means more money to put into existing campaigns.

Scaling vertically means raising budgets on campaigns that already work. Scaling horizontally means building new campaigns to reach more people.

## The four levers

| Quadrant | Position | Lever |
|---|---|---|
| Audiences | High budget, low effort | Widen the audience, raise frequency within limits, add audience segments |
| Geography | High budget, high effort | Reach new countries or regions, with new targeting and copy checks |
| Ads | Low budget, low effort | Improve creative and messaging, test new ad formats |
| Objectives and bids | Low budget, high effort | Change the campaign objective or bid strategy to lower the cost per result |

## Scenarios

**No budget, and time to test.** Work the bottom quadrants. Improve the ads, and test different objectives or bid strategies to lower cost. Better ads or cheaper results free up budget, which then becomes more volume.

**Budget, but no time to test.** Work the top quadrants. Widen audiences first, because it needs the least setup. Add geographies only once the audience lever is used up, because each new geography needs its own checks.

## Procedure

1. **Name the constraint:** budget, time, or both.
2. **Confirm the campaign has passed the measurement check** and shows a stable return. Do not scale a campaign that has not been measured.
3. **Choose the quadrant** from the constraint, and start with the lowest-effort lever in that quadrant.
4. **Change one lever at a time,** and record the change in the experiment log.
5. **Check the return** after a set period before moving to the next lever.
6. **Stop scaling** when the cost per result rises above the breakeven figure for the campaign.

## Output

- The constraint, the quadrant chosen, and the lever to pull first.
- The change to make, and the date to check its effect.
- The point at which scaling should stop.

## Quality bar

Scaling starts from a measured, stable campaign. One lever changes at a time. Each change has a check date and a stop point. Watch for budgets raised on a campaign nobody measured, several levers changed together, and no stop point set.

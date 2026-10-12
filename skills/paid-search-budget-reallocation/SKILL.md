---
name: paid-search-budget-reallocation
version: 1.0.0
status: draft-for-review
description: Use when deciding where to move budget across existing paid search campaigns, for example when some campaigns are capped by budget, others are past their efficient spend, or a seasonal peak is coming. Treats the account as one budget envelope rather than separate silos, reads lost impression share as the signal for underfunded campaigns, compares marginal rather than average cost per result, and caps each move. Not for a new account with no history (see paid-channel-selection) or for the stage split (see paid-budget-by-stage).
sources:
  - "Portfolio-style budget reallocation across campaigns (MIT, John Williams): the envelope framing (the question is which campaign returns more for the next unit of money), impression share lost to budget as the signal for underfunded campaigns, marginal cost per result read alongside the average, the cap of roughly twenty to thirty percent per move, and protected minimums kept outside the optimisation"
  - "Removed: the named bidding strategy and the platform's shared-budget and learning-period terms, replaced by generic descriptions. The protected-minimums section was read in part and is restated only as a principle"
  - "Adapted for GTM-360: the twenty to thirty percent cap per move is an author default. The seasonal planning rule is an author addition"
---

# Paid search budget reallocation

## Purpose

An even split of budget across search campaigns protects the weakest ones and starves the strongest. The useful question is not whether a campaign deserves more money on its own, but which campaign returns more for the next unit of spend, given a fixed total. This skill sets up that comparison and limits how fast money moves, so the change can be judged.

## When to use

- Some campaigns are losing impressions because of budget, while others are spending past their efficient point.
- A seasonal peak is coming and budget needs to move ahead of it.
- A monthly review finds cost per result rising in one part of the account.

Route elsewhere when:

- The account is new and has no history to compare. Use `paid-channel-selection` first.
- The question is the split across demand stages. Use `paid-budget-by-stage`.
- The question is why a campaign is expensive. Use `paid-search-quality-diagnosis`.

## Inputs

- The total budget envelope for the period.
- Each campaign's spend, conversions, and cost per result over the last thirty days or more.
- Lost impression share to budget, per campaign.
- The marginal cost per result for each campaign, estimated from its recent spend changes.
- Minimum budgets the business has committed to keep, such as a brand defence campaign.

## Procedure

1. **Model the account as one envelope.** List every campaign that draws on the total. Do not reallocate inside a silo without checking the others.
2. **Find the underfunded campaigns.** Use lost impression share to budget as the main signal. A campaign losing a large share to budget is missing demand because of its cap, not because the auction is hard.
3. **Check the marginal cost, not the average.** An average hides campaigns that are efficient at low spend and expensive at the margin. Compare the cost of the last increment of spend in each campaign.
4. **Rank the moves.** Give the next unit of budget to the campaign with the best marginal return, and take it from the campaign with the worst.
5. **Cap each move** at roughly twenty to thirty percent of the receiving or giving campaign's budget. Larger single moves can trigger a fresh learning period and make the change impossible to judge.
6. **Hold protected minimums outside the optimisation.** Commitments the business has made stay fixed, and the envelope is reduced by them first.
7. **Plan ahead for seasonality.** If a peak is known, move budget before it arrives, in steps, and set a date to reverse the move.
8. **Set the check date** for each move, and judge it against the marginal figure, not the average.

## Output

- The envelope, with protected minimums shown separately.
- The ranked list of moves, each with its size, the campaigns involved, and the reason.
- The check date for each move, and the reversal plan for any seasonal change.

## Quality bar

The reallocation reads the whole envelope. The signal is lost impression share and marginal cost. No single move exceeds the cap. Protected minimums are not touched. Watch for budgets moved on average cost, one large jump instead of steps, and a campaign funded at the expense of a committed minimum.

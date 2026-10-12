---
name: account-selection-funnel
version: 1.0.0
description: "Use to decide how many target accounts an account-based programme needs for a revenue goal, how to stage accounts from identified to selecting, and which firmographic, technographic, CRM and lookalike criteria choose the accounts. Works backwards from the revenue target to the account count, then builds the list from layered criteria. Not for the campaign level (see abm-campaign-level-choice) or the stage metrics used to report on the programme (see abm-measurement-framework)."
---

# Account selection funnel

## Purpose

An account-based programme starts with accounts, not leads. Every pound or dollar of ad spend and every rep hour goes to the accounts that were chosen. This skill sizes the account list from the revenue goal, sets the stages an account moves through, and chooses accounts on layered evidence.

## When to use

- A revenue target has to be turned into a number of accounts to target.
- An account list is being built or rebuilt for a programme.
- A team is reporting that the list is too large, too small, or the wrong shape for the goal.

Route elsewhere when:
- The question is the campaign level for each segment. Use `abm-campaign-level-choice`.
- The question is the metrics used to report on stages. Use `abm-measurement-framework`.
- The question is the budget and plan. Use `abm-strategy-planner`.

## Inputs

- The revenue target, the average contract value, and the period it covers.
- The close rate and the qualification rate, from the team's own history where it exists.
- The stage conversion rates the team has measured, or the defaults in step 2 with a note that they are unverified.
- The ideal customer profile, with firmographic, technographic and CRM evidence available.
- Closed-lost, churned and previously engaged accounts, from the CRM.

## Procedure

1. **Work backwards from the revenue target.** Divide the revenue target by the contract value to get deals needed. Divide the deals by each conversion rate in turn, from close back through qualification, consideration, interest and awareness, to get the number of target accounts. Show each step.
2. **Apply the stage definitions.**
   - Identified: the account is in the campaign.
   - Aware: the account has received 50 or more ad impressions.
   - Interested: the account has 5 or more ad clicks, or 10 or more engagements.
   - Considering: the account has booked a demo or started a trial.
   - Selecting: the account has an open deal in the pipeline.
   The impression and engagement thresholds are defaults, to calibrate.
3. **Read the conversion arithmetic before quoting it.** Only a small share of targeted accounts reach an open pipeline opportunity, and fewer still close. A programme sized on the target list alone produces far fewer deals than the list suggests. State the implied opportunity and deal counts with the list size.
4. **Select on four layers.** Each layer narrows the list and carries its own evidence.
   - Firmographic fit: size band, revenue or funding stage, industry, geography and business model.
   - Technographic signals: a competitor in use, a competitor missing a feature the team now has, a redundant tool combination, or a recent change in stack.
   - CRM intelligence: closed-lost accounts from the past six to twelve months, lost to a competitor on a feature the team now has, previously engaged in outbound without converting, and churned customers.
   - Lookalikes: the shared attributes of the best customers, used to find similar accounts.
5. **Build the list from the ICP.** Define the ICP with firmographic and technographic criteria first, using win-loss patterns from the CRM. Then apply the layers in step 4, and record the source and date for each criterion.
6. **Check the count against the target.** If the layered list is smaller than the number from step 1, either widen a layer or lower the revenue target. Do not keep the target and shrink the bar silently.

## Output

- The revenue-to-accounts calculation, with each step shown.
- The stage definitions in use, with the thresholds marked as defaults or the team's own.
- The implied opportunity and deal counts for the list size.
- The four selection layers, each with its criteria, source and date.
- The layered list, and the gap to the target count, if any.

## Quality bar

Every account count is traceable to a stated rate. The default rates are labelled as defaults, not benchmarks. Each layer names its source. The list size and the revenue target are checked against each other before the list is used. Watch for a target account count that was never reconciled with the revenue goal, and a list built on a single layer.

## Rules

- Show the arithmetic before quoting an account count.
- Label every conversion rate as the team's own or as a default to calibrate.
- Do not change the revenue target to fit a list without saying so.
- Record the source and date of each selection criterion.

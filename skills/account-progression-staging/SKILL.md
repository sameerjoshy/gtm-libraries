---
name: account-progression-staging
version: 1.1.0
description: "Use to assign each account a single progression stage (unaware, aware, engaged, qualified, sales-ready, customer) from its full signal record, using rules that give the same result for the same inputs. Requires a buying group of several distinct contacts before an account can advance, so one enthusiastic user cannot fake momentum. Records each stage entry with its evidence, and shows whether an activity moved accounts forward, not just whether it produced clicks. Not for individual lead scoring (see account-tier-scoring)."
---

# Account progression staging

## Purpose

Touchpoint credit tells you which campaign got a click. It does not tell you whether an account moved closer to buying. This skill gives each account a single current stage, records when it entered that stage and why, and measures how activity changes the rate and speed of movement between stages. The result shows which work moves accounts, so budget can follow it.

## When to use

- The team wants to know whether activity moves accounts forward, not just whether it gets engagement.
- Sales-ready accounts need a consistent definition and an alert.
- A stuck account needs to be identified, with the reason for it.
- Someone asks why an account is at its current stage.

Route elsewhere when:

- The question is a score for individual accounts. Use `account-tier-scoring`.
- The question is the list of accounts to target. Use `prospect-list-building`.

## Inputs

- Account records with their contacts, and the signals each account has produced: engagement, replies, meetings, product use, and any third-party events.
- The stage definitions and the thresholds, as the team agrees them.
- Stage history, if the team already keeps it.

### Stages

Each account holds one stage at a time, and moves forward only on evidence:

1. **Unaware:** no meaningful signal yet.
2. **Aware:** repeated, low-intent activity, such as visits or content views, from one or more contacts.
3. **Engaged:** an active reply, a conversation, or sustained interaction.
4. **Qualified:** a buying-group signal, meaning a named contact in a relevant role has engaged and the need is stated.
5. **Sales-ready:** qualified, with the buying group gate met, and a recommended next action.
6. **Customer:** a closed-won relationship.

## Procedure

1. **Apply the buying-group gate.** An account can advance past "engaged" only with two or more distinct contacts in relevant roles (default). One user's activity, however strong, does not advance the account.
2. **Assign one stage** by applying the rules to the signal record, from the top stage down. The first stage whose rules are met is the stage. Record the rule that was met.
3. **Write a stage-entry record:** the account, the new stage, the date, the evidence that triggered it, and the time spent in the previous stage.
4. **Route sales-ready accounts** with the buying-group context: which roles are engaged, which are missing, and the recommended next action.
5. **Flag stuck accounts.** An account that has sat in one stage beyond the agreed period is listed for activation, with the reason it is stuck.
6. **Measure movement.** For each stage transition, compare the conversion rate and time to transition for accounts exposed to a given activity with those that were not, in a comparable group. Report the difference, with the group sizes, not only the raw rate.
7. **Review the thresholds** after a quarter. If the gate is too strict to let any account advance, or too loose to separate accounts, change it and record the change.

## Output

- Each account: its current stage, the date it entered, the rule and evidence behind it, and the time in the previous stage.
- Sales-ready accounts with buying-group context and next action.
- Stuck accounts with reasons.
- The movement report: transition rates and times, exposed versus comparable unexposed, with group sizes.

## Quality bar

Every stage has a rule and evidence that a reviewer can check. No account advances on one contact alone. The movement report shows a comparison group and sample sizes. Watch for stages assigned from a single loud contact, movement reported as a raw rate with no comparison, and thresholds changed without a record.

---
name: pipeline-review
version: 1.0.0
status: draft-for-review
description: Use when reviewing a live pipeline for coverage, stage aging, and risk before a forecast call or a recurring pipeline check-in. Flags stalled, regressed, under-threaded, or at-risk deals with cited evidence, recommends one action per issue, and reconciles the weekly pipeline movement. Not a forecast (see revops-forecasting), and not CRM data rules (see revops-data-governance).
sources:
  - "Pipeline review (MIT, Ido Goldberg / Swan), slice of 20 deals, per-deal flags with evidence, lightest action first, action cap of 10 to 15, approval before any CRM write"
  - "Pipeline signal review (MIT, Udi Cohen), risk ranking High, Medium, Low, contact-in-seat check, buying-group coverage gaps, 30-day activity gap, news and negative signals"
  - "Pipeline visibility (MIT, Rutger Katz / Neon Triforce), stage exit criteria, historical stage baseline, stale thresholds by stage, close-date overdue handling, weekly pipeline waterfall, pipeline quality dimensions, reconciliation of movement"
---

# Pipeline review

Inspects the live pipeline, finds the deals that need attention, and gives one concrete next action for each, so that the forecast call is about real deals rather than optimism.

## Purpose

Before a forecast call, know which deals are stalled, regressing, thinly threaded, or carrying dates and amounts that cannot be trusted, and what to do about each. Make the pipeline movement add up week to week. Stay on the inspection. Forecast methodology and CRM configuration are separate jobs.

## Principles

- **Evidence beside every flag.** A flag reads "Stalled: last activity 26 days ago, stage Proposal". Never a vague "looks at risk".
- **Stage-aware.** A 21-day gap is normal in one stage and alarming in another. Use the client's own stage rules, not one universal number.
- **Flags are questions, not verdicts.** A flag says the deal needs a look. Only the owner can say whether it is at risk.
- **Lightest action first.** A task to call the owner beats a restructuring of the deal. Recommend the smallest action that answers the flag.
- **Nothing written to the CRM without approval.** Recommendations first, writes only after the user says which to proceed with.
- **Bounded.** Slices of about 20 deals. No more than 10 to 15 recommended actions in one review. Those that do not make the list go to a follow-up pass.
- **Reconcile.** The pipeline movement must add back to the ending pipeline. Check the arithmetic in code.

## Inputs

1. Scope: whose pipeline (one owner, a team, or the whole org), which stages (mid-funnel by default), and the time horizon. Default: deals due to close this quarter, plus any deal older than 30 days regardless of close date.
2. Deal records: owner, stage, amount, close date, created date, last activity date, associated company, contacts engaged in the last 30 days, and stage history if available.
3. Stage rules: exit criteria per stage and the stale threshold per stage. If none are recorded, use the defaults in Step 3 and label the output as using defaults.
4. A pipeline snapshot from the previous review, for movement and change tracking. If none exists, say the movement section is not available this time.
5. Optional: news and signal sources for flagged accounts, and the buying-group roles the team requires per deal.

If the stage rules or the baseline are missing, say so in the report. Do not present defaults as the client's own data.

## Procedure

### Step 1: Scope the review

Confirm the owner, stages, and horizon. If not given, default to all open mid-funnel deals for the whole team. State the scope at the top of the output.

### Step 2: Check the stage design before judging deals

A flag depends on the stage it sits in. Before flagging, check:
- Each stage has a verifiable exit criterion, such as "budget confirmed" or "signed". Not "rep feels good".
- Stages describe buyer actions, not seller activity.
- Stage probabilities come from the client's own history where that exists. Measure the close rate from each stage over the past twelve months of closed deals. Default probabilities from common SaaS practice carry no research backing and must be labelled as such.

If the stage design is weak, note it in the report. A review run on broken stages reports noise faithfully.

### Step 3: Flag each deal (no enrichment)

For each deal in the slice, check the following using data already in the CRM. Keep one line per flag: deal, flag, evidence.

| Flag | Test | Default (replace with client's stage rule) |
|---|---|---|
| Stalled | No logged activity beyond the stage threshold | 21 days generically. Practice-based stage defaults: Discovery 7, Qualification 10, Solution Design 14, Proposal 7, Negotiation 5. |
| Regressed | Stage moved backwards | Compare stage history or the previous snapshot |
| Under-threaded | Fewer than 3 distinct contacts engaged in the last 30 days | 3 contacts |
| No economic buyer | No economic buyer engaged at stage 3 or later | Set by the client's stage design |
| Champion gone | Primary contact no longer at the company | Check the contact's current employer |
| Activity gap | No noted activity in 30 or more days | 30 days |
| Amount missing | Late-stage deal with no amount | Stage past discovery |
| Close date overdue | Close date in the past | Any |
| Close date stale | Close date more than 90 days out on a "this quarter" deal | 90 days |
| Close date pushed repeatedly | Pushed three or more times | 3 pushes |
| Amount decreased | Value fell since the last snapshot | Any |

A deal with several flags keeps all of them on one line, comma-separated. Discard unflagged deals from the working list.

Stage defaults note: the stale thresholds above are operational guardrails from practice, not research results. Teams with short cycles should tighten them and teams with long cycles should extend them. Calibrate from historical days-to-decision per stage within the first month.

### Step 4: Pull external signals for flagged deals only

For each flagged deal, check the associated company for news from the last 30 days: leadership moves, funding, layoffs, budget signals, product launches, and competitor activity. Record any fresh signal. It is often the angle for the next action.

Do not look up signals for unflagged deals. Most reviews concern the flagged subset, and enrichment spend should follow the flags.

### Step 5: Rank by risk

Assign each flagged deal a risk level:
- **High:** a departed champion, a missing economic buyer at a late stage, a negative business signal (layoffs, budget cut, competitor adoption), or two or more other flags at once.
- **Medium:** a single activity gap, under-threading in an early stage, or a stage that no longer matches the signals.
- **Low:** a single hygiene flag, such as a missing amount or a stale close date with otherwise healthy activity.

Weight the ranking by deal value, so that a high-risk large deal sits above a high-risk small one. Show the value beside each deal.

Then the three groups: At risk (high), Needs attention (medium), and On track (no material flag). Deals that were checked and showed nothing material are listed as On track, so that the reader can see they were examined.

### Step 6: One action per flag

Recommend the lightest action that answers each flag:

| Flag | Default action |
|---|---|
| Stalled, fresh signal exists | Re-engagement message anchored on the signal (hand off to the outbound skill when added) |
| Stalled, no fresh signal | Task for the owner to call or email |
| Regressed | Task to schedule a deal review with the owner |
| Under-threaded or no economic buyer | Multi-threading plan to find the missing roles (hand off to the multi-threading skill when added) |
| Champion gone | Find the champion's new role and whether they can still sponsor (hand off to `champion-job-change-tracking`) |
| Amount missing or close date stale or overdue | Task for the owner to update the record |
| Close date pushed repeatedly | Honest conversation about buyer readiness, owned by the manager |
| High risk with a negative business signal | Deal inspection with the manager, and check whether the deal should be closed |

Overdue close dates are the largest single source of forecast error. Recommend moving them to a new date only with the owner's confirmation. Never move dates automatically.

Do not execute any action. List the recommendations and ask which to proceed with.

### Step 7: Movement and reconciliation (when a prior snapshot exists)

Compute the weekly pipeline waterfall in code:

```
Starting pipeline
+ Created
+ Advanced (moved forward a stage)
- Pushed out (close date moved later)
+ Pulled in (close date moved earlier; verify before counting)
- Lost
- Won
= Ending pipeline (must equal the sum above)
```

If the sum does not match the ending pipeline, stop and find the difference before reporting. An unreconciled waterfall is not a result. Describe the pulled-in deals as upside only after verifying the new date is real.

### Step 8: Hygiene and pattern checks

Report these as portfolio figures, with their denominators:
- Share of pipeline value with overdue close dates. Operational target from practice: under 5%.
- Share of open deals with no amount.
- Share of open value that is stale by stage.
- Share of open deals with fewer than 3 engaged contacts.

Name any pattern that appears across several deals, such as one owner with most of the stale deals, or one stage where deals repeatedly stall. A pattern in the team's behaviour is more useful than a list of individual flags.

Pipeline quality scores combining engagement, threading, decision-maker access, time in stage, next steps, and trend are useful as an operational composite. Their weights are not published research. Set them from the client's own outcomes before using them to rank deals.

### Step 9: Report

```
PIPELINE REVIEW, <date>, <scope>
Stage rules: client's own | defaults (labelled)
<N> deals reviewed. <M> flagged. <K> recommended actions (max 15).

AT RISK (n)
  1. <deal> | <value> | <stage> | <flags> | last activity <N> days ago | fresh signal: yes/no
     Action: <one action>

NEEDS ATTENTION (n)
  ...

ON TRACK (n): <deal names and stages, nothing material found>

MOVEMENT (if prior snapshot exists): waterfall, reconciled yes/no

HYGIENE: overdue close dates x% of value; no amount x%; under-threaded x%

Bottom line: <n> actions recommended. Create the CRM tasks for the top <N>?
```

End with the approval question. Write nothing to the CRM until the user approves.

## Output

1. Scope, stage-rule source, and counts.
2. At-risk, needs-attention, and on-track lists, each deal with its evidence.
3. One recommended action per flag, capped at 15, lightest first.
4. Movement waterfall with reconciliation, when a prior snapshot exists.
5. Hygiene figures with denominators.
6. The approval question.

## Quality bar

- Every flag cites its evidence: days, dates, counts.
- Stage thresholds came from the client's rules, or the report says defaults were used.
- Signal lookups ran only on flagged deals.
- Every recommended action is the lightest one that answers its flag.
- No more than 15 actions were recommended.
- The waterfall reconciles to the ending pipeline, or the report says it does not.
- Pulled-in deals are described as upside only after verification.
- Benchmarks cited from vendor research are labelled as vendor-published, not as standards.
- Nothing was written to the CRM without approval.

## Rules

- MUST process deals in slices of about 20, and never load the whole pipeline into context.
- MUST cite specific evidence for every flag.
- MUST apply stage-aware thresholds and say whether they are the client's or defaults.
- MUST cap recommended actions at 15 and offer a follow-up pass for the rest.
- MUST reconcile the movement waterfall in code before reporting it.
- MUST end with an explicit approval gate. No CRM writes before approval.
- MUST NOT move close dates or change stages automatically.
- MUST NOT flag a deal as stalled in a stage where the normal gap is longer, until the stage rule has been checked.
- MUST NOT present vendor benchmarks as industry standards. Label the source and its date.
- NEVER forecast in this skill. Forecast methodology is a separate skill.

## Boundaries

- Inspects and flags the live pipeline. Does not produce the forecast or its commit and best-case categories: a forecast skill is needed for that.
- Does not configure the CRM, its stages, or its fields. Data governance is covered by `revops-data-governance`.
- Does not model creator-channel or campaign pipeline. Such models are separate.
- Hands off deal-level plays to other skills: `deal-blocker-maneuvers` for a complex deal's next move, `champion-job-change-tracking` for a departed champion, and the outbound and multi-threading skills once they are added to the library.
- Does not write outreach or sequences.

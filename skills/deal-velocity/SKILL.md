---
name: deal-velocity
version: 1.0.0
status: draft-for-review
description: Use when deals stall at specific stages, sales cycles run longer than the segment allows, or the pipeline is large but little closes. Diagnoses which lever of the velocity equation is binding (qualification, stage progression, volume, deal size, or zombie deals), sets stage exit criteria that reflect buyer actions, flags and triages zombie deals, and installs a weekly inspection rhythm. Treats slow deals as a speed problem, after deal truth has been checked by deal-qualification-gates. Not for scoring whether a deal is real.
sources:
  - "Deal velocity engineer (MIT, Rutger Katz / Neon Triforce), pipeline velocity equation and binding-constraint diagnosis, pipeline deflation, zombie criteria and triage, stage exit criteria based on buyer actions, deal health dimensions, multi-threading discipline, mutual action plan rules, signal-to-action rules, 90-day programme structure"
  - "Benchmarks and statistics in the source come from vendor research and composite surveys, of mixed vintage. They are context only, and each must be checked against the client's own data before use"
  - "Adapted for GTM-360: platform-specific configuration steps removed (see the platform skills, when added); a fifth deal-scoring scheme flagged as a conflict; the weighted health score kept as one option for a team to choose"
---

# Deal velocity

## Purpose

Velocity is a system output. Reps cannot will deals to move faster. The system decides how fast a deal can move, through the stage gates, the inspection rhythm, the qualification standard, and how zombie deals are removed. This skill finds the binding constraint and fixes that first.

Order of work: first check whether a deal is real, using `deal-qualification-gates`. Then check whether it is moving at a sensible pace, using this skill. Speed applied to an unreal deal only produces a faster loss.

## When to use

- Cycles are longer than the segment benchmark, or getting longer.
- Deals stall at the same stage again and again.
- The pipeline is large, but the number closing is small.
- The forecast keeps missing, and the pipeline looks inflated.
- A velocity programme needs scoping.

Route elsewhere when:

- The question is whether a deal is real. Use `deal-qualification-gates`.
- The question is how to handle one live, complex deal. Use `deal-blocker-maneuvers`.
- The question is the forecast number. Use `revops-forecasting`.
- The question is the wider set of metrics. Use `revenue-metrics`.

## Inputs

- Opportunities from the last 12 months, by segment and deal size: stage history, dates, value, outcome, and contact count.
- Stage definitions and any exit criteria currently in use.
- Activity logs for each open deal: the date of the last logged buyer interaction.
- Close date history, showing how many times each deal's close date has moved.
- The segment cycle benchmarks the client has agreed to use, or a plan to set them from the client's own history.

## The velocity equation

Pipeline velocity equals the number of opportunities, times the win rate, times the average deal size, divided by the sales cycle length.

The numerator needs all three terms to rise. The denominator needs to fall. Four levers, each can be the constraint.

Compounding: the levers multiply, so small gains add up. A 10% improvement in each of the four levers gives about 46% more velocity (1.1 to the fourth power is about 1.46). The source quotes 49% for the same case, which does not match the arithmetic. Use the calculation, not the quoted figure.

## Procedure

### Step 1: Measure the current state

Pull these figures for the last 12 months, by deal size:

- Average sales cycle length, against the segment benchmark.
- Win rate, from opportunity to closed-won.
- Average deal size, and its change over 12 months.
- Pipeline velocity per day, and its change over six months.
- Slippage rate: the share of deals whose close date moved past the period.
- Zombie share: deals older than twice the average cycle, against a target below 10%.
- Multi-threading rate: the share of deals with two or more buyer contacts.
- The stage with the steepest drop-off.

### Step 2: Identify the binding constraint

Use the symptom table to find the one lever that limits throughput:

| Symptom | Binding constraint | First response |
|---|---|---|
| Low win rate, normal cycle | Qualification. Weak deals are in the pipeline. | Tighten entry criteria. Enforce the ideal customer profile gate. |
| Normal win rate, long cycle | Stage progression. Deals are stalling. | Enforce exit criteria. Put mutual action plans in place. |
| Healthy metrics, low velocity | Volume. Too few deals. | The only case where more pipeline is the answer. |
| High win rate, short cycle, low revenue | Deal size. Winning small deals. | Review the ideal customer profile, pricing, and land-and-expand. |
| Metrics look fine, forecast keeps missing | Zombie deals inflating the pipeline. | Deflate the pipeline before anything else. |

Apply the theory of constraints: fix one constraint at a time. Fixing a non-constraint adds complexity and does not change throughput.

### Step 3: Deflate the pipeline

The reflex when a target is missed is to add pipeline. That is usually wrong. Pipeline with a low conversion rate can be made more valuable by removing its dead deals.

Worked example from the source, in simplified form: 20 million of pipeline closes 4 million, a 20% conversion. Removing zombie deals leaves 15 million, which still closes 4 million, so the conversion rises to about 27%. Fixing handoffs and next steps on the clean pipeline can then lift closes to 5 million from the same 15 million. The target is hit without any extra pipeline.

**Zombie criteria.** A deal is a zombie if it meets two or more of these:

- No logged activity in the last 14 days.
- The close date has been pushed at least twice.
- The deal has been in its current stage for more than twice the average time in that stage.
- No scheduled next step.
- Only one buyer contact.
- The close date is more than 30 days past.
- No economic buyer identified, at proposal stage or later.

**Triage.** Each zombie gets one of three outcomes, decided by the owner, with a date:

- Revive: a specific, buyer-facing reason to re-engage, with a named person and date.
- Push: a dated buyer action that will show whether the deal is alive.
- Close: closed-lost with a reason recorded.

The source states that closing is the right answer for about 60 to 70% of zombies, and that most managers close too few. Treat that share as a hypothesis to test against the client's own outcomes.

**Prevention.** Run automated detection each day against the criteria above. Review the flagged deals each week in the manager's pipeline meeting. Run a deeper scrub each month in the manager one-to-ones, and a purge with leadership each quarter.

### Step 4: Set stage exit criteria based on buyer actions

The most practical fix for velocity is an enforceable gate. Most teams have stages but no gates, so deals move forward because reps push them, not because the buyer has progressed.

The principle: advancement requires a buyer action, not a seller activity. "We sent the proposal" is a seller action. "They booked a review with their finance lead" is a buyer action.

Rules for the criteria:

- Keep three to five criteria per stage.
- Each criterion is something the buyer has done or said, with evidence in the record.
- Make the required fields a CRM rule where the platform allows. Keep the number of required fields small.
- Inspect them in the weekly review. "Show me the mutual action plan" is a coaching question, not a penalty.

Example criteria, to adapt:

- Entering solution design: the economic buyer is named, with their role, and the buyer has agreed to the next meeting.
- Entering proposal: at least three buyer contacts have engaged, and the buyer has confirmed the decision criteria in writing.
- Entering negotiation: the buyer has agreed the commercial scope, and procurement has been engaged.

A deal that cannot advance without its criteria is evidence that the system, not the rep, is the constraint.

### Step 5: Score deal health, and choose one scheme

This is the library default for deal health: six weighted dimensions, each scored, totalling 0 to 100. Use it as the team's single health score (see DECISIONS.md).

| Dimension | Weight | Scoring |
|---|---|---|
| Engagement recency (days since last buyer activity) | 20% | Under 7 days: 10. 7 to 14: 6. 14 to 21: 3. Over 21: 0. |
| Multi-threading (buyer contacts engaged) | 20% | 4 or more: 10. Three: 7. Two: 4. One: 1. |
| Stage velocity (days in stage against average) | 20% | Below average: 10. 1 to 1.5 times: 6. 1.5 to 2 times: 3. Over 2 times: 0. |
| Methodology adherence (exit criteria met) | 15% | All: 10. Most: 7. Some: 4. Few: 0. |
| Next step quality | 15% | Scheduled and confirmed: 10. Scheduled: 6. Vague: 3. None: 0. |
| Economic buyer access | 10% | Met and engaged: 10. Identified: 5. Unknown: 0. |

Bands: 80 to 100 healthy, on the standard cadence. 60 to 79 watch, coach at the next one-to-one. 40 to 59 at risk, intervene this week. Below 40 critical, triage now.

**Other scales in this library, and what each is for.** They measure different things, so they stay as separate fields:

1. `deal-qualification-gates`: 1 to 5 per dimension, with stage minimum totals.
2. `deal-blocker-maneuvers`: -1 to +1 per dimension, with stage bands.
3. `revenue-metrics`: 0 to 3 across six dimensions, totalling 0 to 18.
4. `account-tier-scoring`: signal weights, for accounts rather than deals.
5. This skill: weighted 0 to 100.

The health score is for triage and inspection. The first two scales score evidence quality for stage and blocker decisions, so keep deal truth on the gate scale. Do not average any of them together, and do not report the 0 to 18 scale alongside this score.

### Step 6: Treat single-threading as a risk

Single-threaded deals are the most common and most preventable risk. The source cites that they slip more often, and that broader engagement improves win rates on larger deals. Those figures are vendor research, so treat them as direction, not measured effect.

Multi-threading score, by the number of buyer contacts engaged in the last 30 days:

- One contact: critical. Flag it immediately.
- Two: high risk. One departure would end the deal.
- Three: moderate. Adequate for smaller deals.
- Four or more: healthy, and resilient to changes of contact.

Engagement means real two-way communication in the last 30 days. A name copied on an email does not count.

Coaching questions for a single-threaded deal:

1. Who else is affected by this problem?
2. Who will use it day to day?
3. Who controls the budget?
4. Who tried to solve this before?
5. Who would block this if they were not involved?

### Step 7: Use mutual action plans

A mutual action plan is a shared record of the steps, owners, and dates that lead to a decision. The rules this skill applies:

- The buyer owns more than half of the steps, because the decision is theirs.
- Every step has a date and a named owner.
- The plan is reviewed on every buyer call, as a living document.

If the buyer will not help build the plan, treat that as a finding about how seriously they are buying. The detailed method is in `mutual-action-plan-builder`, which applies the same principle with the buyer's own milestones.

### Step 8: Set the signal-to-action rules

A velocity system only works if each signal has an owner and a deadline.

| Signal | Action | Forum | Owner |
|---|---|---|---|
| Health score falls below 60 | Manager reviews at next one-to-one, and decides to coach, intervene, or close | Weekly pipeline review | Sales manager |
| Deal in stage for more than 1.5 times the average | Rep records the reason and the next step within 48 hours | Pipeline hygiene | Rep, then manager |
| Close date pushed a second time | Manager contacts the buyer directly, or joins the next call | Weekly revenue review | Sales manager |
| No activity for 14 days or more | Rep logs activity within 48 hours, or the deal moves to at-risk review | Pipeline review | Rep, then manager |
| Single-threaded at stage three or later | Cannot advance until a second contact is engaged | System validation | Rep |
| Segment win rate below the agreed floor | Strategic review: is it ideal customer profile, qualification, or competitive? | Monthly strategy review | Revenue leadership |
| Cycle more than 30% over benchmark | Deflation sprint and exit-criteria audit | Monthly strategy review | Revenue operations and sales leadership |
| Zombie share above 15% of pipeline | Mandatory scrub within five working days | Revenue review | Sales manager and revenue operations |

The thresholds (48 hours, 14 days, 15%, 30%) are defaults. Set them per client.

### Step 9: Run AI assistance only with a baseline

Automation can scale detection, scoring, and summary work. It needs a baseline first. Before any automated zombie flag or health score is trusted:

- Run the rule manually for at least one cycle, and compare it with what the managers actually decide.
- Check that the automated score does not disagree systematically with the managers' judgement, and when it does, find out why.
- Keep a human decision on any closed-lost or stage change.

The source's percentage claims about AI accuracy and time savings are vendor figures and are not used here.

### Step 10: Scope a velocity programme when velocity is the constraint

Three phases, each with a clear output:

1. **Diagnose (weeks 1 to 3).** Extract the data, find the patterns, and name the one constraint. Output: a velocity diagnostic.
2. **Design (weeks 4 to 6).** Build the exit criteria, the health model, the mutual action plan template, and the zombie detection rules. Output: a velocity system blueprint.
3. **Install and measure (weeks 7 to 12).** Turn the design on, adjust it, and build it into the operating cadence and reporting. Output: a first results report against the agreed targets.

Set targets against the client's own baseline. Revisit them at six months.

## Output

- The velocity scorecard for the client, against their own baseline and the agreed benchmark.
- The binding constraint, with the evidence for it.
- The zombie list, with a triage decision and an owner for each deal.
- The stage exit criteria, one set per stage, with the buyer action each one requires.
- The health scoring scheme chosen for the team, with the reason.
- The signal-to-action rules, with owners and deadlines.

## Quality bar

The binding constraint is named, and one fix is made at a time. Stage moves rest on buyer actions in the record. Zombies are triaged with a decision and a date, not left in the pipeline. Health scores are used to direct inspection, not to rank reps. A single scoring scheme is used across the team. Watch for pipeline added to fix a conversion problem, gates that reps can bypass, and benchmarks quoted without their source.

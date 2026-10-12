---
name: deal-qualification-gates
version: 1.0.0
description: "Use when a pipeline is full of deals that advance on optimism rather than buyer evidence. Scores the evidence quality behind each qualification dimension from 1 to 5, sets minimum totals and per-dimension floors for each stage, and enforces a qualify, downgrade, or kill verdict with a name and a date. Covers deal truth, not account fit (see icp-builder) and not deal speed (see deal-velocity). Its 1 to 5 scale is separate from the in-flight scoring in deal-blocker-maneuvers. Use one scale per team."
---

# Deal qualification gates

## Purpose

CRM stages record where a deal is. They rarely record how well the team knows what it claims about the deal. A conversation gets logged as a deal, the stage moves forward on hope, and the forecast inherits the fiction. This skill adds a second axis: a score for the quality of the evidence behind each qualification dimension, with minimum scores before a deal can advance.

This is a gate system, not an extra set of fields. Gates change behaviour. Fields do not.

## When to use

- The pipeline has deals at late stages with early-stage evidence.
- Reps report that every deal is closing, and the forecast keeps missing.
- Deals stall at the proposal stage with no clear reason.
- The team needs a stage definition that means something.
- A qualification framework is being rolled out.

Route elsewhere when:

- The question is whether the company is the right fit at all. Use `icp-builder`.
- The question is why a real deal is slow. Use `deal-velocity`.
- A live, complex deal needs an in-flight read and a next move. Use `deal-blocker-maneuvers`.

Scale rule: this skill's 1 to 5 scores and the -1 to +1 scores in `deal-blocker-maneuvers` must not be mixed in one forecast or one dashboard. Each is kept as its own labelled field. The team's deal health score is the 0 to 100 scale in `deal-velocity` (see DECISIONS.md).

## Inputs

- The stage model, and the exit criteria each stage currently has.
- The qualification framework the team uses, or the default SPICED.
- The open pipeline with each deal's stage, value, close date, and the evidence in the record (call notes, transcripts, emails, the buyer's own figures).
- The account tier for each deal, from the ICP work, so that deal health can be read against fit.

## Procedure

Apply the evidence-quality scale first, then the dimensions, then the stage gates. Deployment and rollout come after the gates are agreed.

## The evidence-quality scale

Score each dimension from 1 to 5. The scale grades evidence, not the rep's confidence.

| Score | Grade | Meaning |
|---|---|---|
| 1 | Unknown | Never asked. |
| 2 | Weak | A surface mention, not corroborated. For example, "they said budget shouldn't be an issue." |
| 3 | Confirmed | The buyer said it explicitly, and it is logged with a quote, a transcript, or an email. |
| 4 | Quantified | Numbers are attached: the cost of the problem, the number of people affected, a deadline date. |
| 5 | Validated | Corroborated by a third party or by system data. For example, their finance lead repeated it, usage data shows it, or a signed evaluation plan names it. |

The step that matters most is from 2 to 3: from "the rep believes it" to "the buyer said it and the record shows where." A pipeline where most dimensions sit at 2 is a mood, not a forecast.

## The dimensions

The default lens is SPICED, scored across six dimensions:

- Situation
- Pain
- Impact
- Critical event
- Decision criteria
- Decision process

The total is out of 30. If the team uses MEDDICC or BANT, keep the same scale and the same gates, and swap the dimensions. The framework gives the vocabulary. The gates make it a system.

## The stage gates

Minimum total score and per-dimension floor for each transition, for the six-dimension, 30-point model.

| Transition | Minimum total | What it enforces |
|---|---|---|
| Inbound to discovery | 7 | There is something real beyond a form fill. |
| Discovery to demo | 14 | Pain and situation are confirmed, not assumed. The demo has something specific to aim at. |
| Demo to proposal | 19 | Impact is at least quantified. A proposal without a number is a brochure. |
| Proposal to commit | 23 | The critical event and the decision process are hard. The team knows why now and how the buyer decides. |

Two enforcement rules:

1. **No dimension below its floor.** A deal can reach 19 in total with critical event at 1 and still not advance. By proposal stage, every dimension needs at least a 3. One dimension under its floor keeps the deal where it is. Do not round up. Go back, ask again, then qualify or kill.
2. **The critical-event forcing question:** "What breaks for this customer if they do nothing until next quarter?" If there is no concrete answer, critical event scores 1, and the record is a conversation, not a deal.

Any floor in this skill is a starting value. Calibrate it per client using their own closed-won and closed-lost deals before it drives a forecast. A stage gate that is set too high empties the pipeline. One set too low lets the fiction back in.

## Deployment

1. **CRM:** one property per dimension (the 1 to 5 score), plus a computed total shown beside the account's fit tier. Deal health is the fit tier combined with the evidence total, on one screen.
2. **Enforcement:** validate stage transitions where the CRM supports it. Otherwise, run a weekly exception report that lists every deal sitting in a stage its evidence does not support, with the missing dimensions named.
3. **Qualify-or-kill review:** each deal on the exception report gets one of three verdicts, with a named owner and a date.
   - Re-qualify: a named person asks the missing question by a named day.
   - Downgrade: move the deal back to the stage its evidence supports.
   - Kill: close as lost, and record the loss pattern. "Leave it and hope" is not a verdict.
4. **Scoring hygiene:** score when the evidence arrives, after calls, or from transcripts. Do not batch the scores from memory on a Friday. If an AI agent processes call transcripts, the dimension scores belong in that pipeline, because the transcript is the evidence.
5. **Expect resistance for about two weeks.** The gates are not an audit of the rep. They protect calendars from deals that were never going to close.

## Rollout

- **Week 1:** score the current pipeline with no consequences. The distribution is the diagnostic. A healthy pipeline shows scores rising with stage. A hope-based pipeline shows late-stage deals with early-stage evidence.
- **Week 2:** install the gates for new stage transitions only. Existing deals are grandfathered, but flagged on the exception report.
- **Week 4:** run the first qualify-or-kill review over the flagged backlog. Expect to remove a meaningful share of active pipeline. The source reports 15 to 30%. Treat that as a range to check against the client's own data, not a target.

## Diagnostic questions

Ask these before rollout, to see where the pipeline stands.

1. Take the three largest deals. For each one, what breaks for the buyer if they do nothing this quarter? If the answer starts with "I think," score it honestly.
2. What share of proposal-stage deals have a quantified impact number, in the buyer's own figures, anywhere in the record?
3. When did a deal last move backward a stage? If the answer is never, the stages are a ratchet, and the forecast inherits the fiction.
4. How many deals are older than twice the median cycle time, and what evidence score do they carry?
5. Who is allowed to kill a deal, and when did that last happen without a manager forcing it?

## Output

- The evidence distribution by stage, from the week-one scoring.
- The list of deals below their gate, with the missing dimensions named.
- A verdict for each deal (re-qualify, downgrade, or kill), with an owner and a date.
- The calibrated floors, if the client's own data is available, with the basis.

## Quality bar

Evidence scores rise with stage. Every score of 3 or higher points to something in the record: a quote, a transcript, or an email. No deal advances while a dimension is under its floor. Deals move backward when the evidence says so, and a downgrade is not treated as a failure. A pipeline that only ever moves forward is the sign that the gates are theatre.

---
name: deal-blocker-maneuvers
version: 1.1.0
description: "Use after a meaningful interaction on a complex, multi-stakeholder deal (a call, a stakeholder meeting, a procurement exchange) when the question is what to run next, not what is missing. Scores the deal's qualification from primary evidence only, reads it against the stage it is in, identifies the single worst blocker, and produces a two-cycle maneuver with a trigger, pre-mortem, verbatim opener, branches, and explicit abort criteria. Not for transactional or high-velocity deals."
---

# Deal blocker maneuvers

Turns a complex deal's qualification into one saved artifact the rep can act on: a stage-adjusted read, one named blocker, and a two-cycle move with abort criteria. The gaps that nobody has asked about are listed as literal questions.

## Purpose

Tell the rep what to do next week on a deal that is stuck, has gone quiet, or is about to be forecast. Stop it from being scored on optimism. Make the next move specific enough to run, and the stopping point clear enough that the rep will actually stop.

## When to use

- A complex, multi-stakeholder deal is stuck, has gone quiet, or is about to be forecast.
- A rep needs one named blocker, one two-cycle move and clear abort criteria for next week.

Route elsewhere when:
- The question is the qualification standard for the whole deal. Use `deal-qualification-gates`.
- The question is the agreed plan with the buyer. Use `mutual-action-plan-builder`.

## Principles

- **Primary evidence only.** Score what the buyer said or wrote. Never the rep's summary, confidence, or assurance that the economic buyer is engaged.
- **Unknown is zero.** An absent dimension scores 0. A guess dressed as a score is worse than an honest gap.
- **Read against the stage.** A raw total means nothing alone. +3 is healthy in discovery and alarming in negotiation.
- **One blocker, one maneuver.** Cycle 1 targets the single worst blocker. Cycle 2 starts only after cycle 1 reaches an exit state.
- **Abort before you start.** Define the failure condition before anyone is invested in the play.
- **Unknowns clustered behind one person are the warning.** Three or more zeros behind a single stakeholder means the deal has one source, however good the total looks.
- **Do not blend divergent stakeholders.** If the parties want different things, score them separately.

### Scope

Built for enterprise and complex deals: several stakeholders, a real evaluation, third parties or procurement in the path, and a cycle of months. Do not run the full framework on transactional deals, or deals that close in under about 30 days with no second stakeholder. The diagnostic overhead exceeds what those deals return. Use the team's lighter qualification standard instead.

Terminology: use the client's own labels for the eight dimensions and stages if they differ from the labels here. Declare the mapping once and use only those labels in output.

## Inputs

1. The primary context: call transcripts or recordings, email threads, meeting notes, and shared documents. These are the only evidence source for scoring.
2. The current qualification assessment, if one exists in the deal record or a prior review. Use it only per dimension, and only where it passes the provenance test in Step 2.
3. The stage and the exit criteria for that stage.
4. The stakeholder map: who is in the deal, their role, and when each was last heard from.
5. The last two interactions, and any stated next steps.
6. The forecast owner, the person who must be told the same day when a deal breaches an escalation condition.

## Procedure

### Step 1: Segmentation gate

Test whether one assessment is valid. If the definition of success, the decision-maker, or the risks differ across the parties, a blended assessment averages two realities into a third that describes neither.

Three outcomes:
- **Unified track:** one assessment.
- **Segmented track:** a separate assessment per party. The deal takes the weaker of the two positions. Never report a blended total.
- **Stop and ask:** the deal shows divergent stakeholders, but the evidence cannot say how they diverge. Ask the one question that resolves it. Do not guess.

### Step 2: Establish the assessment

Eight dimensions: metrics, economic buyer, decision criteria, decision process, third parties and paper process, implicated pain and initiative, champion, and competition.

**Existing assessments.** Prefer an existing assessment over re-deriving one, but only where a dimension passes the provenance test. A dimension is usable only if it carries its evidence: a quote, a cited exchange, or a named source in the primary context. A qualification field on a deal record usually carries none. It is the rep's self-assessment in the form of a score. Accept the dimensions that cite evidence. Score every other dimension from the primary context, which will often mean 0.

Where an accepted dimension conflicts with newer evidence, say so and cite both sides. Do not overwrite it quietly.

**Mapping a different rubric.** Some assessments use two axes: how well evidenced a dimension is, and whether the answer favors you. Map them in this order, never by feel:

| Incoming | Maps to |
|---|---|
| Well evidenced, favorable | +1 |
| Well evidenced, neutral or adequate | +0.5 |
| Well evidenced, actively unfavorable, a condition that kills the deal unaddressed | -1 |
| Well evidenced, unfavorable but survivable | +0.5 |
| Asserted without evidence, any direction | 0 |
| Explicitly flagged as a gap | 0 |

The per-dimension criteria in Step 2a govern wherever the detail allows. The table is a fallback for coarse input. The champion dimension never maps below 0. A documented finding that a contact lacks influence means the champion is absent, not that there is a blocker. Record the original label beside the mapped score.

**Step 2a: Score each dimension** from the evidence, on this scale: -1 blocker, 0 unknown, +0.5 friction, +1 accelerator.

- **Metrics.** +1: the economic decision-maker has confirmed that a specific number achieves an outcome they own, in a case jointly agreed. +0.5: a target is known but treated as a nice-to-have, and is operational rather than tied to the financials. 0: no target stated. -1: the buyer cannot say what happens if the target is missed, or the conversation is anchored on a pilot budget disconnected from any larger outcome. A number the buyer is measured on is not the same as a number their business depends on.
- **Economic buyer.** +1: direct, substantive interaction with the person who releases the money, who stated the priority in their own words. +0.5: known, but every interaction is filtered through a subordinate. 0: cannot name the approver at this size. -1: identified, and actively blocked. The line between friction and blocker is passive versus active. "We haven't got to them yet" is friction. "You don't need to talk to her" is a blocker, and reps often record it as friction because it arrives politely.
- **Decision criteria.** +1: explicit, and they favor capabilities you hold and competitors do not, and you helped shape them. +0.5: generic criteria any credible vendor meets, or criteria you only learned. 0: unknown. -1: written around a competitor's strengths, or a constraint you cannot meet. Discovering criteria is not the same as influencing them.
- **Decision process.** +1: every step, approval, and timeline is documented and confirmed by someone inside the account. +0.5: a verbal outline nobody has validated. 0: not mapped. -1: stalled with no restart date, or you are excluded from steps you should be in.
- **Third parties and paper process.** Covers partners, agencies, resellers, integrators, procurement, legal, and security review. +1: every external party is identified, their role is clear, and none blocks delivery. +0.5: involved, but timelines or incentives are unclear. 0: no visibility at all. -1: actively blocking, deprioritizing, or gating the timeline. Read incentives, not intentions. A friendly partner who earns nothing from the integration is a blocker with good manners.
- **Implicated pain and initiative.** +1: a funded, time-bound initiative with executive sponsorship, and slipping it has a named cost. +0.5: pain acknowledged, but no deadline or initiative. 0: unknown what prompted the evaluation. -1: no real pain, or not big enough to beat the other things competing for the budget. Doing nothing for two more quarters costs the buyer nothing, and this is where no-decision losses are decided.
- **Champion.** +1: proven. Advocates internally without prompting, has shared information you did not ask for, and has influenced an outcome at least once. +0.5: unproven. Friendly and responsive, but has never sold on your behalf. 0: absent. There is no -1. A contact with no influence, or who has misled you, was never a champion. Score them 0 and the next action becomes finding one. A +0.5 that has sat at +0.5 for months deserves a re-test: what has this person actually done for you since the last run?
- **Competition.** Include the status quo, which wins most often. +1: preferred or sole-sourced, with differentiation the buyer can say back to you. +0.5: a fair evaluation with identified advantages. 0: you do not know who else is being considered. -1: undifferentiated, a competitor is favored, or the criteria are written against you.

Total range: -7 to +8.

**Relevance test for a dimension that does not apply.** Score it +1 only where its absence is confirmed and favorable (for example, no third parties in the path, verified), and record why. Where it is merely not visible, it is 0. "No procurement involvement" and "nobody has mentioned procurement" are different, and the difference is often a quarter.

### Step 3: Read the score against the stage

Use the stage bands below. Map your own stage names onto the five bands.

| Band | Expected total | Hard floor | Additional gate |
|---|---|---|---|
| Discovery or qualification | 0 or more | -2 | Unknowns are normal |
| Validation | +2 or more | 0 | No unknowns on metrics, economic buyer, or champion |
| Proposal or business case | +4 or more | +2 | No dimension at -1 |
| Negotiation | +5.5 or more | +4 | Any -1 triggers a forecast review |
| Commit or close | +6.5 or more | +5 | Decision process and paper process both at +1 |

These are defaults. Calibrate them before they affect a forecast (see Calibration below).

**Gap test.** Compare the actual total with the expected total for the band.
- At or above expectation: on track. Work the highest-value unknown.
- Up to 1.5 below, and above the floor: recoverable inside the stage. Build a maneuver, and leave the forecast alone.
- More than 1.5 below, or under the hard floor: escalate to the forecast owner the same day. Either the deal is in the wrong stage, or something was scored on faith.

**Unknown-cluster override.** Regardless of the total, if three or more dimensions score 0 and the missing evidence all sits behind a single stakeholder, the deal does not hold its current stage. Escalate, and recommend moving the opportunity back one stage until a second independent source exists inside the account. The override never softens a read. A deal that also fails the gap test is not rescued by being read at an earlier stage. It fails both tests.

**Band gates have consequences, independent of the total:**

| Breached gate | Consequence |
|---|---|
| Validation, with an unknown on metrics, economic buyer, or champion | The deal cannot advance past validation. Each unknown becomes a discovery item this cycle. |
| Proposal, with any dimension at -1 | Cycle 1 must target that dimension. The proposal is not pursued while it stands. |
| Negotiation, with any dimension at -1 | Forecast review that week. The forecast owner decides whether the close date holds, and records it either way. |
| Commit, with decision process or paper process below +1 | The close date is an estimate, not a commitment, until both reach +1. |

**Stall rule.** No movement across two consecutive runs at validation or later is a stall at any stage. A live deal produces new information. A deal that has stopped producing it has usually stopped moving inside the account. Report the stall as a finding in its own right.

### Step 4: Pick the target

Sort the dimensions: blockers (-1), friction (+0.5), unknowns (0), accelerators (+1).

Cycle 1 targets the single worst blocker, meaning the one that would kill the deal first if left unresolved. Cycle 2 either flanks that blocker, or clears the highest-value unknown. Cycle 2 does not begin until cycle 1 reaches a defined exit state.

If there is no -1, target the unknown that most constrains the stage gate.

### Step 5: Construct the maneuver

Each cycle has four phases: observe, orient, decide, act.

**Observe.** Write triggers that two people reading the same context would agree have fired. "Two consecutive meetings rescheduled by them, and the last two substantive questions unanswered for more than four working days," not "the champion seems less engaged." Add a hold condition: do not act until the triggers are confirmed. A maneuver launched on suspicion burns the move and teaches the buyer to expect it.

**Orient.** State the reframe the move depends on, in one line. Almost every blocker has an obvious response that makes it worse: the champion goes quiet, so you follow up harder. Procurement stalls, so you escalate. The buyer says it is expensive, so you discount. Examples of the reframe:
- From asking for access to making the introduction serve the person you are asking. A deflection is usually self-protection.
- From proving value to removing risk. A buyer who agrees and still hesitates is exposed, not unconvinced.
- From selling the outcome to selling the first ninety days, where the objection is implementation capacity.

If you cannot state the reframe, you have a follow-up, not a maneuver. Send the follow-up and skip the rest.

If the blocker has already survived a straightforward attempt, classify the kind of contest first (a hostile negotiation, a zero-sum resource fight, or the sale of a financial abstraction). Each needs a different response, and ordinary qualification logic prescribes the same wrong move for all three.

**Decide.** Four checks, and all must pass before the move runs:
- Why the rep should care, in the rep's interest, not the company's.
- Pre-mortem: assume the move went badly. What is the worst realistic outcome? In complex deals it is usually one of: a champion who feels bypassed, a stakeholder whose authority was violated, a premature no, or an internal politics problem the rep does not see. The mitigation must sit inside the script, not in a warning after it.
- Go/no-go checklist:
  - [ ] The prerequisite fact is confirmed, not assumed.
  - [ ] The target stakeholder is currently responsive.
  - [ ] The asset the move needs exists and is ready.
  - [ ] The political cost from the pre-mortem is smaller than the gain.
  Any unchecked box sends the rep back to targeted discovery. An unchecked fourth box means the move is wrong, not early.

**Act.**
- Persona check: the register should be a peer diagnosing a business problem. Direct, focused on the buyer's outcome. No manufactured urgency and no gratitude as an opener. The test: would a peer of the buyer send this? If it reads as junior, rewrite it.
- Verbatim opening: write the actual two to four sentences the rep says or sends. Not a description of what to communicate. One opening per move.
- IF/THEN counter-moves: two to four branches for the responses you can predict. Branch on what the buyer does, never on what the rep hopes. A typical set: deflection to a subordinate (accept, and use them to establish the approval path); silence past the window (send a closing message that makes silence an answer, then stop); price objection (separate "cannot afford" from "does not believe the return"); buyer confirms the blocker openly (stop the move as successful, and treat the blocker as a known condition with a different play).
- Pitfall: one named warning specific to this move.
- Exit criteria, stated before execution:
  - Success: observable to a third party. A meeting held, a name given in writing, a written confirmation. Not "improved sentiment."
  - Abort: a bounded count or window, such as two attempts or ten working days, and what replaces this cycle.

The abort criterion is the most valuable line in the artifact. A rep who has invested in a play will run it again rather than conclude it failed. Naming the failure condition in advance is what makes stopping possible later.

### Step 6: Route and publish the missing-information report

Route each move to a lane: third parties and procurement, client-direct, or targeted discovery.

Write discovery items as literal questions addressed to a named person, never as topics. A topic gets postponed. A written question gets asked.

Every dimension scored 0 appears in the missing-information report as an unchecked item, with the question that would close it. This turns "we don't know" into an assignable task.

### Step 7: Persist the delta and re-run

Mark every dimension retained, upgraded, downgraded, or new, against the previous assessment. Change a score only on clear new evidence. Where new evidence contradicts an existing score, record both sides. Where nothing new has landed, retain the score and say so. Silence is neither progress nor decay.

Re-run at the review cadence. Default: after every meaningful interaction, and at least weekly.

**Writes to the deal record** need explicit human approval, field by field. The artifact is a recommendation, not an update.

### Calibration

The bands above are defaults. Calibrate them before they affect a forecast.

1. Take the last 30 to 40 closed deals that have a usable record, mixed won and lost. Score each deal once per stage it passed through, using only evidence available at that stage's exit. Score blind to the outcome where possible. A deal that reached negotiation yields four data points.
2. Count winners per stage, not deals. Aim for about 30 winners at the stage being calibrated. Below that, use the minimum and median of the winners as the floor and expectation, mark the bands provisional, and keep them out of forecast decisions.
3. Set the expectation near the 40th percentile of winners at that stage. The median makes half your winners read as behind, which teaches the team to ignore the score.
4. Set the hard floor near the 10th percentile of winners.
5. Check the floor against the losers. If less than a third of losses were below the floor at that stage, the floor is too low; raise it toward the 20th percentile of winners and re-check. If more than three quarters were below it, check whether breaches cluster just before the loss. If they do, the bands are recording the death of the deal, not predicting it. Put the effort into the earlier stages.
6. Note that the observations are correlated. A strong deal tends to score well at every stage, so the effective sample is smaller than the count. Prefer the fallback for longer than the raw numbers suggest.

## Output

One saved artifact per run:
1. **Segmentation result:** unified, segmented, or stop and ask.
2. **Assessment table:** each dimension with its score, its evidence quote or source, whether it was accepted or re-derived, and its change from the last run.
3. **Stage read:** the total, the band expectation, the gap, the hard-floor test, and any unknown-cluster override or stall flag.
4. **Escalation:** whether the forecast owner must be told today, and why.
5. **Primary blocker and maneuver:** cycle 1 and cycle 2 with observe, orient, decide, act, and the exit criteria.
6. **Missing-information report:** each zero as a literal question addressed to a named person, with its lane.
7. **Open questions:** anything the segmentation or provenance test could not settle.

## Quality bar

- Every score traces to a quote or a named source in the primary context.
- No dimension was scored from the rep's summary, confidence, or assurance.
- Every total is read against its stage band, never on its own.
- Any unknown cluster behind one stakeholder was checked against the override.
- Divergent stakeholders were scored separately, and the deal takes the weaker position.
- Cycle 1 targets one blocker. Cycle 2 has its own exit criteria and does not start early.
- Every move has an abort criterion that is observable to a third party.
- Every IF/THEN branch is keyed to the buyer's response.
- Every downgrade is explained in writing.
- Bands used for forecasting are marked provisional where calibration is incomplete.

## Rules

- MUST score only from primary evidence. NEVER score from a rep's summary, confidence level, or verbal assurance.
- MUST score absent evidence as 0. NEVER infer a score to avoid an unknown.
- MUST read every total against its stage band. NEVER report a raw score as healthy or unhealthy on its own.
- MUST stop and ask when the segmentation gate is unclear. NEVER blend divergent stakeholders into one total.
- MUST prefer an evidenced existing assessment over re-deriving one, and MUST state any conflict rather than overwriting.
- MUST NOT give the champion a -1. A contact with no influence is absent, scored 0.
- MUST give every maneuver an explicit abort criterion before it runs.
- MUST run a pre-mortem before any move that goes around a stakeholder. NEVER propose a move that bypasses a required approver without naming the political cost and its mitigation.
- MUST explain every downgrade in writing. NEVER overwrite a prior score silently.
- MUST NOT write to the deal record without explicit human approval, field by field.
- MUST treat bands as provisional until calibrated. NEVER let an uncalibrated band remove a deal from the forecast.
- MUST NOT run the full framework on a deal below the complexity floor.
- NEVER let outside jargon reach the rep. Use the client's labels.


- Runs after a deal interaction and produces the next move. It does not score accounts for fit: use `icp-builder` and `account-tier-scoring`.
- Does not forecast or set forecast categories. A forecasting skill is needed for that.
- Does not write outreach sequences. The opening line is a sentence the rep sends, not a campaign.
- Does not set discount or pricing policy.
- Does not run the pipeline-wide inspection: use `pipeline-review`. This skill works on one complex deal at a time.
- Mutual action plans and multi-threading are adjacent skills. Merge them later, and link here once they exist.

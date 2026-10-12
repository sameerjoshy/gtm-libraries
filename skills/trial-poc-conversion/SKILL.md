---
name: trial-poc-conversion
version: 1.0.0
status: draft-for-review
description: "Use when trials go nowhere, prospects want to test before buying, or evaluations expire without a verdict. Designs trials, POCs, and pilots as decision processes: picks the evaluation motion, contracts success criteria and the consequence before granting access, defines and instruments an activation milestone, runs a decision-forcing clock, and closes out expired evaluations as logged outcomes. Not for qualification (see deal-qualification-gates) or the procurement steps after a win (see procurement-navigation)."
sources:
  - "Trial and POC conversion (MIT, Rutger Katz / Neon Triforce): evaluation as a mutual project with an end date, choosing the motion per segment, the entry gate (criteria, then-what, owners, clock), activation-first design, midpoint readout, criteria-met and criteria-missed endings, zombie-trial hygiene"
  - "Removed as unverified: trial-to-paid ranges, activation-conversion splits, buyer-survey figures on ROI expectations and speed of deployment. These are replaced with the instruction to measure the client's own cohorts"
  - "Adapted for GTM-360: the 14-day and 30-day clocks, the day-3 stall check, and the 30-day zombie rule are author defaults to replace with the client's cohort data after two quarters"
---

# Trials and POCs that convert

## Purpose

A trial or proof of concept is supposed to end in a decision. In practice, many end in silence: access is granted to be accommodating, nobody agrees what success means, the clock is loose, and the expiry date passes without a verdict. The result is a pipeline full of undecided evaluations and a sales team that blames the prospect.

This skill treats every evaluation as a mutual project with three properties: an end date, a definition of done, and a pre-agreed consequence. If it lacks any of them, it is a giveaway, and it should not be granted.

## When to use

- Trials expire without a decision, or pile up unused.
- Prospects ask to test before they buy, and the team cannot say what a test would prove.
- Conversion from trial to paid is low, and nobody knows whether the trial or the buyer is the problem.
- A POC is about to start on a deal that has not been qualified.

Route elsewhere when:

- The question is whether the deal is qualified enough to justify any evaluation. Use `deal-qualification-gates` and `sales-methodology`.
- The question is the contracting steps after a successful evaluation. Use `procurement-navigation`.
- The question is discounting to get a trial over the line. Use `deal-desk-operations`.
- The question is reviving a lost or expired evaluation. Use `closed-lost-revival`.

## Inputs

- The evaluation types in use: self-serve trial, card-required trial, sales-assisted POC, or paid pilot.
- A list of the last 90 days of evaluations, with start date, end date, activation state, and outcome.
- The product's core workflow, and the milestone that proves a customer got value from it.
- The pain evidence from discovery, including any quantified cost.
- Whether evaluations are free, and what they cost the company in people and infrastructure.

## Procedure

### Step 1: Pick the motion per segment

Choose the evaluation motion for each segment, not for the whole company:

- **Self-serve trial, no card.** Low-value deals where volume matters more than depth. Expect many starts and a low share of conversions. Activation has to happen without a person.
- **Card-required trial.** Deliberately fewer, hotter evaluations. Accept fewer starts in exchange for higher intent.
- **Sales-assisted POC.** Deals where the value justifies human time, and the buyer will run a real test with their own data.
- **Paid pilot.** Where the buyer will pay for the evaluation. This filters for intent most reliably.

Measure conversion against the client's own cohorts for each motion. A conversion rate that is strong for self-serve may be a crisis for sales-assisted work, and comparisons across motions mislead. External ranges are context at best, and their methods vary too much to use as targets.

### Step 2: Set the entry gate

Before granting any POC, four things must exist in writing. If the buyer will not help write them, that is a useful finding, and cheaper to learn now than after three weeks.

1. **Success criteria, two or three, measurable, and the buyer's own.** "See if we like it" is not a criterion. "Reduce manual triage time on the support queue by half, measured on their own data" is. The criteria come from the pain evidence gathered in discovery. An evaluation cannot prove value that discovery never quantified.
2. **The then-what.** What happens if the criteria are met: commercial terms agreed in advance, the signature path named, and a start date pencilled in. An evaluation without a pre-agreed consequence is a tour, not a decision.
3. **Named owners on both sides, and the evaluation committee.** Who judges, against what criteria, and on what date. A POC judged by one enthusiast converts to nothing. The economic buyer must see the readout, or the readout is a rehearsal.
4. **The clock.** Default durations, to replace with cohort data: around 14 days for self-serve and around 30 days for sales-assisted. Extend only for activity, never for silence. An expiry with no decision is itself a decision, and it is logged as one.

### Step 3: Design for activation

- **Define one activation milestone per motion.** It is the smallest observable event that proves the buyer used the core value on their own data. One milestone, not five.
- **Shrink the surface.** Configure the trial around the one workflow the criteria name, and hide or defer everything else. An evaluation of everything proves nothing.
- **Instrument time to activation.** Track the time from first access to the milestone, and alert when it stalls. For self-serve, a stall at day three is a warning. For assisted work, the first working session is the checkpoint.
- **Hold a midpoint readout on assisted evaluations.** Show progress against the criteria in the buyer's numbers, name the blockers, and restate the clock. This is where drift is caught while there is still time to act.

The core claim behind this step is that activation drives conversion. Test it on the client's data: split the last two quarters of trials by whether they activated, and compare conversion. If the gap is small, the activation definition is measuring the wrong thing.

### Step 4: Run the conversion close

The readout is a business case, not a demo recap. It shows the criteria against the results, in the buyer's numbers, with the effort it took, and then invokes the pre-agreed consequence.

**If the criteria are met:** invoke the agreement. Renegotiating from scratch after a successful POC gives away the leverage the design created. The sales team should not reopen price or scope.

**If the criteria are missed:** say so first, plainly. Then either scope one fix with a dated extension, or close the evaluation honestly and record the reason. A vendor who names its own miss keeps the relationship for a later attempt. A vendor who hides it loses the buyer's trust.

### Step 5: Clean up zombie evaluations

Expired and silent evaluations inflate the pipeline and waste outreach.

- An evaluation expired for thirty days or more with no decision is marked cold. Suppress warm outreach, and log the loss reason as "no decision".
- Re-entry happens through a fresh trigger, under the revival process (`closed-lost-revival`), not through "checking in on your trial".
- Never count un-activated evaluations in the weighted pipeline at the same probability as activated ones. The gap between them is usually the strongest single signal an evaluation-stage deal carries. Use the client's own split, not an external figure.

### Step 6: Measure the programme

Track each evaluation with these fields:

- Motion, segment, owner, and the committee size.
- Start date, the decision date set at the entry gate, and the actual end date.
- Activation state and the time to activation.
- Criteria met, missed, or not tested.
- Outcome: converted, lost with a reason, or expired without a decision.

Review the cohort each quarter. The useful questions: which motion converts best per segment, whether activation predicts conversion in this client's data, and how many evaluations ran past their clock without an agreed extension.

## Output

- The motion per segment, with the reason for each choice.
- The entry gate template: criteria, then-what, owners and committee, and the clock.
- The activation definition for each motion, and the stall rule.
- The midpoint readout template for assisted evaluations.
- The closing rules for criteria met and criteria missed.
- The zombie rule and the pipeline treatment for un-activated evaluations.
- The cohort dashboard and the quarterly review questions.

## Diagnostic questions

1. List the last ten evaluations. For how many can you produce success criteria written by the buyer?
2. What is the activation rate inside trials, and what is the conversion gap between activated and un-activated accounts?
3. What happens automatically when a trial expires today?
4. How many active POCs are past their original clock with no agreed extension?
5. When a POC succeeds, how often do commercial talks restart from zero?

## Quality bar

Every evaluation has written success criteria, a named committee, a consequence, and a decision date before access is granted. Activation is measured, and stalls are caught early. Expired evaluations are closed with a logged reason. Watch for access granted to be accommodating, criteria written by the seller alone, successful pilots that reopen price, and un-activated trials counted in the forecast.

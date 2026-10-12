---
name: sales-ramp-enablement
version: 1.0.0
status: draft-for-review
description: Use when new reps take too long to produce, capacity plans assume ramp that nobody measures, or certification is a formality. Designs rep ramp as an instrumented system: the ramp cost, a milestone-gated 30-60-90 with certification evidence, ramped-equivalent capacity, ramp-adjusted quota and draw, the enablement content system, and the manager cadence that catches a drifting ramp early. Not for the methodology itself (see sales-methodology) or the wider change programme (see revops-change-management).
sources:
  - "Sales ramp and enablement (MIT, Rutger Katz / Neon Triforce): ramp cost formula, ramped-equivalent capacity, ramp-adjusted quota, the evidence-gated 30-60-90 arc with three gate outcomes, enablement as a system with a call library, measuring enablement by ramp outcomes, the manager cadence"
  - "Removed as unverified: average ramp durations for SDRs and AEs, the structured-versus-unstructured multiplier, and the figures from industry compilations published without a unified method. The shape of the ramp curve is kept, and the client's own cohort figures replace them"
  - "Adapted for GTM-360: the gate timings, call-review frequency, and monthly verdict are author defaults. The ramped-equivalent example assumes a linear ramp, which should be checked against the client's data"
---

# Sales ramp and enablement

## Purpose

Ramp is the period between a rep's start date and full productivity. It is often the most expensive unmanaged cost in a go-to-market budget, because it is paid in salary and missed quota before any revenue arrives. Most companies manage it by calendar: a training week, some shadowing, and a quota that switches on at a date someone picked.

This skill treats ramp as something to measure and shorten. Each stage is passed on evidence, the capacity plan uses the ramp curve, and the manager sees problems in the first weeks rather than the sixth month.

The core rule: ramp is graduated by evidence, not elapsed time. If it is not measured, every capacity plan built on it is guesswork.

## When to use

- New reps take a long time to book their first meetings or create qualified pipeline.
- Hiring plans count heads, not productive capacity, and the pipeline target keeps missing.
- Certification is a certificate for attending training.
- A rep who was never going to succeed is discovered late.
- A new team, territory, or product is being staffed, and its ramp assumptions are unknown.

Route elsewhere when:

- The question is the methodology used in discovery. Use `sales-methodology`.
- The question is the forecast model. Use `revops-forecasting`.
- The question is the playbook content itself. Playbook foundations sit in a separate skill (`sales-playbook-foundations`).
- The question is the change programme for the whole team. Use `revops-change-management`.

## Inputs

- The last four or more hires: start date, the first meeting booked, the first qualified opportunity, the first win, and their loaded cost.
- The current onboarding plan, its training content, and its certification method.
- The quota and draw structure for new reps, and any guarantees.
- The capacity model: whether it counts heads or productive capacity.
- The call library, if one exists, and the age of its newest example.
- The manager structure, and the time managers spend on call review.

## Procedure

### Step 1: Put the ramp cost in the revenue model

Ramp cost per hire is the months to full productivity multiplied by the loaded cost plus the quota coverage the rep does not yet carry. Calculate it for the last four hires. This figure justifies the rest of the programme, so present it to finance and sales leadership.

Track the components separately:

- Months to first meeting booked.
- Months to first qualified opportunity.
- Months to first win.
- Months to full quota.

Each one points at a different fix. Slow first meetings point at prospecting and messaging. Slow qualified opportunities point at discovery. Slow wins point at deal management and the proposal.

### Step 2: Plan capacity on ramped-equivalent reps

Capacity planning should use ramped-equivalent reps, not headcount. A rep in a stage of the ramp contributes a fraction of a fully ramped rep. If the ramp is linear, a rep in month two of a five-month ramp contributes roughly 40% of a full rep. Check that assumption against the client's cohort data, since many ramps are not linear.

A plan that counts heads will show a pipeline gap that is really a ramp gap, and blame the market for it. Feed the ramped-equivalent figures into the bottom-up capacity model in `revops-forecasting`.

### Step 3: Set ramp-adjusted quotas and draw

A full quota on day one does not speed up learning. It teaches new reps to chase whatever deals are available, including poor ones, and the qualification gates then have to catch them.

Use stepped targets across the ramp. Match the draw or guarantee to the steps, so that the rep is paid for progress through the stages, not only for closed revenue. Write the steps and the triggers into the plan, and review them with the compensation design in `gtm-compensation`.

### Step 4: Build the milestone arc

A default arc for a mid-market account executive. Compress or extend it by motion, and keep the gate logic.

**By day 30, certified on the story.** The rep can run a first-call pitch and a discovery conversation to the standard, scored against the call rubric on real or role-play calls. The score comes from a reviewer, not the rep's self-assessment. The rep knows the ideal customer profile, the top reasons deals are lost (taken from the win and loss programme, not from anecdote), and the qualification bar.

**By day 60, certified on the motion.** The rep runs discovery on live calls with a manager or peer listening. The rep has created qualified opportunities that pass the evidence gates. Leading indicators are tracked from week one: time to first meeting booked, time to first qualified opportunity, and call quality scores.

**By day 90, producing with a fading scaffold.** The rep owns deals through the middle of the funnel, and has a first closed or near-closed outcome that suits the cycle length. The scaffold, meaning shadowing and call review on every call, steps down as the evidence improves.

Each gate has three outcomes:

- **Pass.** The rep moves on.
- **Targeted remediation.** A named gap, a specific plan, and a date for the re-test.
- **An honest early verdict.** If the rep is not going to reach the standard, say so while there is still time to decide.

The most expensive outcome is a rep who was never going to succeed and is found out at month nine. Gates exist to find that out at month two, when it is cheaper and kinder.

### Step 5: Run enablement as a system

- **One home.** The playbook, the call library, and the assets live in one place, with an owner and an update schedule. If there is no playbook, write one before the second week of training. Playbook foundations are covered in a separate skill.
- **The call library is the curriculum.** Keep the best recordings for each stage, examples of weak calls with commentary, and the new rep's own calls reviewed against the library. Reps learn the standard from real calls more readily than from slides.
- **Certification uses real material.** The pitch being certified is the one the best calls actually use. The objections being drilled come from the most recent top loss reasons. The ideal customer profile being memorised is the one the team scores against, not an aspirational version.
- **Measure enablement by ramp outcomes.** Completion of training is an input. Time to first qualified opportunity, by hiring cohort, is the scoreboard.

Check the age of the newest example in the call library. If the best example of a discovery call is two years old, the library is out of date.

### Step 6: Install the manager cadence

Ramp fails quietly without a manager rhythm. Set these:

- A weekly one-to-one against the milestone plan, reviewing the evidence, not impressions.
- At least two call reviews a week until day 60.
- A written monthly verdict, marked on track, in remediation, or of concern, which someone above the manager reads and signs.

A ramp plan without this cadence is a list of milestones with no one checking them.

### Step 7: Track the cohort

For each hiring cohort, plot the leading indicators against the previous cohorts: first meeting, first qualified opportunity, first win. A cohort that falls behind the curve should trigger a review of the onboarding, not only of the individual rep.

Review the cohort curve at each quarter-end. Changes to the programme should be judged against it.

## Output

- The ramp cost per hire for the last four hires, with its components.
- The ramped-equivalent capacity model, with the ramp curve used.
- The ramp-adjusted quota and draw schedule.
- The milestone gates for each stage, with the evidence required and the three possible outcomes.
- The enablement system: the playbook owner, the call library, and the certification method.
- The manager cadence and the monthly verdict template.
- The cohort dashboard, with the leading indicators.

## Diagnostic questions

1. What did the last four hires cost in ramp months multiplied by loaded cost, and who is responsible for reducing that figure?
2. Does the capacity model count heads or ramped-equivalents? Rebuild this year's plan with the ramp curve, and check whether the pipeline target still holds.
3. What evidence moves a rep out of ramp today: a date, or scored certifications? Has a gate ever failed anyone?
4. What is the time to first qualified opportunity for each hiring cohort, and is it improving?
5. Where does a new rep go to hear what a strong discovery call sounds like, and how old is the newest example there?

## Quality bar

Ramp is graduated by scored evidence at each gate. Capacity plans use ramped-equivalents. Certification is scored by a reviewer on real material. Each cohort is tracked on leading indicators, and at least one gate has failed someone early enough to matter. Watch for certificates for attendance, full quota in the second month, ramp problems found in the sixth month, and call libraries nobody has updated.

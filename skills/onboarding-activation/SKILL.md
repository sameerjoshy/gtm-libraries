---
name: onboarding-activation
version: 1.0.0
description: "Use when customers sign and then stall, go-live takes months, or the gap between signed and successful is where accounts quietly die. Defines an activation event, carries the buying evidence across the signature, drives a 30-60-90 activation arc with milestone gates, detects stalls while they are cheap, and graduates accounts into steady state with a value baseline. Onboarding ends at first realised value, not at go-live. Not for Sales-to-CS handoff mechanics (see revenue-handoffs) or CS health scoring (see cs-operations)."
---

# Onboarding to activation

## Purpose

After the signature, the customer is the least watched they will ever be. Sales has moved on, the customer success team has a kickoff template, and the champion is spending political capital on a promise nobody has yet proven. Accounts that later churn often stalled here, long before anyone said they were unhappy.

This skill turns onboarding into an activation system: one event that defines success, a clock that the customer cares about, early warning on stalls, and a graduation step that installs the baseline every later business review will use.

## When to use

- Customers sign, then go quiet, or use the product only lightly.
- Go-live takes months, and the customer's critical event passes while implementation drags.
- Kickoffs repeat what the customer already told sales.
- Accounts exit onboarding with no measure of value, so renewal conversations start from nothing.

Route elsewhere when:

- The question is how a closed deal passes to CS. Use `revenue-handoffs`.
- The question is the health score or renewal process. Use `cs-operations`.
- The question is which expansion to pursue. Use `expansion-revenue-architect`.

## Inputs

- The product's core workflows, and the one that carried the buying case.
- The buying evidence from sales: the pain, the quantified impact, and the critical event with its date.
- The signed scope, the success criteria, and the named people: champion, economic buyer, and skeptics.
- Usage data by account for the last six months, if any exists.
- The current onboarding plan, its milestones, and the time from signature to first value for recent accounts.

## Procedure

### Step 1: Define the activation event

Activation is the smallest observable event that proves the customer experienced the core value on their own data, in their own workflow.

- **Go-live is not activation.** Configured, trained, and launched are vendor milestones. Activation is a customer outcome: a report that changed a decision, a workflow that replaced the old one, the first week the legacy tool went unopened.
- Write down one primary activation event per segment or product line. It must be measurable from system data. If someone has to be asked in a meeting whether an account is activated, the definition is wrong.
- Track time to first value as a distribution, from signature to activation. Watch the slow tail, because that is where churn tends to sit. Do not report only the average.

### Step 2: Carry the evidence across the signature

Most onboarding opens with a kickoff that asks the customer to re-explain what they told sales. That wastes the first meeting and signals that nobody was listening.

Hand over, in writing, at signature:

1. **Why they bought,** in their words: the pain, the quantified impact, and the critical event with its date. If qualification ran, this is a lookup, not an interview.
2. **Success criteria and the activation definition,** inherited from the evaluation, or written at kickoff if no evaluation ran.
3. **The people map:** the champion, the economic buyer, the skeptic who nearly blocked the deal, and whoever is spending political capital on it working.
4. **The clock they care about.** The event that justified buying does not pause while legal finishes the contract.

The kickoff then confirms rather than collects. It opens with a question that resets scope honestly: "What has changed since you signed?"

### Step 3: Run the 30-60-90 activation arc

Use milestone gates. The gates matter more than the dates, so compress the arc for simple products.

- **First 30 days: one workflow live.** Narrow the rollout to the single workflow that carried the buying case, and get it producing results on real data. Broad rollouts tend to activate nothing.
- **By day 60: the activation event, witnessed.** The customer can show the value to their own manager without the vendor in the room. Measure it from system data. Do not rely on a survey.
- **By day 90: wider use, and a baseline agreed.** A second workflow or a wider group is live, and the value baseline is written down: the customer's numbers before, and their numbers after, agreed by both sides. This baseline is the reference point for every later business review and renewal case.

### Step 4: Detect stalls while they are cheap

Instrument three stall signals from day one. Each has a named response.

1. **Access stall.** An environment, data source, or integration has been blocked for more than a week. Response: escalate to the sponsor, and state the cost of delay against the customer's critical event. A polite reminder to the blocked administrator is not enough.
2. **Attendance decay.** The kickoff was full, and by session three one junior person attends. Response: have a champion conversation, asking what has changed internally. Attendance decay in onboarding is the same signal as sponsor drift before renewal, only earlier and cheaper to fix.
3. **Usage flatline after launch.** The product is live but idle for two weeks. Response: narrow the scope further, retrain on the one workflow, and reconnect with the buying pain. Do not add features to an account that has not used the first one.

A stall that survives two responses needs an honest internal verdict, which may be that the account is the wrong fit. Pushing a doomed onboarding into steady state does not save the account. It delays the churn to a later and more expensive date.

### Step 5: Graduate the account, do not let it fade out

Onboarding ends with an explicit graduation, with four conditions met:

- The activation event is verified from data.
- The value baseline is documented and agreed.
- A named owner for steady-state cadence is introduced to the customer.
- The first business review is scheduled, using the baseline as its starting point.

Accounts that leave onboarding without a baseline force every future value conversation to begin with reconstruction. Reconstruction is slow and usually weakens the case.

### Step 6: Track the onboarding metrics

Measure these by segment and track the trend:

- Time from signature to activation, as a median and a worst-decile figure.
- Share of accounts activated within 90 days.
- Share of accounts with a documented baseline at graduation.
- Count of stalls by type, and the time each took to resolve.
- Share of kickoffs that open by reading back the customer's stated goal.

Targets come from the client's baseline. A useful internal test: if you can list which accounts signed in the last 90 days and have not activated, in seconds, from a single view, the system is working.

### Step 7: Test the link to retention on the client's own data

The idea that activation drives renewal is plausible, and it should be tested rather than assumed. Within two quarters, split renewal outcomes by activated and not activated. If the split is weak, the activation definition is measuring the wrong thing, and the arc needs changing.

## Output

- The activation definition for each segment, in one sentence, with its data source.
- The evidence handover template, filled for the current pipeline.
- The 30-60-90 gate plan, with the owner for each gate.
- The stall signals, their thresholds, and the response owner for each.
- The graduation checklist.
- The metric definitions and the first baseline.

## Diagnostic questions

1. What is your activation event in one sentence, per segment? If the answer is a paragraph of milestones, you have a phase, not an event.
2. What is the median time to first value, and what does the worst tenth look like? Who owns that tail?
3. Open your three most recent kickoffs. Did the customer repeat what they told sales, or did you read it back to them?
4. Which accounts in onboarding now show an access stall or attendance decay, and who is acting on each this week?
5. Of the accounts that churned in the last year, how many ever activated? The answer often changes the churn conversation.

## Quality bar

Activation is an event measured from data, not a milestone a vendor ticks off. The buying evidence is carried across the signature. Stalls are detected within two weeks and escalated with a named owner. Every account graduates with a documented baseline. Watch for go-live counted as success, kickoffs that re-ask for information already given, and accounts moved to steady state while still stalled.

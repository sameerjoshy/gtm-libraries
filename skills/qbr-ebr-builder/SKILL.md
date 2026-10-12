---
name: qbr-ebr-builder
version: 1.1.0
description: "Use to design and build customer business reviews that buyers attend: the quarterly operational review for users and the executive business review for the economic buyer, with the value recap in the customer's own numbers as the central artefact. Includes a pre-meeting executive account brief for the seller. Use when reviews are a feature parade, when the economic buyer has stopped attending, when renewal value has to be proved from scratch, or before a sponsor sync. Not for internal meeting design (see revenue-operating-cadence) or for the intervention itself when a review finds risk (see renewal-save-motion)."
---

# QBR and EBR builder

## Purpose

Most business reviews fail the same way. A feature parade is presented to the daily users, while the economic buyer, the person who will decide the renewal, has stopped attending. When renewal season arrives, the value case is built in a panic, for an audience that has not heard it all year.

A business review has one job: keep the people who pay convinced of the value, in their own numbers, on a regular rhythm. Then the renewal is a formality and the expansion conversation has a natural place to happen.

Entry condition: an internal health read already exists, from `cs-operations` or an account health check. A review built without one presents to the customer something the company has not verified itself.

## When to use

- Reviews are slide decks about features and roadmap, with little on outcomes.
- The economic buyer has not attended a review in the last two quarters.
- A renewal is within 120 days, and the value case has not been built.
- A customer has stopped attending reviews.
- A seller needs a one-page brief before a sponsor sync or a review.

Route elsewhere when:

- A review surfaces risk that needs an intervention. Hand off to `renewal-save-motion`.
- A review surfaces headroom for expansion. Hand off to `expansion-revenue-architect`.
- The question is the company's own internal meeting design. Use `revenue-operating-cadence`.

## Inputs

- The account's contract value, renewal date, and segment.
- The customer's agreed success baseline, from onboarding or the last review. If none exists, that is the first finding.
- The customer's own system data: usage, outcomes measured in their terms, and tickets.
- The contacts: the economic buyer, the executive sponsor, the program owner, and the daily users, with attendance history for each.
- The most recent internal health read for the account.
- The open actions from the last review, and whether the customer completed them.

## Procedure

### Step 1: Choose the instrument

Two instruments, not one blended review.

| | Quarterly review (operational) | Executive business review (executive) |
|---|---|---|
| Audience | Daily users and the program owner | Economic buyer and executive sponsor |
| Rhythm | Quarterly, or asynchronous for smaller accounts | One or two a year, timed 90 to 120 days before renewal |
| Question | Is the product working, and used well? | Was it worth the money, and what should it do next? |
| Center of gravity | Adoption, blockers, and the roadmap of use | Value recap in their numbers, strategic alignment, and the roadmap of outcomes |
| Typical failure | A feature parade | Skipping it because "the users are happy" |

The executive review is timed before the renewal because, by the time a renewal conversation starts, an unengaged economic buyer has already formed a view from hallway talk. The executive review is where that view is formed deliberately.

### Step 2: Segment the effort

Review effort is a budget. Spend it where revenue concentrates. Defaults to calibrate:

- **Top tier** (the largest contracts, the clearest expansion headroom, the strategic logos): a quarterly review plus one or two executive reviews a year, held live.
- **Middle tier**: a semi-annual review. An executive review is held only when a trigger fires: renewal within 120 days, a risk flag, an expansion signal, or a change of sponsor.
- **Long tail**: no live reviews. A quarterly one-page value summary replaces the meeting. It is assembled from usage and outcome data and reviewed by a person before it is sent.

Assembling review material used to be the expensive part, which justified skipping reviews for smaller accounts. Automated assembly of the data pack moves the constraint to the customer's attention, not to the company's capacity. Spend the freed capacity on better top-tier meetings, not on more meetings everywhere.

### Step 3: Build the three panels

Every review, quarterly or executive, follows the same spine. The depth differs by audience.

**Panel 1: look back, in their numbers.** This is the central artefact. Its rules:
- Build it from the customer's own system data, against a baseline agreed at onboarding or at the previous review. If no baseline exists, installing one is the first review's job.
- Report outcomes, not activity. "Cut manual reconciliation time by a stated amount since March" lands better than "487 workflows run."
- Include what did not improve. One acknowledged miss makes every claimed win believable. A review with no misses reads as marketing.
- If the value recap cannot be built, that is a finding, not a formatting problem. Either instrumentation is missing, which needs fixing, or value is absent, which needs the save motion now rather than at renewal.
- Report value, not usage or performance. Tasks run and uptime keep the product running, but only value figures carry a renewal. If the data is usage-shaped, convert it before use.
- Take the "before" figure from the customer: the time or cost of each task before the product, and the rate the customer uses for the people who did the work. Use the units the customer already tracks. Where no benchmark was ever agreed, capture one now and label it as a new assumption.
- Show the arithmetic: tasks resolved, the human-equivalent time they replace, the cost avoided, and the multiple of value to price. A buyer who can re-derive the number will defend it internally.
- Compute value per account. Averages across accounts hide large differences in value.
- Where value is measurable, a monthly one-page receipt is cheaper than a renewal scramble. Do not lead with the count of tasks completed alone. Activity is not value.

**Panel 2: current state, honestly.** Adoption depth against plan, open issues with owners and dates, and a plain health verdict. Do not turn the internal health read into a greener version for the customer. Experienced buyers keep their own scorecard. The gap between the company's view and theirs is lost trust.

**Panel 3: look forward, jointly owned.** The next quarter's success plan, with the customer's name on about half the actions. Each action has a goal, an owner, a date, and the one measure the next review will be judged on. A review that ends with no customer-owned actions was a presentation, not a review. Expansion surfaces naturally here, as unmet goals and adjacent problems raised as the customer's roadmap, not as the company's quota.

### Step 4: Apply the stakeholder rules

- **The economic buyer attends the executive review, or the review moves.** A review without them is a rehearsal. Getting them there is the sponsor's job, agreed in the success plan, not a calendar surprise.
- **Treat attendance drift as a signal.** A sponsor who attended two reviews and skipped the third has told you something the health read has not yet caught. Feed it to risk triage.
- **A new stakeholder restarts the relationship at their starting point.** After a reorganization or a new executive, run a compressed look-back, and do not assume they carry any of the prior context.

### Step 5: Prepare the executive account brief

Before any sponsor sync or executive review, the seller prepares a one-page brief. It is for the seller's preparation, not for the customer. It is the most useful single page in account management, because it forces facts before narrative.

Structure, in order:

```
ACCOUNT:       Company, industry, size, stage
OPPORTUNITY:   Contract or deal name, value, stage, target date
OWNER:         The seller's name

THE PICTURE (three sentences)
  What they are trying to do, why now, why us.

BUYING COMMITTEE
  Name, title, sentiment in one word, with the quote or behavior behind it.
  Sentiment is never stated without a quote or a specific behavior.

WHERE WE ARE (three to five bullets)
  The last meaningful contact and its outcome.
  The commitment still open, whether ours or theirs.
  The step currently holding things up.

RISKS (three to five, each sourced)
  Risk, then the source: "raised by the CFO on the March call."
  Stakeholder, commercial, competitive, and execution risks are the four categories.

ASKS
  What the seller needs from the executive: air cover, an introduction,
  an approval, or a sponsor on a call. Be specific. A brief without an
  ask is a status update.
```

Rules for the brief:
- If a section has nothing real to say, write "no current risk" or "no stakeholder issue." Do not invent content to fill it.
- If the deal record is stale, say so as a finding. For example: "The CRM stage says proposal, but the last call suggests the budget is not yet approved."
- Read it back once before use. Cut or sharpen every line that is vague, generic, or unsourced.
- For a shorter pre-call prep, use a short version of the brief rather than the full page.

When the brief is shared beyond the seller, show contact names as initials and do not include private contact details. The full record stays in the CRM.

### Step 6: Route the outputs

A review is upstream instrumentation for the rest of the post-sale system. Every review produces:

1. An updated success plan (panel 3), dated and shared with the customer.
2. A refreshed baseline for the next value recap.
3. Routed flags: risk signals to the save motion, expansion signals to the expansion motion, and product blockers to the product team, with a feedback loop the customer can see.
4. A one-paragraph internal verdict on the account: trajectory, sponsor state, and one thing to fix before the next review.

## Anti-patterns

- **The feature parade.** Roadmap-heavy decks answer a question nobody asked. The roadmap earns about ten minutes in panel 3, framed by the customer's goals.
- **The survey score as proof.** A satisfaction score is not a value recap. Scores decorate; outcomes persuade.
- **The annual ambush.** The first value conversation happening at renewal is the most expensive scheduling failure in account management. The executive review ahead of renewal exists to make the renewal uneventful.
- **The unchanged deck.** If the review could be last quarter's deck with new dates, cancel it and send the one-page summary. Customer attention is being spent on no news.
- **The solo review.** The vendor presents and the customer receives. A jointly built agenda, with panel 1 sent in advance and the customer asked what they want challenged, is itself a signal of engagement. An account that will not help shape the agenda is telling you where you stand.

## Output

- The instrument and the audience for each review, and the tier of the account.
- The value recap, with the baseline it is measured against and the misses it acknowledges.
- The current-state verdict, shared plainly.
- The success plan for the next period, with customer-owned actions, owners, and dates.
- The executive account brief, if a sponsor sync or executive review is planned.
- The routed flags and the internal verdict.

## Diagnostic questions

1. For the top ten accounts, when did the economic buyer last hear the value case from the company, in their own numbers?
2. Can the company produce a value recap, against an agreed baseline, for the largest renewal due in the next two quarters, without a data search project?
3. What share of the last quarter's reviews ended with customer-owned actions that were completed?
4. Which sponsors stopped attending reviews in the last year, and what happened at their renewals?
5. How many hours does one review pack take to assemble, and is that why the long tail gets no reviews?

## Quality bar

The economic buyer is in the executive review, or the review has moved. The value recap is in the customer's numbers, against an agreed baseline, and admits at least one miss. Every review ends with customer-owned actions. The internal verdict and the customer-facing verdict match. Watch for feature parades, scores presented as value, executive reviews without the buyer, and briefs with sentiment but no quotes.

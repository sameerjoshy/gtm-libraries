---
name: deal-desk-operations
version: 1.0.0
status: draft-for-review
description: Use when reps hold too much pricing authority, discounts vary widely by region or rep, approvals stall deals, or margin is leaking without anyone seeing it. Designs the discount approval matrix by depth and deal size, a margin floor, a strategic exception lane with a 30-day review, a three-stage quote workflow with turnaround targets, discount tracking with expiry, governance of usage and outcome deals, and the metrics that show whether the desk is helping or slowing deals. Not for list pricing or packaging strategy (see pricing-monetisation-ops) or renewal positioning (see cs-operations).
sources:
  - "Deal desk operations (MIT, Rutger Katz / Neon Triforce): triggers for building a desk, discount authority bands, margin floor, deal-size overrides, strategic value lane, three-stage quote workflow, discount tracking requirements, renewal cohorts, expiry enforcement, usage and outcome deal governance, metrics, maturity levels, anti-patterns"
  - "Removed as unverified or vendor-sourced: margin-leakage percentages, cycle-time reduction claims, the cost of each hour of quote delay, the quote-turnaround benchmark attributed to a vendor, usage-based adoption trends, and the vendor and survey figures. Targets are kept as defaults to test"
  - "Corrected: the source's Netherlands cold-email exception is removed. Member-state rules on unsolicited electronic marketing vary and are a point for counsel"
  - "Adapted for GTM-360: bands, SLAs, scoring scales and metric targets are author defaults. Calibrate them against the client's own margin and win data"
---

# Deal desk operations

## Purpose

A deal desk is the control between a sales team's need to close and the company's need to protect margin and precedent. Without one, discounts depend on who asks whom, approvals wait in inboxes, and nobody can say what was given away. With one that is badly designed, every deal waits for a committee.

The job is to make approvals fast for normal deals, rigorous for unusual ones, and visible for all of them.

## When to use

- Reps have discount authority that nobody has written down.
- Discounts vary sharply by region, rep, or tenure.
- Deals sit waiting for pricing or contract approval.
- Margin erosion is suspected but not measured.
- Usage, outcome-based, or multi-year deals are becoming common and nobody owns their economics.

Do not build a deal desk on day one. It earns its place when deal complexity, discount variance, or approval queues justify it. For a small team with consistent deals, a written discount policy and a single approver may be enough.

Route elsewhere when:

- The question is the list price or packaging. Use `pricing-monetisation-ops`.
- The question is billing, metering, or revenue recognition. Use `pricing-monetisation-ops`.
- The question is renewal price positioning. Use `cs-operations`.
- The question is the strategic exception as a sales decision on a single deal. Use `deal-qualification-gates` to test the case.

## Inputs

- The current discount history: depth, deal size, region, rep, and reason, for the last 12 months if available.
- The contribution margin by product and deal type, and the margin floor the company accepts.
- The approval roles that exist today, and who signs what.
- The quote tool, if there is one, and its current workflow.
- Average deal size, sales cycle length, and win rate by segment.
- Any open disputes or recent pricing exceptions, and how they were decided.

## Procedure

### Step 1: Confirm the desk is needed

Build a desk when at least one of these holds:

- Custom structures, such as outcome-based pricing, consumption models, non-standard terms, or step-up contracts, are becoming common.
- Reps have too much discretion, and discounts cluster unpredictably.
- Margin leakage is visible in the numbers, or the finance lead cannot say how much discount was given.
- Quote turnaround is stretching past one to two working days.
- The team is large enough that "ask the CRO" no longer works. A common threshold is around fifteen account executives, but use the client's own queue data.

The test: when leadership asks how much is being left on the table, can anyone answer from data? If not, the desk is overdue.

### Step 2: Build the approval matrix

The matrix sets the authority for each discount depth, adjusted for deal size. Default bands, to calibrate against the client's data:

| Discount depth | Approver | Turnaround target | What the approver must have |
|---|---|---|---|
| 0 to 10% | Rep, within policy | None needed | Nothing beyond the policy |
| 10 to 20% | Sales manager, with a deal desk check | 4 to 8 hours | The margin impact on the deal |
| 20 to 30% | Regional sales leader and deal desk lead | 8 to 12 hours | A written reason |
| Above 30% | Chief revenue officer and finance, with a written strategic case | Up to 24 hours | The precedent effect and the margin floor position |

**Margin floor.** No deal below the target contribution margin is approved at any level. A deal that breaches the floor even with every approval goes to finance and the leadership team as an explicit, rare exception, logged separately.

**Deal-size overrides.** For large deals, the thresholds tighten. For example, a discount above 15% on a large strategic account may go straight to a senior leader. For small deals, packaged bundles may approve automatically within set limits.

**Simplicity.** Keep the matrix to four tiers at most: rep, manager, director, and executive. A matrix with ten tiers means reps spend hours finding the right approver, and decisions stall.

The rule that tests the matrix: if a person can approve a discount without knowing its effect on margin, the matrix is too loose.

### Step 3: Run the strategic exception lane

Some deals fail the discount gate but carry strategic weight, such as a new logo in a target segment, a reference account, or a beachhead for expansion. Without a separate lane, reps label every large discount as strategic, and the matrix stops working.

The lane:

1. The rep flags the deal as a strategic exception, with a short written rationale.
2. The desk scores its strategic value on a one-to-five scale, covering whether it opens a target segment, whether it creates a reference, and whether it is a beachhead for expansion.
3. A score of three or more goes to the senior sales leader, with the full financial effect and the strategic case.
4. Approval, and its rationale, is recorded on the deal.
5. Every thirty days, review each exception. Did it produce what the strategy said it would?

The lane separates genuine strategic cases from routine pressure, and makes the strategy testable.

### Step 4: Run the three-stage quote workflow

A quote is a commercial commitment. A slow quote loses deals, and a careless one causes disputes after signature.

**Stage 1, intake and validation (within two hours).** The rep submits the quote with structured fields: account, contract value, discount, whether terms are non-standard, and whether renewal terms are standard or custom. The desk checks that the deal clears the margin floor, that the fields are complete, and that the discount sits within normal bands for the segment. Standard quotes route automatically. Non-standard quotes go to a desk analyst, who pulls the account's discount history, renewal risk, and lifetime value.

**Stage 2, approval routing (two to eight hours for standard, four to twenty-four for non-standard).** Standard quotes within the first band approve automatically. Non-standard quotes route to the approver in the matrix. The approver reviews the discount depth, the strategic fit, the precedent (is this the third deal at the same discount in this vertical?), and the implementation complexity, since a complex deal with a deep discount squeezes margin twice. If legal review is needed for new terms, security requirements, or data residency, it runs in parallel, with a turnaround target of one to two days and escalation on a miss.

**Stage 3, delivery and signature (within eight to twenty-four hours).** The final quote goes to the customer within two hours of the last approval. Set a signature window, typically around 72 hours, and a shorter window for fast-moving deals.

**Turnaround targets, as defaults:**

- Standard quote: four to six hours from request to approval.
- Non-standard quote: twelve to twenty-four hours.
- Legal or pricing-heavy quote, such as outcome-based or multi-year: twenty-four to forty-eight hours.
- At least 80% of quotes within target, measured on a trailing 30-day average.

Measure where the time goes. In most desks, the time sits in waiting for an approver, not in the review itself.

### Step 5: Track every discount

Every approved discount carries:

- **Reason**, from a fixed list: competitive, loss aversion, strategic, volume, or loyalty.
- **Expiry**: one-time for this deal, automatic renewal, or expiry on a set date. Most discounts should expire.
- **Precedent flag**: is this the first time this discount has been offered to this industry, region, or company size?
- **Renewal behaviour**: returns to list price, renegotiated, or held over, with the decision recorded.

Most margin leakage comes from four sources: discounts that were never approved or documented, concessions forgotten at renewal, annual discounts treated as permanent, and prices agreed in a sales call that never reached the record. The expiry field and the renewal check address the first three. Reconcile the CRM against the signed contracts each quarter to catch the fourth.

Leakage is measured, not assumed. Compare the discount in the signed contract with the discount in the approval record, and report the gap.

### Step 6: Manage renewal uplifts by cohort

Price increases at renewal fail when they are not planned. Plan them by cohort, starting at least 120 days before renewal.

1. **Segment the base.** High value and low churn risk: defend and grow. Mid value and normal risk: optimise and hold. High risk and lower value: selective increase, or prune.
2. **Set an increase by cohort.** Default ranges to calibrate: the defended cohort may take a larger increase, the middle cohort a moderate one, and the at-risk cohort a small one or none.
3. **Record the rationale.** Which cohort, which tier, why, and who approved the strategy. A chief revenue officer and a finance lead should co-sign it.
4. **Track the hold rate by cohort.** If the defended cohort shows churn on the first contact, the strategy needs changing.

Renewal behaviour for each discount follows Step 5. An expired discount renews at list price unless someone decides otherwise and records it.

### Step 7: Govern usage-based and outcome-based deals

**Usage-based deals.** These need desk review before the proposal. Govern five elements:

- The minimum commitment: set it to cover acquisition and onboarding cost, or label the deal as a land-and-expand play.
- The overage rate: price it to hold the gross margin target. If it does not, the deal is a loss leader and needs a written reason.
- The usage tracking method: the customer should be able to see usage and audit it monthly.
- The billing cadence: monthly or quarterly, with true-up language if quarterly.
- The true-up rule: how over- and under-use is settled at year end.

Check the customer's prior usage. If it runs well above the minimum commitment, renegotiate the commitment before signing.

**Outcome-based deals.** These link revenue to a customer result. Before signing, confirm:

- The success measure can be observed, and an independent party can audit it, not only the seller's view of success.
- The baseline is documented, from data gathered before the solution starts.
- The payout schedule is explicit: whether there is a retainer, when the outcome bonus is triggered, and how it is paid.
- The dispute process is named, including who settles a disagreement about how the measure was calculated.
- The contract has term and exit clauses for the case where the customer leaves before outcomes are proven.

Approval for outcome-based deals needs the chief revenue officer, finance, and sales operations together. These deals need ongoing management after signature.

**Multi-year contracts with step-ups.** Tie each step-up to a usage or performance trigger, not an arbitrary date. Consider a freeze option, where the customer holds the prior year's price for one year in return for a renewal commitment. Schedule a mid-contract health check before the step-up, so that a deteriorating relationship is found before the renewal.

### Step 8: Measure the desk

Three dimensions: velocity, quality, and compliance. Default targets, to calibrate:

**Velocity:**

- Standard quote approval within four to six hours.
- Non-standard quote approval within twelve to twenty-four hours.
- At least 80% of quotes within target.
- Deal velocity, calculated as opportunities times win rate times average deal size, divided by sales cycle length, rising month on month.

**Quality:**

- Untracked discount concessions below 2% of contract value.
- Gross margin on desk-reviewed deals at or above target.
- Win rate on desk-reviewed deals at or above the rate for deals not reviewed. If it falls, the desk is slowing deals or making them worse.
- Renewal hold rate on custom-priced deals at or above the cohort baseline.

**Compliance:**

- 100% of discounts with a documented reason.
- 100% of discounts with an explicit expiry.
- 100% of strategic exceptions with a recorded outcome.
- Exception volume, meaning discounts above the approval threshold, at or below about 5% of quarterly bookings. A rising trend means either the matrix is too strict or reps are discounting more. A falling trend may mean discounts are being hidden, so audit a sample.

Review velocity and compliance weekly. Review quality and strategic exceptions monthly.

### Step 9: Move through the maturity levels

**Level 1, ad hoc.** Reps ask the chief revenue officer. Discounts are undocumented. Legal reviews are slow and unpredictable. Symptoms: wide variance by rep, churn on discounted renewals, and no one can say how much was discounted.

Move to Level 2 by naming a desk lead or assigning the work to revenue operations, auditing existing discounts for thirty to sixty days, and installing a three-tier matrix. Use the quote tool the company already has, or set one up in the CRM. For Salesforce, see `revops-salesforce`.

**Level 2, formalised.** The matrix is documented. Quote turnaround targets are set and tracked. The desk reviews most deals above a set discount. Legal has a named process. Gaps: limited data on discount patterns, reactive renewal pricing, and usage and outcome deals handled one at a time.

Move to Level 3 by building a discount dashboard, a cohort-based renewal strategy, and standard templates for usage deals, and by reporting the quality metrics each month with finance.

**Level 3, strategic.** The desk is cross-functional, with revenue operations, sales, finance, and product involved. Usage and outcome deals have playbooks. Renewals are planned 120 or more days ahead. The desk feeds insight back into pricing, for example by showing that one segment is consistently discounted and the list price should move.

Level 3 usually takes twelve to twenty-four months of building, as volume and complexity justify it. Do not aim for it before the basics are in place.

**Sequence for the first year:**

- Quarter one: formalise the matrix, document the existing discounts, and set up the quote workflow.
- Quarter two: enforce discount tracking and expiry, and start the weekly velocity review.
- Quarter three: build the renewal cohort strategy, and set the governance rhythm: weekly velocity review, monthly deep dive.
- Quarter four: add the quality and strategic exception metrics, and tie the desk to the monthly finance close.

### Step 10: Apply the data protection points

Enrichment used to set pricing or renewal terms may be subject to the notice obligations under GDPR Article 14. Document the sources, and decide whether customers must be told, with counsel.

Pricing conversations by email or social media should not include discounts or special terms before the terms are agreed in the contract process. Rules on unsolicited electronic marketing vary by member state, so confirm them with counsel.

Contracts with EU customers should say which data is used for pricing and renewal decisions, the customer's right to object under Article 21, and how a customer can dispute a price increase based on inaccurate data.

## Output

- The approval matrix with its bands, turnaround targets, and deal-size overrides.
- The margin floor, and the rule for breaches.
- The strategic exception lane, with its scoring scale and its thirty-day review.
- The three-stage quote workflow, with owners and targets.
- The discount tracking fields and the expiry enforcement rule.
- The renewal cohort plan, with its rationale and sign-off.
- The governance rules for usage, outcome, and multi-year deals.
- The metrics dashboard, with weekly and monthly reviews.
- The maturity level today, and the next step.

## Anti-patterns

| Anti-pattern | Symptom | Fix |
|---|---|---|
| Ten approval tiers | Reps hunt for the approver, and decisions stall | Four tiers at most |
| No expiry on discounts | Discounts persist into renewal and erode margin | Mandatory expiry, audited each quarter |
| Desk judged on speed alone | Deals move faster and margin leaks | Measure margin and win rate alongside turnaround |
| Reps hiding discounts | Reported discounts are well below actual | Make the desk a facilitator, and recognise clean deals |
| Strategic label on everything | The exception lane becomes the default route | Score every exception and review it at thirty days |
| Vague outcome measures | Disputes at payout, and churn | Auditable measures, a baseline, and a named dispute process |
| Aggressive step-ups with no trigger | The customer hits a cap and churns at the next renewal | Tie step-ups to usage or performance, and check in mid-contract |

## Quality bar

Discount authority is written down, and every person can name their own limit. Each approval shows its margin effect at the point of decision. Quotes clear each stage within its target, and exceptions carry a written reason. Expiry is recorded on every discount, and the contract is reconciled to the approval record. Watch for approvals without margin information, strategic labels used by default, discounts with no expiry, and a desk that is faster but less profitable.

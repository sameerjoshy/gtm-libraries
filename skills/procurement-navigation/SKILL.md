---
name: procurement-navigation
version: 1.0.0
status: draft-for-review
description: Use when a verbally won deal enters security review, legal redlines, privacy terms, or vendor onboarding, and the close date keeps slipping at contract stage. Maps the buyer's gauntlet before the proposal, pre-builds the artifact pack for security, legal, and privacy, runs the reviews in parallel on a mutual close plan, and negotiates with procurement by trading concessions rather than giving them. Not for qualification (see sales-methodology) or discount approval (see deal-desk-operations).
sources:
  - "Procurement and security review navigation (MIT, Rutger Katz / Neon Triforce): mapping the gauntlet early, the standing artifact pack with owners and review dates, the mutual close plan, escalation through the sponsor, trading concessions, logging gauntlet duration by step"
  - "Removed as unverified: the win-rate figures by days to close and the benchmark attributed to a 2025 industry report. The point that long cycles hurt is kept as a hypothesis to measure on the client's own deals"
  - "Corrected: the source presents a contract-stage concession as 'unearned' without a test. This skill frames it as a trade, governed by the deal desk. Data-protection terms are flagged for counsel"
  - "Adapted for GTM-360: response-time targets and the artifact list are defaults to calibrate with the client's security and legal teams"
---

# Procurement navigation

## Purpose

A deal the sales team has won can still be lost in contracting. Security questionnaires, privacy terms, redlines, and vendor onboarding run slowly and in sequence, the close date rolls forward, and the champion's momentum fades. Most of that delay is predictable and can be scheduled before the proposal goes out.

The core rule: map the gauntlet before the proposal, start the reviews in parallel, and run them on a plan the buyer shares. Nothing in the gauntlet should come as a surprise, because every step is known.

## When to use

- A verbal yes has turned into security review, legal redlines, or onboarding paperwork.
- The close date has moved more than once at contract stage.
- Security questionnaires take weeks to answer, and the answers are assembled from scratch each time.
- Legal redlines go round several times, and each round involves a committee.
- A buyer asks for a data processing agreement, data residency terms, or a sub-processor list.

Route elsewhere when:

- The question is whether the deal is qualified. Use `sales-methodology`.
- The question is the discount to offer. Use `deal-desk-operations`.
- The question is the evaluation before the win. Use `trial-poc-conversion`.
- The question is the pricing model. Use `pricing-monetisation-ops`.

## Inputs

- The current deal, its stage, the expected signature date, and the buyer's go-live date.
- The buyer's known decision steps, and the people who run each one.
- The company's existing security and privacy documents, and their current state.
- The standard contract, its fallback positions, and the clauses that are usually negotiated.
- The history of recent contracting cycles: which steps took longest, and why.

## Procedure

### Step 1: Map the gauntlet before the proposal

Build a checklist with the champion, during discovery or at the start of the proposal. Ask:

1. Every step between yes and signature, in the buyer's order: security review, privacy and data processing terms, legal, procurement negotiation, vendor onboarding, and the signature chain.
2. For each step: who runs it, roughly how long it takes, what they need from the vendor, and what has delayed vendors there before. Champions usually answer this readily, because they want the deal to land.
3. Which steps can run in parallel, and which are true dependencies. Most are parallel. Buyers often run them in sequence out of habit, and a champion with a parallel plan can push for it internally.
4. Calendar constraints: fiscal year-end, holiday freezes, the legal team's known backlog, and signer availability. A signature chain in a holiday month can lose weeks before it starts.

If the champion cannot answer these questions, the decision-process score in qualification has fallen. Learn that now, not in week five of a legal review.

### Step 2: Build the artifact pack

Most contracting delay comes from the vendor assembling the same answers again. Keep a standing pack, with an owner and a review date for each item.

**Security:**

- Completed standard questionnaires in the common industry formats.
- Current certifications and audit reports, shareable under a non-disclosure agreement.
- An architecture and data-flow summary.
- The sub-processor list, with locations.
- An incident response summary.

**Legal and privacy:**

- The company's standard agreement and data processing agreement.
- The company's position on the clauses that are always negotiated: liability caps, indemnities, data terms, termination, and service levels.
- For each of those clauses, a fallback position agreed with counsel in advance. Then each redline round takes days, not committee cycles.

**Commercial and administrative:**

- Insurance certificates, tax and bank forms, and the vendor onboarding basics that large buyers request.

Track the response time to security questionnaires as a measure during this phase. Answers within days show a company that is easy to buy from. A three-week scramble tells the buyer's security team there is a risk, and that team's job is to look for risk.

### Step 3: Run the reviews in parallel on a mutual plan

Turn the gauntlet map into a dated plan that the buyer co-owns. Each step has an owner on each side, a due date, and the go-live date the buyer wants, at the top. When something slips, frame the impact in the buyer's cost: a delayed go-live means a delayed benefit, not a late quota for the vendor.

Review the plan weekly with the champion. Two rules keep it honest:

- A deal in the gauntlet is not forecast as committed until every remaining step is listed with an owner and a date. "In legal" is not a status. "Redlines returned, our counsel responds Thursday, one clause open" is.
- When a step stalls, escalate through the sponsor, and state the cost of delay against the buyer's go-live. Spend executive-level attention on real blockages only. One well-aimed call with a clear cost usually does more than several check-ins.

### Step 4: Negotiate with procurement without losing the deal

Procurement's mandate is savings and reduced risk. Respect that, and do not reopen the value the champion already sold.

- **Anchor on the business case.** Refer back to the numbers from the evaluation or discovery. Procurement can negotiate a percentage, but a documented business case is harder to dismiss.
- **Trade every concession.** Term length, case study or reference rights, expansion options, payment terms, and reference calls can all be traded for price or terms. A concession given for nothing at this stage tends to be repeated at the next renewal, and it teaches the buyer that the first number is negotiable.
- **Hold the walk-away line.** Set it before this phase begins, and stick to it. Let procurement win something visible that costs little. The analyst has a scorecard too.

Concession limits and approval belong to the deal desk. Check `deal-desk-operations` before offering any price change at contract stage.

### Step 5: Handle data protection terms

Data processing agreements, sub-processor lists, transfer mechanisms, and data residency commitments often sit on the critical path.

- Check the standard data processing agreement against the buyer's requirements before the redline starts, and list the differences.
- Keep the sub-processor list current, and tell the buyer how changes are notified.
- Where data leaves the buyer's jurisdiction, document the transfer mechanism and any supplementary measures. Have counsel confirm the position before it is offered.
- Do not promise a residency or certification the company does not hold.

These are points for counsel to confirm, not legal advice.

### Step 6: Log the gauntlet for the next deal

For each deal, record:

- The duration of each step, and the total from verbal yes to signature.
- Which artifacts were missing or out of date.
- Which clauses took the most rounds, and what was finally agreed.
- Where the plan slipped, and why.

After five or so deals, the artifact pack and fallback positions should cover most of what buyers ask. Until then, each deal teaches the team something it can reuse.

## Output

- The gauntlet map for the deal, with owners, durations, and parallel and serial steps.
- The mutual close plan, shared with the champion, with the buyer's go-live date at the top.
- The artifact pack checklist, with an owner and a review date for each item.
- The fallback positions for the clauses that are usually negotiated, agreed with counsel.
- The concession log, showing what was traded for what.
- The post-deal record that feeds the next cycle.

## Diagnostic questions

1. For the current late-stage deals, can anyone list the remaining steps to signature, with owners and dates? Which ones are guesses?
2. How long did the security review take on the last three enterprise deals, and how much of that time was the company's own response time?
3. Are the fallback positions for each standard clause written down and agreed in advance, or does each redline round need a committee?
4. What was conceded at contract stage last year without anything being traded for it?
5. Which calendar constraints, such as fiscal close, freezes, or signer availability, sit inside this quarter's committed deals, and has anyone checked?

## Quality bar

The gauntlet is mapped before the proposal is sent, and each step has an owner and a date. The artifact pack is current, and security answers are returned in days, not weeks. Concessions are traded, and the walk-away line holds. Watch for a verbal yes treated as the finish line, deals forecast as committed with steps still unlisted, close dates that roll each week, and a late discount paid just to end the process.

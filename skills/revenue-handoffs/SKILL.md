---
name: revenue-handoffs
version: 1.0.0
status: draft-for-review
description: "Use when revenue leaks between teams: leads go dark after handover to sales, promises made before signature disappear, implementation loses momentum, or nobody owns expansion. Designs the handoff protocol for each transition in the revenue bow tie (marketing to sales, sales to implementation, implementation to customer success, customer success back to sales), with an owner, a context packet, an SLA, and leading indicators for each. Not for routing rules (see lead-routing-design) or for tool build-out."
sources:
  - "Design revenue handoffs (MIT, Rutger Katz / Neon Triforce), five-node bow tie, context packet per transition, SLA targets and speed-to-lead tiers, promise and commitment log, go-live readiness conditions, three expansion types with the new-buying-group test, ownership thresholds by contract value, leading indicators of failure, quality scorecard"
  - "Speed-to-lead and expansion figures cited in the source are from vendor and research reports, labelled as context only and not used as rules"
  - "Adapted for GTM-360: tool names, prices, and platform build steps removed; the reference files named in the source are not in this library and are not relied on; contract-value thresholds labelled as examples to set per client"
---

# Revenue handoffs

## Purpose

Revenue leaks where one team hands work to another. A lead goes quiet after it is passed to sales. A promise made during the sale is not known to the people delivering it. An expansion signal stays with the customer success manager, because nobody has been told to act on it. Each transition needs a named owner, a context packet the receiving team actually reads, a time target, and a signal that shows when it is failing.

## When to use

- Leads are unworked, or go dark after handover.
- Customers say the delivery team did not know what was promised.
- Momentum drops between signature and go-live.
- Customer success never hears about expansion, or sales never hears about risk.
- A new handoff process is being designed, or an old one is being audited.

Route elsewhere when:

- The question is which rep gets which lead. Use `lead-routing-design`.
- The question is how to score a lead. Use `marketing-operations`.
- The question is how to build the handoff in a specific CRM. Use `revops-salesforce` for Salesforce, or `revops-tech-stack` for other CRMs.

## Inputs

- The revenue process as it runs today, with each team and each step.
- The deal stages and the fields that record the deal, including the qualification method in use.
- Speed-to-lead and response-time data, if any exists.
- Contract value bands, to set the ownership model.
- The customer segments, and which ones use implementation partners.
- Any handoff complaints from the teams involved.

## Procedure

### Step 1: Map the bow tie

Most B2B companies have four transitions. Those with implementation partners have five:

```
Marketing -> Sales -> Partner or implementation -> Customer success -> Sales (expansion)
                                                          ^
               Lifecycle marketing and account-based loops feed back here
```

Each transition has five parts:

- **Owner:** one named role accountable for the handoff.
- **Context packet:** what must transfer.
- **SLA:** the time target and the quality target.
- **Trigger:** the event that starts the handoff.
- **Measure:** how you will know it is working.

Start the audit at the transition that loses the most revenue, not the most visible one.

### Step 2: Marketing to sales

This is the most studied transition and the most often broken.

Response targets by lead type, as starting points:

| Lead type | First response |
|---|---|
| Hand-raisers, such as a demo or pricing request | Under 5 minutes |
| Paid ads | Under 3 minutes |
| Partner referral | Under 30 minutes |
| Organic inbound | Under 10 minutes |
| Content or webinar | 3 to 4 days, with nurture first |

Premature outreach to content downloaders damages trust. Nurture first.

Lead tiers:

- Hand-raisers skip scoring and go straight to sales, on the five-minute target.
- Marketing-qualified leads combine firmographic fit, behavioural intent, and any third-party intent. A starting split is 40% fit, 40% behaviour, and 20% third-party intent. Adjust it against the client's closed-won data.
- Product-qualified leads, where there is a free product, are routed on usage triggers.

Context packet for a marketing-to-sales handoff: firmographics, the full engagement history, the score broken down into fit and intent, the other contacts at the same account, and any qualification data already gathered. Enrich before routing, so the rep does not do the research while the lead waits.

Marketing-to-sales agreement:

- Marketing commits to a number of qualified leads, and to the pipeline contribution that goes with them.
- Sales commits to responding within the SLA, a set number of follow-up attempts, and a recorded outcome by a fixed deadline.
- Enforce it with automatic escalation, automatic reassignment after 24 hours, and a weekly compliance report.

Leads from known accounts go to the account owner, not into rotation. Route by language as the first filter where the team is split by region.

### Step 3: Sales to implementation

Customer excitement is highest at signature and falls quickly when nothing happens. Move the work within days, not weeks.

Context packet, seven elements:

1. How the deal started, and where it came from.
2. The customer's goals, with measurable success criteria stated in their terms.
3. The stakeholder map: champion, economic buyer, end users, and any detractors.
4. Every commitment the seller made, explicit and implied. Keep this as a promise log.
5. Known risks and internal politics.
6. Technical requirements: integrations, migration, and compliance.
7. The customer's timeline, including the critical events identified in qualification.

Milestones, as starting targets:

| Milestone | Target |
|---|---|
| Seller briefs implementation | 24 to 48 hours after signature |
| Introduction email to the customer | Within the first week |
| Kickoff scheduled | 48 to 72 hours after signature |
| First implementation meeting | 2 to 7 days |

For partner-delivered work, the partner receives the same packet, the promise log, and the stakeholder map. The seller attends the partner kickoff. The partner reports milestones back to the company's records. Keep hypercare for two to four weeks after go-live, as the bridge to customer success.

Choose the seller's involvement by deal size. These are examples; set the bands for each client:

- Warm overlay, the default: the seller attends kickoff and introductions, then steps back, and stays copied for about two weeks.
- Pre-sale customer success, for large deals: the CSM joins late-stage calls.
- Clean handoff, for small deals: an automated handoff with no ongoing seller involvement.

### Step 4: Implementation to customer success

This is the least standardised transition and the one with the most consequence. Early value, in the first 30 days, is linked to better retention. Treat it as a measured stage.

Context packet: scope and configuration, training completed and still missing, open issues with their workarounds, customer sentiment during implementation, the updated stakeholder map, first adoption metrics, and lessons learned.

Go-live is ready only when all five conditions hold:

1. The tasks work end to end.
2. The people who will use the product are trained.
3. The data has been migrated.
4. A support plan is in place.
5. A rollback plan exists.

Start health scoring at go-live, not at the first steady-state review. Track the completion of milestones, stakeholder engagement, the customer's responsiveness, admin login frequency, and training attendance.

### Step 5: Customer success back to sales (expansion)

Expansion is usually cheaper to win than new business, but it has no owner unless one is named. The source's cost figures are historical and are not used as rules here.

Three expansion types. Choose the right one, because each has a different sales process:

| Type | Buying group | Pipeline | Discovery |
|---|---|---|---|
| Upsell | Same champion and budget | Short: identified, proposal, won | Refresh the qualification |
| Warm cross-sell | Partial overlap; the champion introduces the new group | Standard, with a needs assessment | Partial new qualification |
| New-group cross-sell | A completely new buying group | Full discovery stages | Full new qualification, required |

A cross-sell to a new buying group is a new-logo sale inside a known company. Trust sits with the account, not with that group. Putting it into the short pipeline distorts win rates and velocity.

The litmus test: if the company lost the contract in one business unit, would that affect closing in another? If not, treat the deal as a new logo with a customer referral as its source.

Ownership by contract value. These bands are examples. Set them in governance, because ambiguity means nobody closes the deal:

- Small contracts: the CSM closes end to end.
- Mid-size contracts: the account executive and the CSM share the deal. The CSM stays in the meetings for context.
- Large contracts: the account executive runs the full cycle. The CSM introduces and advises.

Expansion signals to watch:

- Usage: seat limits approaching their cap, adoption of new features, rising daily use.
- Relationship: a champion promoted, a new stakeholder, positive survey scores.
- Commercial: headcount growth at the customer, a new budget cycle, interest from other departments.
- Outcomes: value delivered ahead of plan, return exceeded, new use cases raised.

Handback sequence: the CSM flags a signal, a deal is created and assigned to the account executive, the CSM prepares a short brief (health, usage, stakeholders, and open opportunities), a joint meeting takes place, and the rules of engagement are agreed from there.

### Step 6: Lifecycle and account-based loops

After the sale, marketing has five jobs: onboarding (role-based education), adoption (feature guidance), retention (value reports and business reviews), expansion (usage-triggered content), and advocacy (case studies and reviews).

Account-based plays for existing customers include churn prevention (competitor activity leading to executive outreach), cross-sell (content matched to products), new-department multi-threading, renewal preparation (value reports 90 to 120 days before renewal), and usage-based expansion. Each one feeds the handoff back to the owner.

### Step 7: Use AI only where it removes manual work

Useful where the work is repetitive: drafting a handoff summary from the call record, enriching a record before routing, and flagging a usage trend for review.

Controls that apply to any AI use in handoffs:

- The source record stays the basis for every claim. A summary that adds facts not in the record is wrong.
- Data residency, model-training opt-outs, and consent must be confirmed, especially for customers in the EU.
- A human approves any customer-facing message or any change to a deal record.

### Step 8: Measure each handoff

| Handoff | Key measures | Starting targets |
|---|---|---|
| Marketing to sales | Speed to first response, conversion from qualified lead to opportunity, share of leads never worked | Under 5 minutes for hand-raisers; under 5% never worked |
| Sales to implementation | Time to kickoff, completeness of the packet, quality score | Under 7 days; packet complete over 90% of the time |
| Implementation to customer success | Time to first value, go-live rate, early churn | Over 85% go-live; under 3% early churn |
| Customer success back to sales | Expansion pipeline from customer success, handoff time, expansion win rate, net retention | Handoff under 48 hours; growing each quarter |

Leading indicators of failure:

- Unworked leads above about 10%: an overloaded team or a routing failure.
- Rising rejection of qualified leads: the ideal customer profile is misaligned.
- Time to kickoff over 14 days: a bottleneck between sales and implementation.
- Falling onboarding completion: capacity or complexity is the problem.
- A shrinking expansion pipeline: customer success is not surfacing signals.

Quality scorecard: the receiving team rates each handoff from 1 to 5 on the completeness of information, alignment with promises, continuity of customer sentiment, quality of the context transfer, and quality of the stakeholder map. Review it weekly.

## Output

- The bow tie for the client, with an owner, a packet, an SLA, a trigger, and a measure for each transition.
- The promise log template, and the context packet templates.
- The ownership model, with the contract value bands set for the client.
- The dashboard of measures, and the leading indicators with their thresholds.
- The first transition to fix, with the reason it leaks most.

## Quality bar

Each transition has a named owner and an SLA. The receiving team reads the context packet, and they rate it. Speed to first contact is measured, and breaches reach someone accountable. After signature, customer success can see what was promised without asking. Watch for handoffs that depend on memory, expansion owned by no one, and dashboards that only show the leaks in retrospect.

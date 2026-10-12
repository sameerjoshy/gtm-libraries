---
name: sales-methodology
version: 1.0.0
status: draft-for-review
description: "Use to choose and operationalise a sales methodology: SPICED for recurring-revenue discovery and qualification, MEDDIC or MEDDPICC for complex enterprise deals, BANT as a first screen only, and Challenger, SPIN, or Gap Selling as selling styles. Covers the discovery call structure, the discovery score as one field per deal, stage gates, CRM properties, deal-review coaching, rep onboarding, the discount conversation, and how the methodology connects to the pipeline. Use when reps skip discovery, deals reach proposal unqualified, or the framework lives in a deck and not in the CRM. Not for the health score (see deal-velocity) or change management across the whole revenue team (see revops-change-management)."
sources:
  - "Sales methodology implementation (MIT, Rutger Katz / Neon Triforce): SPICED elements and 0-3 scoring, CRM properties and stage gates, coaching prompts, customer-cluster routing, discovery call timings, MEDDIC and MEDDPICC scoring, BANT limitations, Challenger, SPIN, Gap Selling, the selection guide, discount negotiation playbook, pipeline management model, stakeholder roles, AI-assisted scoring with override guardrails"
  - "Removed as unverified or vendor-sourced: multi-threading and win-rate figures from call-analytics platforms, talk-ratio findings, framework uplift percentages, the survey and history claims about framework origins, the platform capability claims, and the cold-email and consent rules by country (replaced by a counsel point)"
  - "Corrected: a framework score is one scale per team, and SPICED's 0-15 total is recorded in DECISIONS.md as a discovery score. It is not the health score and is not summed with it"
  - "Adapted for GTM-360: the stage thresholds, the discovery call timings, and the coaching cadence are author defaults to calibrate. Persona and reference detail from the source is summarised here; full persona playbooks are not carried over"
---

# Sales methodology

## Purpose

A methodology gives reps a shared way to have a discovery conversation, judge whether a deal is real, and decide what to do next. It only works when it is written into the CRM, the stage gates, and the weekly coaching. A framework that lives in a training deck changes nothing in the pipeline.

This skill chooses a methodology for the team, sets it up in the CRM, and sets the rhythm that keeps it in use. The main framework is SPICED, because it suits recurring-revenue deals. MEDDIC and MEDDPICC are the alternative for complex enterprise deals. BANT is a screen, not a method.

## When to use

- Reps skip discovery, and deals reach proposal with no economic buyer or decision process.
- Deal reviews are status updates, not qualification.
- The team has no shared language for what makes a deal qualified.
- A new framework is being introduced, or the current one is ignored.
- Discount requests arrive without a link to the evidence of value.

Route elsewhere when:

- The question is the approval of discounts. Use `deal-desk-operations`.
- The question is the stage evidence scale for forecasts. Use `deal-qualification-gates`.
- The question is the deal health score. Use `deal-velocity`.
- The question is the wider change programme. Use `revops-change-management`.
- The question is building the target account list. Use `icp-builder`.

## Inputs

- Average deal size, sales cycle length, and the share of recurring revenue.
- The current CRM deal stages and any fields for qualification.
- Recent deals, won and lost, with the notes available.
- The rep count and their experience levels.
- The discount history, and the reasons recorded for it.

## Procedure

### Step 1: Choose the methodology

| Factor | SPICED | MEDDIC / MEDDPICC | BANT | Challenger, SPIN, Gap |
|---|---|---|---|---|
| Best fit | Recurring revenue, mid-market and large, cycles of 30 to 90 days or more | Complex enterprise, several stakeholders, cycles of 90 days or more | High-volume, low-value screening | A selling style, not a qualification method |
| Typical deal size | Mid-range to large | Large | Small | Any |
| Role | Discovery and qualification | Qualification | First screen (five to ten minutes) | Conversation style |

Recommended pairings:

- **SPICED with Challenger.** SPICED gives the structure for discovery. Challenger gives the posture: teach the buyer something new, tailor it to each stakeholder, and take control of the process.
- **MEDDPICC with SPIN.** SPIN shapes a multi-meeting discovery. MEDDPICC tracks qualification across the committee.
- **Gap Selling with SPICED.** Gap Selling's current and future state line up with SPICED's situation, pain, and impact.
- **BANT then SPICED.** BANT as the quick screen for inbound, then SPICED for qualified deals.

Pick one qualification framework per team. Several frameworks running at once produce several scores that nobody can compare.

BANT is a filter. It answers "is this worth pursuing?" and not "how do we win?" If it is reordered as NTBA, it is still a filter.

### Step 2: Learn SPICED

SPICED is five elements. The "CE" pair is one element, the critical event.

- **Situation.** How the customer works today: the team, tools, process, and growth stage. Prove you understand their baseline. Discovery question: "Walk me through how your team handles this today."
- **Pain.** The specific problem caused by the current situation, with a cost where it can be measured. Discovery question: "What is breaking, and what does that cost you?"
- **Impact.** What changes if the problem is solved, and what happens if it is not. The buyer should do the value arithmetic. Discovery question: "If this were solved in the next 90 days, what would change?"
- **Critical event.** An external deadline or trigger that makes the timing matter, such as a board review, a contract renewal, or a compliance date. Deals without one tend to stall, so treat a missing critical event as a risk to name.
- **Decision.** The criteria, the committee, and the steps from interest to signature. Map each person who touches the decision, their priorities, and whether they can block it.

### Step 3: Score SPICED, one score per deal

Score each element from 0 to 3:

- 0, unknown: not explored.
- 1, identified: a surface understanding.
- 2, validated: confirmed with the buyer, with evidence.
- 3, leveraged: actively used to move the deal forward.

The total runs from 0 to 15. Read it as follows:

- 12 to 15: well qualified. Focus on execution.
- 8 to 11: gaps. Find the weakest element and close it before advancing.
- 4 to 7: under-qualified. Do not move to proposal. Return to discovery.
- 0 to 3: not yet a deal. It is a conversation.

Record the SPICED total in its own field. It is a discovery score. It is not the team's deal health score, which is the 0 to 100 scale in `deal-velocity`, and the two are not added together (see DECISIONS.md).

Score on evidence. A 2 means the buyer confirmed it. A 3 means the score changed what the team did.

### Step 4: Set up the CRM

Create these fields on the deal:

- One score field per SPICED element, with values 0 to 3.
- A total field, calculated where the CRM allows.
- A critical event date, and a description of the event.
- The named champion and the named economic buyer.
- The quantified pain and the quantified impact, in the client's currency.
- A committee map, listing each stakeholder's role, priorities, and veto power.
- A decision process field, listing each step to signature with timing and risk points.
- The economic buyer engagement level, from not contacted to committed.
- A field recording the methodology in use, so that reporting can split by method.

Set stage gates. Example thresholds, to calibrate against the team's own won deals:

- **Discovery to solution design:** Situation at least 2, pain at least 2, impact at least 1, pain quantified.
- **Solution design to proposal:** critical event at least 1, or flagged as a risk. Decision at least 2. Champion engaged in at least two conversations. Economic buyer identified. Total at least 8. Impact quantified.
- **Proposal to negotiation:** economic buyer engaged directly. Decision criteria confirmed, not assumed. Decision process walked through to signature. Total at least 10. Technical buyer confirmed with no blockers.
- **Negotiation to closed:** verbal yes from the economic buyer and the champion. Legal and procurement engaged with dates. No open objections.

A deal that moves forward without the gate is a deal that is not qualified.

### Step 5: Run discovery calls to a structure

Before the call: know the company's size, sector, and situation. Hold one hypothesis about the buyer's problem. Prepare two or three questions for each element.

**Inbound discovery, 20 to 30 minutes.** The buyer has already identified the problem, so the call confirms the baseline and cost, then moves to timing and committee.

- 0 to 2 minutes: agenda and context.
- 2 to 8 minutes: situation and pain. Confirm the cost.
- 8 to 18 minutes: impact and critical event.
- 18 to 25 minutes: decision. Map the committee and the process.
- 25 to 30 minutes: next steps, with the stakeholders named.

**Outbound discovery, 45 to 60 minutes.** The seller introduces the problem, so the call needs more context-building.

- 0 to 3 minutes: set the purpose. Make clear that this is a conversation about how the buyer works, not a pitch.
- 3 to 10 minutes: situation. Ask about the organisation, the sales structure, the growth target, and the tools.
- 10 to 18 minutes: pain. Ask where deals are lost, and what that costs.
- 18 to 28 minutes: impact. Ask what would change if the problem were solved, and what that is worth.
- 28 to 35 minutes: critical event. Ask what is driving urgency and whether there is a date.
- 35 to 42 minutes: decision. Ask who decides, and how.
- 42 to 60 minutes: deep dive and next steps. Competitive position, technical requirements, and procurement.

After each call, score the elements while the notes are fresh. Record the buyer's exact words for the cost, the critical event date, and each decision step. Name the weakest element, and the one person to speak to next.

Track talk time as a coaching signal. The team should set its own target, and check that the buyer is doing most of the talking in discovery.

### Step 6: Route by customer cluster

Where the client sells to a few distinct buyer types, define a cluster for each: its typical deal size, cycle length, and the SPICED element that tends to carry it. Use the cluster to choose the language for the first call. A buyer who hears their own situation described back is more willing to continue.

Build the clusters from the client's own deal data, not from a generic profile.

### Step 7: Coach through the methodology

**Weekly deal review.** Pick three to five deals per rep, prioritising stalled deals, close dates in the next month, and large opportunities. Ask methodology-specific questions, not "how is this going?" Ask: "What is the critical event?" and "Who is the economic buyer, and have you spoken to them?"

Score the deal live, with the rep, so the rep learns the scoring. Identify one gap, and assign one action to close it. One action, not three. "Get a fifteen-minute call with the finance lead this week. How will you do that?" Follow up the next week: was it done, and what changed?

**Coaching prompts for deal reviews:**

- "Walk me through the decision process. How many steps from interest to signature? Where could it stall?"
- "Who holds the budget? Have you spoken to them directly, or are you relying on the champion to carry the message?"
- "The pain is documented, but not quantified. What does this cost them each quarter?"
- "What is the critical event? If there is none, this will stall. Is there a date?"
- "If the champion left tomorrow, who would carry the deal?"
- "What does procurement need, and how long does legal usually take?"

**Driving adoption.** Methodology adoption fails when it feels like extra work. Make it the way selling works:

- Put it in the CRM, in the deal record, not in a separate document.
- Coach with the methodology on live deals, not in a separate training session.
- Recognise wins that came from the methodology, such as an early critical event or direct access to the economic buyer.
- Start with five to seven fields. Add more only when the first set is routine.

### Step 8: Onboard new reps over four weeks

- **Week 1:** framework and language. Score a set of historical deals with the manager.
- **Week 2:** guided practice. Role-play discovery, and analyse recorded calls against the elements.
- **Week 3:** shadow live calls, and debrief each one.
- **Week 4:** live calls with coaching after each one.

Then continue weekly deal reviews, monthly calibration sessions where managers score the same deal independently, and a quarterly refresh of the language.

### Step 9: Handle the discount conversation

When a buyer asks for a discount, first find out what is driving the request. Most requests are signals rather than price demands:

- "We need a discount" often means "I need to show I negotiated."
- "It is too expensive" often means "I do not see the value yet."
- "A competitor is cheaper" often means "I have an alternative and want leverage."
- "Our budget is limited" often means "this is not a priority," or "the timing is wrong."

Ask: "What is driving the request?" before offering anything.

Then use the methodology:

- **A strong pain score** means the cost of the problem is on record. Show the return against the annual cost, in the buyer's numbers.
- **A strong champion** can make the internal case. Offer to build the business case together, and ask what the finance lead needs to see.
- **A confirmed critical event** limits the room for delay. Point out that a long negotiation puts the date at risk.

Trade, never give. Each concession should buy something in return. Example trades, to calibrate with the deal desk:

- A longer term, for a modest discount.
- An annual prepayment, for a payment-terms discount.
- Reference or logo rights, for a strategic discount.
- An expansion commitment, for a volume discount on a set schedule.
- A faster signature. The urgency is the concession, and it does not need a price.

Approval limits and the matrix belong to `deal-desk-operations`. Use the scripts and rules there for live objections.

Record the discount in CRM fields: whether it was requested, the reason from a fixed list, the percentage approved, the approver, the concession traded, the expiry date, and the days from first request to close. If discounted cohorts show lower net retention later, the discount attracted the wrong customers, and the governance needs tightening.

### Step 10: Run the pipeline on the methodology

The methodology feeds the pipeline model:

- **Stage entry and exit criteria** for each stage, from the gates in Step 4.
- **Required fields** for each stage. If a field is empty, the deal does not move on.
- **Inspection cadence.** A weekly review of the largest deals by close date, a monthly cross-functional pipeline review, and a quarterly review of coverage and win and loss patterns.
- **Kill criteria.** Close out a deal when there is no identifiable pain after two discovery calls, no access to the economic buyer by qualification, a critical event that keeps moving, a departed champion, a deal older than about twice the average cycle with no progress, or requirements outside the product. A deal with no progress for more than about one and a half times the average cycle goes to mandatory review.
- **Forecast categories**, defined by evidence, not feeling. Commit: verbal yes, in legal, expected to sign this period. Best case: presented and accepted, budget confirmed, no known blockers. Upside: a high SPICED total, the champion engaged, and a plausible timeline. Pipeline: too early to forecast.

If Commit plus Best Case is below quota, the problem is pipeline generation, not forecasting. For forecast method, use `revops-forecasting`. For the Salesforce field and stage configuration, use `revops-salesforce`.

### Step 11: Use AI assistance with guardrails

AI tools can extract candidate evidence for each SPICED element from call transcripts, pull prior conversations from the CRM, and surface company signals such as hiring or funding. Use them to suggest scores, not to set them.

- Never write AI scores into the deal without a rep confirming or overriding them. Store both the AI score and the rep score, so that calibration can be checked.
- Track the override rate. A very low rate may mean reps are accepting suggestions without reading them. A very high rate may mean the model is poorly calibrated for this team.
- Use the calibration in weekly reviews. If a rep's pain scores run well below the team's average, ask whether the buyers are different, or whether discovery is not digging deep enough.
- Keep methodology training focused on closing skills and discovery. Prospecting is covered by the outbound and list skills.

Thresholds for override rates are defaults to calibrate against the team's data.

### Step 12: Apply the data protection points

Buying committee maps hold personal data: contact details, roles, priorities, and influence. Record a lawful basis for each contact, in a field, and check it at the time the contact is added. The basis may be consent, contract, or legitimate interest with a documented balancing test. Confirm which applies with counsel.

When a deal closes or is disqualified, delete personal data on request, within the period that counsel confirms.

Rules for cold contact and electronic marketing vary by country. Check them with counsel before the first outreach, and do not rely on a summary of the rules in this skill.

## Output

- The methodology chosen, with the reason, and the pairing with a selling style if any.
- The SPICED or MEDDIC scoring guide, with the definitions and thresholds.
- The CRM fields and stage gates, with the calibrated thresholds.
- The discovery call structure, inbound and outbound.
- The weekly deal review format, with the coaching prompts.
- The four-week onboarding plan and the ongoing cadence.
- The discount conversation guide and the CRM fields for negotiation.
- The pipeline rules: stage criteria, kill criteria, and forecast categories.
- The AI guardrails and the override tracking.

## Diagnostic questions

1. Pick the last ten deals that reached proposal. How many have a documented economic buyer and a decision process?
2. Where is the methodology recorded: in the CRM, in a deck, or nowhere?
3. What do the weekly deal reviews actually ask?
4. How many discounts in the last quarter have a recorded reason and a recorded trade?
5. Are reps scoring the methodology from evidence, or from how they feel about the deal?

## Quality bar

One framework is used across the team, and it is written into the CRM. Stage gates are enforced, and every score rests on evidence the buyer confirmed. Coaching uses live deals. Discounts are traded and recorded. AI suggestions are confirmed by a rep. Watch for frameworks that exist only in decks, scores with no evidence, deals advanced without an economic buyer, and discounts given without a trade.

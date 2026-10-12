---
name: lead-routing-design
version: 1.0.0
status: draft-for-review
description: Use when designing or fixing how inbound or outbound leads are assigned to reps: the routing decision order, the routing model (geographic, named account, round-robin, weighted, skills-based, load-balanced, or hybrid), speed-to-lead SLAs with escalation, account-based routing for existing accounts, and the quarterly routing audit. Covers strategy and logic, independent of CRM. For CRM build-out, use the platform skill. For scoring leads, see marketing operations.
sources:
  - "Lead routing (MIT, Rutger Katz / Neon Triforce), six-question routing decision order with consent check first, routing models, round-robin and weighted round-robin with availability checks, territory design variables, speed-to-lead tiers with escalation timers, account-based routing, quarterly audit checklist, AI routing governance checkpoints"
  - "Speed-to-lead research cited in the source (MIT Sloan 2007, HBR 2011, and vendor reports) is for context only and is not used as a rule"
  - "Adapted for GTM-360: vendor tool landscape removed, AI conversion-lift claims removed as unverified, consent-first ordering kept, build-versus-buy thresholds labelled as practice-based"
---

# Lead routing design

## Purpose

Routing decides who gets a lead, how fast, and with what context. A lead that sits in a queue for two hours has usually lost most of its chance. Design the routing logic first, then build it in whichever system the client uses.

## When to use

- Leads are reaching the wrong rep, or sitting unassigned.
- Reps are picking off the easy leads from a shared queue.
- Speed to first contact is slow, or nobody is measuring it.
- Territories need redesigning.
- A new routing tool or a new CRM is being set up.

Route elsewhere when:

- The question is how to build the rules in a specific CRM. Use the CRM platform skill.
- The question is how to enrich a lead before routing. Use `data-enrichment`.
- The question is how to score a lead. Use `marketing-operations`.
- The question is what happens after assignment. Use `revenue-handoffs`.

## Inputs

- Lead sources and volumes, by month.
- The rep roster: territory, segment, product or vertical expertise, language, tenure, and current quota attainment.
- The account list, including named and strategic accounts and their owners.
- Current SLA and response-time data, if any exists.
- Consent and opt-out status for each contact. Check this before routing.
- Working hours and time zones for each rep.

## Procedure

### Step 1: Apply the routing decision order

Every lead passes these checks in order. Stop at the first check that settles it.

1. **Consent.** Is the contact under a marketing objection or a data-protection opt-out? If yes, route to a no-outreach queue and keep the record. Do not route to sales.
2. **Known account.** Does the lead match an existing account? If yes, route to the account owner (see Step 5).
3. **ICP fit.** Does the lead meet the scoring threshold? If no, route to nurture. If yes, continue to sales routing.
4. **Territory.** Which territory does the lead belong to, by geography, industry, company size, and product interest?
5. **Rep within the territory.** Round-robin, weighted, skills-based, or load-balanced.
6. **Availability.** Is the rep available? If yes, assign and notify. If not, route to a backup, or queue with an SLA timer.

Consent comes first so that no later step can route a contact who has opted out.

### Step 2: Choose the routing model

| Model | How it works | Suits | Watch for |
|---|---|---|---|
| Geographic | Routes by region, country, or city | Field sales with territories | Territories of unequal size |
| Named account | Routes to the account owner | ABM and enterprise | New accounts that fall through |
| Round-robin | Rotates evenly across reps | Inside sales with equal territories | Ignores capacity |
| Weighted round-robin | Rotates with weights, such as a senior rep at twice the share | Mixed-tenure teams | Harder to maintain |
| Skills-based | Routes by product, language, or vertical expertise | Multi-product or multi-language teams | Specialists become bottlenecks |
| Load-balanced | Routes by current capacity | High-volume teams | Needs live capacity data |
| Hybrid | Territory first, then round-robin within the territory | Most B2B teams | More rules to maintain |

Hybrid is the usual default for B2B. Start there unless the client has a clear reason not to.

### Step 3: Build round-robin correctly

Basic rotation: keep a counter, assign to the rep at position counter modulo the number of reps, then advance the counter.

Weighted rotation: expand the rep list in proportion to the weights. A senior rep at weight 3, two mid-level reps at weight 2, and a ramping rep at weight 1 gives a list of eight, with the senior rep appearing three times.

Add availability checks before each assignment:

- Skip a rep who is out of office.
- Skip a rep who has reached the daily lead cap.
- If the lead arrives outside the rep's working hours, queue it for the next working hour, or route it to a rep who is working.

Weights are illustrative. Set them from capacity, ramp status, and attainment.

Common problems and fixes:

| Problem | Symptom | Fix |
|---|---|---|
| Cherry-picking | Reps take good leads and leave the rest | Assign directly to an owner, not to a shared queue |
| Queue rot | Leads sit untouched | An SLA timer with automatic reassignment |
| Uneven distribution | One rep receives more | Audit the counter, and check time zone and filter logic |
| Ramping rep flooded | A new rep gets full volume | Use a weighted rotation during ramp |
| Time-zone gaps | Leads arrive with no owner outside hours | Time-aware routing, or follow-the-sun coverage |

### Step 4: Design territories

Territory variables, from simplest to most complex: geography, industry or vertical, company size, product or solution, named accounts, and a hybrid of several.

Check territories each quarter:

- Pipeline per territory should sit within about 10 to 15% of the median, for territories in the same segment. This tolerance is practice-based.
- Lead volume should be even within each segment.
- A large difference in win rate between territories points to the territory design, not to the reps.
- Coverage should match the required multiple for the win rate: one divided by the win rate. See `revops-forecasting`.

Choose the assignment method by team size:

- Under 10 reps, simple territories: a static assignment kept in a spreadsheet.
- 10 to 50 reps: rule-based assignment in the CRM, with audit logs.
- Over 50 reps, or overlays and hierarchies: a territory management module.

### Step 5: Route existing accounts to their owners

When a lead matches an existing account:

- If the account has an owner, route to the owner, so the relationship is preserved. If the owner is an SDR, route to the AE the SDR works with.
- If the account exists but has no owner, route through the standard territory logic, and assign the owner at the same time.
- If there is no match, use standard routing.

Special cases:

- A new contact at an existing account may be an expansion signal. Route to the owner, and alert customer success.
- A contact at a customer account goes to the customer success manager, not to sales.
- A competitor account should be routed differently, or excluded from routing altogether.
- A former customer returning is a priority. Route to the original AE or a win-back owner.

### Step 6: Set speed-to-lead SLAs

Tiers, with first-touch targets. These are practice-based starting points.

| Tier | Definition | First touch | Escalation |
|---|---|---|---|
| 1, hot | Strong ICP fit and high engagement, such as a demo or pricing request | 5 minutes | At 15 minutes, alert the manager. At 30 minutes, reassign. |
| 2, warm | Good fit and moderate engagement, such as a content download | 1 hour | At 2 hours, alert the manager. At 4 hours, reassign. |
| 3, nurture | Low fit or low engagement | 24 hours | At 48 hours, return to marketing and alert operations. |

Track these fields for every lead: the time routed, the time of first activity, the minutes between them, the SLA status (met, at risk, or breached), and the SLA tier.

Escalation runs in stages:

1. **First threshold reached, no activity:** alert the rep.
2. **Twice the threshold, still no activity:** alert the manager, and create a review task.
3. **Four times the threshold, still no activity:** reassign to a backup or the queue, alert operations, and record the breach.

The source research on speed-to-lead is consistent in direction: contacting a hand-raiser within minutes converts better than contacting them after hours. The exact curve varies by industry and lead source, so set the client's own targets from their data.

### Step 7: Consider AI-assisted routing only with controls

AI-assisted assignment, such as predicting which rep will convert a given lead, is an option at higher volumes. Use it with these controls:

1. **Explainability.** For each assignment, log the top three factors behind it.
2. **Fairness audit.** Check monthly that no rep is systematically disadvantaged by the model. Training data can carry historic bias.
3. **Override logging.** Record when a manager or rep changes an AI assignment. Use those records to review the model.
4. **SLA compliance.** AI routing still has to meet the SLAs. If it does not, fall back to a hybrid of AI recommendation with manual override.

Do not adopt AI routing on the strength of a vendor's conversion claim. Test it against the client's own round-robin baseline first.

### Step 8: Decide build or buy

Practice-based thresholds, to confirm with the client:

- Under about 500 leads a month, with simple territories: build with native CRM automation.
- About 500 to 5,000 a month, moderate complexity: evaluate a dedicated routing tool, and build only if the team has strong CRM administration.
- Over about 5,000 a month, or complex territories: a dedicated routing tool. Justify it with the expected speed-to-lead gain multiplied by the conversion lift and the deal value.

### Step 9: Run the quarterly audit

1. **Coverage:** do any rules produce no owner? Those leads are falling through.
2. **Balance:** is distribution even across reps in the same segment? A variance of about 10% is acceptable.
3. **Speed:** what is the median speed to first contact, and the 90th percentile? Target a median under five minutes for Tier 1.
4. **SLA compliance:** what share of leads were touched within SLA? Target 90% or more.
5. **Reassignment rate:** how often are leads reassigned? Above about 15% suggests a logic problem. This threshold is practice-based.
6. **Conversion by route:** do different routes convert differently? A route that converts much worse may be broken.
7. **Queue health:** how many leads are waiting now, and for how long? Target no lead waiting more than an hour.
8. **Availability:** are there times with no rep available?

## Output

- The routing decision order, as implemented, with each check named.
- The model chosen and the reason.
- The territory design and the balance figures.
- The SLA tiers, the fields, and the escalation timers.
- The audit results, with the failing checks named.
- The list of questions the client must answer before build: capacity, ramp status, time zones, and consent sources.

## Quality bar

Consent is checked first. Every lead has an owner, and each owner is reachable in time. Speed to first contact is measured and visible. Territories are balanced and reviewed each quarter. Reps cannot pick their own leads from a shared queue. Watch for leads with no owner, queues nobody watches, and AI routing adopted without a baseline.

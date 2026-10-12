---
name: cs-operations
version: 1.0.0
status: draft-for-review
description: Use when customers churn without warning, red accounts pile up, renewal conversations turn contentious, or expansion-ready accounts slip away. Designs the post-sale operating model: a five-dimension health score refreshed weekly, traffic-light triage into rescue or renewal-risk mode, the renewal timeline from T-120, event playbooks, coverage tiers, discount governance, churn autopsies, and the customer-to-product feedback loop. Tool-neutral. Not for expansion scoring and whitespace (see expansion-revenue-architect) or the Sales-to-CS handoff mechanics (see revenue-handoffs).
sources:
  - "Customer success operations (MIT, Rutger Katz / Neon Triforce), four-pillar operating model, CS maturity stages, five-dimension health score and its weights, traffic-light bands, anti-patterns, renewal timeline T-120 to T+7, event-based playbooks, discount sunset governance, churn autopsy and feedback loop, cadence design"
  - "Vendor claims removed: platform feature lists, ML churn-accuracy and churn-reduction percentages, AI-agent productivity claims, vendor coverage ratios, dated survey medians, and a survey-tool shutdown note. Benchmarks are context only"
  - "GDPR Article 22 note retained as a point for counsel, not legal advice. Platform-specific references removed"
  - "Adapted for GTM-360: weights, bands, thresholds and cadences are author defaults to calibrate against the client's own churn outcomes"
---

# Customer success operations

## Purpose

Customer success operations is the system that keeps paying customers paying and growing: it sees risk early, assigns an owner, runs a defined play, and learns from every loss. Without it, retention depends on individual heroics, and every churn is a surprise.

This skill designs that system. It is tool-neutral. Choose the platform after the process is designed, not before.

## When to use

- Customers churn and nobody saw it coming.
- Red accounts appear suddenly, with no owner or plan.
- Renewal conversations start with a discount request, not a value discussion.
- CSMs have too many accounts to give each one attention.
- Product does not act on what customers say.

Route elsewhere when:

- The question is which expansion to pursue, or how to score expansion readiness. Use `expansion-revenue-architect`.
- The question is how a closed deal passes to CS. Use `revenue-handoffs`.
- The question is onboarding to first value. Use `onboarding-activation`.
- The question is the metric definitions for GRR and NRR. Use `revenue-metrics`.
- The question is pricing and discount policy. Pricing governance sits in a separate skill (`pricing-monetisation-ops`).

## Inputs

- The customer list with contract dates, ARR, segment, and current CSM.
- Product usage data by account: active users, feature use, and trend.
- Support tickets with severity and resolution time.
- Renewal outcomes for the last 12 to 24 months, including churn reasons.
- Current health checks, if any, and how they are used.
- CSM capacity and the number of accounts each CSM holds.

## Procedure

### Step 1: Assess the operating model

CS operations has four pillars. Neglect one and the others fail.

- **Process:** playbooks, the renewal timeline, escalation paths, and swimlanes between CS, sales, support, and product.
- **Data:** health scores, churn prediction, expansion signals, and cohort analysis.
- **Technology:** a single customer record, usage analytics, support data, and the CRM, connected so that a CSM sees one view.
- **Enablement:** CSM onboarding, documented playbooks, certification on the key processes, and a knowledge base.

Score the current state with the maturity stages in Step 2.

### Step 2: Place the team on the maturity stage

| Stage | Health scoring | Renewals | Expansion | Governance |
|---|---|---|---|---|
| Reactive | None. The team responds to churn. | Ad hoc, customer-led | Accidental | CS isolated, no feedback loops |
| Defined | Manual, based on CSM judgment | A playbook starts about 60 days before expiry | Signals found inconsistently | A written handoff exists |
| Proactive | A composite score, updated weekly, with alerts | Automated 90-day process with save plays | A scoring model and targeted outreach | Quarterly CS and product reviews |
| Predictive | A calibrated model, checked against outcomes | Preventive interventions | Expansion scoring feeds the sales pipeline | Near-real-time feedback loops |

If the team is Reactive, build Defined first. The later stages depend on the health score and the renewal timeline, which Reactive teams do not yet have.

### Step 3: Build the health score

Use a composite score from 0 to 100, built from five weighted dimensions. Default weights are a starting point. Calibrate them against the client's own churn outcomes once a year of data exists.

| Dimension | Default weight | What it measures |
|---|---|---|
| Product usage | 35% | Login frequency, feature adoption, depth of use, and trend |
| Relationship | 25% | Executive sponsor engaged, survey response, meeting cadence, and breadth of users across the organisation |
| Support | 18% | Ticket volume trend, severity, resolution time, and satisfaction |
| Commercial | 17% | Contract value trend, payment history, and expansion conversations |
| Outcomes | 5% | Achievement of the stated goals, value realised, and milestone completion |

Usage carries the highest default weight because it is usually the most direct signal. Outcomes carries the lowest because it is often incomplete early on. Treat both as defaults.

**Bands.** Use these as starting thresholds:

- **Green (80 and above):** expansion posture, growth-partner conversations.
- **Yellow (40 to 79):** intervene, increase touchpoints, check the sponsor.
- **Red (below 40):** save mode, executive involvement.

Do not attach churn-probability figures to these bands until the client's own data supports them. Vendor and survey figures for churn risk by band are not evidence for this client.

**Red rule.** A customer does not turn red on one signal. Red means three or more dimensions breaking at once. A single dip, such as one unhappy support ticket, goes to yellow monitoring.

**Anti-patterns:**

- Binary scores ("healthy" or "at risk") with no gradation. Use the 0 to 100 scale.
- Usage-only scores. Use the composite.
- A score updated quarterly. Update weekly at minimum.
- Green accounts that churn. Calibrate the score against outcomes.
- Red accounts nobody acts on. The CS lead reviews every red account each week.

**Data protection point for counsel.** Health scores use personal data, such as survey responses and engagement from named contacts. If an automated score drives a customer-visible decision, such as a renewal discount or a reduced support tier, without human review, a documented lawful basis and a route to human review may be required under data protection rules, including GDPR Article 22 in Europe. The safe design is to let automation trigger internal escalation only, and require a CSM or manager to review before any customer-visible decision. Confirm with counsel.

### Step 4: Set coverage tiers

Segment accounts by ARR and complexity. The thresholds below are defaults. Set them from the client's own deal sizes and the time each account needs.

| Tier | Default criteria | Coverage model |
|---|---|---|
| High-touch | Above the strategic ARR threshold, or complex product | Named CSM, quarterly business reviews, dedicated onboarding |
| Mid-touch | The middle band, with moderate complexity and growth potential | Pooled CSM, templated touches, triggered playbooks |
| Tech-touch | Below the lower threshold, or simple self-serve use | Automated in-product guidance, community, webinars |

Set the CSM-to-account ratio from the work each tier needs, measured in hours per account per quarter, not from a vendor benchmark. Reassess tiers each quarter based on usage growth, health, and expansion potential.

Most teams try to high-touch everyone, which does not scale past a small number of accounts. The tier model is how coverage is rationed.

### Step 5: Run the renewal timeline

Start 120 days before contract end. Starting at 30 days leaves time only for discounting.

- **T-120, prep.** The renewal record is created automatically. The CSM reviews health, usage, and expansion signals. Finance confirms the contract terms. Product flags any blockers. If the health score is red, escalate now rather than waiting for T-90. Output: a renewal strategy, which is one of standard, at-risk save play, or expansion.
- **T-90, health check.** Run the business review. Build the value-delivered summary. Check internally for pricing or product changes. If a discount expires here, start a value-led conversation. Score the renewal as likely, at risk, or needs work.
- **T-60, proposal.** Standard: send the renewal proposal and present value, roadmap, and terms. At risk: the executive sponsor conversation, removal of barriers, and the save play. Expanding: present the expansion proposal alongside the renewal, jointly with sales.
- **T-30, negotiation.** Send the contract. Handle objections. Escalate to the CS leader if unsigned. Track daily. Use a graduated step-up only if it is needed, and only as a save play.
- **T-0, close.** Record the signed contract or the churn. If churned, start the churn autopsy within seven days, and feed the learning to product.
- **T+7, check-in.** Confirm satisfaction, record the win or loss reason, set the next review date, and update the health score.

Track: on-time renewal rate, early renewal rate, save rate for red accounts, and renewal cycle length.

### Step 6: Triage red accounts

When an account turns red, the CSM or an automated alert notifies the CS lead within 24 hours. The CS lead and the account executive decide the mode together:

- **Rescue mode (more than 90 days to renewal).** Find the cause, name a recovery plan with an owner, set a review date every two weeks, and involve an executive sponsor on both sides.
- **Renewal-risk mode (under 90 days).** Start the renewal process immediately. Do not wait for T-90.

Save play basics, in order:

1. Confirm the buying problem the customer hired you for, in their words.
2. Show the value delivered against that problem, with their numbers.
3. Name the barrier and remove it: a missing integration, an unresolved bug, a departed champion.
4. Bring in the executive sponsor, from each side.
5. Offer pricing last, and only if the value case is made. See Step 8.

If the customer's problem is no longer one the product solves, say so. A honest "wrong fit" verdict is better than a discount that delays churn by a quarter.

### Step 7: Install event-based playbooks

These are starting triggers. Tune them after two quarters of data.

| Event | Default response |
|---|---|
| Weekly active users fall by more than 30% week on week | CSM outreach within 24 hours. Find the cause: a change, holidays, a budget freeze, or a support issue. |
| Survey score below 6 (detractor) | Call within 48 hours. Record the specific complaint, not a general sense of dissatisfaction. |
| Champion leaves | Identify a new stakeholder within one week. Involve the next-level executive immediately. |
| Severity-one ticket, or three or more tickets in seven days | Triage within two hours, with the CS lead and the support manager. |
| No kickoff by day three | Reminder to CSM. |
| Health below 50 at day 90 | Move the account to a yellow playbook. |

### Step 8: Govern discounts so they do not surprise at renewal

The most common cause of contentious renewals is a discount that was never recorded with an expiry. At renewal, the customer anchors on what they paid, not on what the product is worth.

Install these controls:

- Every discounted contract carries an expiry date in the CRM.
- The T-120 step flags any discount expiring within the renewal window.
- The CSM prepares the value justification before the conversation.
- The conversation leads with value at T-90, frames the step-up at T-60, and offers a graduated step-up only as a save play at T-30.
- Group or consortium accounts get coordinated volume and tier checks from T-120 through T-30, with deal desk, and no terms outside the framework.

Discount approval matrices belong in pricing governance, not here.

### Step 9: Run the expansion handoff

Expansion is a separate motion with its own ownership model and scoring. This skill covers the health and renewal plumbing it depends on. Once a customer shows expansion readiness, hand over to `expansion-revenue-architect`, and use `revenue-handoffs` for the handoff mechanics.

### Step 10: Close the customer-to-product loop

Install four mechanisms. Without them, product does not hear what customers say.

- **Churn autopsy on every churned account.** The CS manager and the product manager review each one within seven days. The output is a churn reason category and a proposed action.
- **Feature request tagging.** Every request records the customer's ARR, the use case, whether a competitor is involved, whether it relates to expansion, and whether it blocks adoption.
- **Adoption blocker log.** A monthly list of the issues that stop customers from using the product, feeding a dedicated product queue.
- **Customer advisory board.** Quarterly, with three to five customer executives and the product leader. Use it to test direction, not to sell.

Product responds to revenue data. Present requests with their ARR and the number of accounts affected.

### Step 11: Set the operating cadence

A health score with no review is a dashboard nobody reads. Use this cadence:

- **Weekly:** CSMs review accounts whose score fell by more than 10 points. Flag any move from green to yellow, or yellow to red, to the CS lead.
- **Monthly:** full review of all scores. Each red account is reviewed with the CS lead and the account executive.
- **Quarterly:** portfolio review, business reviews for high-touch accounts, and recovery planning for red accounts.

Event triggers from Step 7 run on top of this cadence. They do not replace it.

### Step 12: Automate in stages

Automation helps only once the data is clean. Sequence it:

1. Start with a weekly composite score, refreshed from clean usage data.
2. Add real-time triggers for the events in Step 7.
3. Add automatic escalation to CSMs once the triggers have been checked for false alarms for at least two weeks.
4. Add call-transcript analysis or AI-assisted synthesis only after the key fields are populated. Set the field-completion threshold for the client, starting around 80% for the fields the score uses.

Automation notifies and recommends. The CSM remains accountable for the customer decision.

## Output

- The operating model, with the four pillars and their owners.
- The current maturity stage and the next step.
- The health score: dimensions, weights, bands, and the red rule.
- The coverage tiers, with the criteria and the coverage model for each.
- The renewal timeline with its owners and the save-play basics.
- The event playbooks and their response times.
- The discount governance rules.
- The churn autopsy and feedback loop, with owners and cadence.
- The weekly, monthly, and quarterly review agendas.

## Key metrics

Set targets from the client's own baseline after one quarter of measurement. The figures below are starting points, not standards.

| Metric | Starting target |
|---|---|
| Gross revenue retention | Track the trend first. Set the target from the baseline. |
| Net revenue retention | Track by segment as well as overall. |
| Time to kickoff | Under three days |
| Time to first login | Under seven days |
| Time to first value | Under 30 days |
| Renewal on-time rate | Above 90% |
| Save rate on red accounts | Above 40%, practice-based |
| Accounts without an executive sponsor | Under 5% |
| Admin time as a share of CSM time | Under 30% |
| CSM attrition | Under 15% a year |

Industry medians for these metrics vary widely by segment and deal size. Do not quote them to the client as targets without checking against their own segment.

## Diagnostic

Count the yes answers across five areas:

- **Process:** documented playbooks, a defined renewal timeline, a written health scoring framework, escalation paths, and business reviews for every high-touch account.
- **Technology:** one system that shows usage, support, and commercial data together, with automated scoring.
- **Data:** can you forecast churn 30 days out, and do you track expansion signals and team efficiency?
- **Enablement:** structured CSM onboarding, accessible playbooks, and process certification.
- **Governance:** a feedback loop to product, a handoff process to sales, monthly exec review of CS metrics, churn autopsies, and discount tracking.

Read the score as a guide. Fix the weakest area first, because the areas depend on each other.

- 0 to 6 yes: Reactive. Write the playbooks and the basic health score first.
- 7 to 13 yes: Defined. Connect the data and automate the playbooks.
- 14 to 19 yes: Proactive. Build the predictive models and rebalance coverage.
- 20 to 25 yes: Predictive. Tune the models, and add automation with human review.

## How to use this skill

- **"We keep losing customers and don't know why":** build the health score, and run churn autopsies on the last ten churned accounts. Patterns usually show within four weeks.
- **"The CS team is overloaded":** a coverage problem. Build the three tiers. Stop high-touching accounts that do not need it.
- **"Discounts are expiring and customers push back":** install discount governance. Record each expiry, lead with value at T-90, and keep step-ups as a T-30 save play.
- **"Product does not listen to CS":** install the feedback loop, with ARR on every request.
- **"We are starting from nothing":** run the diagnostic. Month one is playbooks and a basic score. Month two is the renewal timeline. Month three is automation.

## Quality bar

Every account has a health score and an owner. Red accounts have a named play before the renewal window opens. Renewal conversations start from documented value, not a pricing surprise. Churn autopsies feed a playbook for each churn cause. Watch for vendor churn percentages quoted as fact, scores that nobody acts on, discounts with no expiry, and a score that is never checked against outcomes.

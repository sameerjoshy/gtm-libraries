---
name: partner-channel-operations
version: 1.0.0
status: draft-for-review
description: "Use to run the operational plumbing of a partner or channel programme: choosing partner types and tiers, defining an ideal partner profile, deal registration and conflict rules, partner onboarding and enablement, co-sell motions, attribution of sourced versus influenced revenue, partner health scoring, and the review cadence. Use when partners are signed but not producing, when partner and direct reps fight over accounts, or when partner revenue cannot be reported. Not for deciding whether to build a partner motion at all (see partner-ecosystem-architect)."
sources:
  - "Partner channel operations (MIT, Rutger Katz / Neon Triforce): partner type matrix, ideal partner profile scoring, three-tier programme structure, deal registration process and conflict rules, CRM properties for partner deals, onboarding sequence, enablement content matrix, co-sell motions, sourced versus influenced attribution, partner health scoring, review cadence, maturity levels, common pitfalls"
  - "Removed as unverified: all benchmark statistics attributed to research reports and vendor studies (win-rate uplift, cycle-length, deal-size, churn, programme ROI, CAC, activation and retention rates, and the share of programmes under fifty partners), the platform and tool prices and rankings, the market-moves list, and the EU compliance grades. Replace with the client's own partner data"
  - "Adapted for GTM-360: tier thresholds, commission ranges, registration windows, SLA hours, and health-score weights are author defaults. Commission and revenue-share terms are for the client's finance and legal teams to set"
---

# Partner channel operations

## Purpose

Most partner programmes fail in operations, not in recruitment. Partners are signed, nobody knows how to bring them deals, registrations collide with direct reps, and the revenue cannot be reported. This skill sets out the operating system that makes a partner programme measurable and repeatable.

The core rule: recruit fewer partners, enable them properly, register every deal in one place, and report sourced and influenced revenue separately. Activation matters more than the count of partners on paper.

## When to use

- The partner programme exists, but few partners produce pipeline.
- Partner and direct sales claim the same accounts.
- Partner-sourced revenue cannot be separated from direct revenue.
- The company is about to design tiers, a portal, or a deal registration process.
- A partner QBR or review cadence has to be set up.

Route elsewhere when:

- The question is whether to build a partner motion, which partner types to pick, or the economics of the strategy. Use `partner-ecosystem-architect`.
- The question is the handoff between partner and direct teams inside a deal. Use `revenue-handoffs`.
- The question is the CRM build itself. Use `revops-salesforce`.
- The question is the GTM capacity plan. Use `gtm-planning-org-design`.

## Inputs

- The partner types in use or planned, and any existing partner agreements.
- The list of partners, their status, and the last deal each registered.
- The CRM fields that exist for partner tracking, and whether they are filled.
- The direct sales rules for account ownership.
- Current commission or referral terms, and any marketing development funds.
- Partner-sourced and partner-influenced revenue for the last four quarters, if any.

## Procedure

### Step 1: Choose the partner type for each job

The type follows the job the partner does, not the ambition.

| Type | Use when | Usual economics (default, to calibrate) |
|---|---|---|
| Referral | Early programme. Partners have relationships but no sales capacity. | Referral fee on first-year contract value |
| Technology | Shared customer, integration creates combined value | Revenue share or referral on co-sold deals |
| Reseller | Fast distribution in a market or region. Partner owns the customer relationship. | Margin on resold product |
| Implementation | Solution needs set-up or configuration before it works | Project fees to the partner, plus indirect uplift |
| Co-sell | Both teams sell the same accounts | Agreed revenue share or reciprocal fee |
| VAR | Bundled hardware, software, and services | Discount off list, plus project margin |
| Managed service provider | Customer wants the outsourced operation | Wholesale margin, plus managed-service margin |
| Systems integrator | Enterprise, custom requirements, long cycles | Discount plus project margin, often with co-investment |
| Embedded or marketplace | Product extends into another product's ecosystem | Revenue share, referral on co-sold deals |

Start with one or two types that match the motion. Add the others only when the first types have produced pipeline.

### Step 2: Define the ideal partner profile before recruiting

Score each candidate on a 1 to 5 scale across four groups:

- **Strategic fit:** shared customer profile, complementary rather than competing offer, aligned go-to-market motion, and geographic or vertical overlap.
- **Operational readiness:** a dedicated partner or sales team, CRM and deal tracking in place, an existing customer base to cross-sell, and marketing capability.
- **Commitment:** an executive sponsor, willingness to invest in enablement, a history of informal referrals, and motivation beyond commission.
- **Customer overlap:** the share of the partner's customers who fit the client's ICP. Measure this with account mapping (Step 5), not by estimate.

Default bands, to calibrate: 36 to 60 for strategic (tier 1), 24 to 35 for growth (tier 2), 12 to 23 for referral (tier 3), and under 12 not ready. Do not recruit a partner who scores under 12 on the strategic dimensions, however attractive the logo.

### Step 3: Structure the tiers

Three tiers. Promote on performance, not tenure.

- **Tier 1, strategic.** A small number, three to five as a default. Requires a profile score in the strategic band, a named partner manager, a signed joint plan, and a minimum pipeline commitment set by the client. Gets the highest rates, joint marketing funds, priority registration, executive alignment, quarterly reviews, and early roadmap access.
- **Tier 2, growth.** Ten to twenty as a default. Requires a completed certification, a minimum number of registered deals per quarter, and active portal use. Gets standard rates, co-marketing resources, monthly check-ins, and lead sharing.
- **Tier 3, referral.** No cap. Requires a signed agreement and completion of basic product training. Gets referral rates, portal access, collateral, and quarterly updates.

Commission and fund percentages are set by the client. Do not copy them from another programme.

### Step 4: Run deal registration with clear conflict rules

Registration is the process that decides who owns an account when both partner and direct teams are involved. Without it, reps fight and partners stop registering.

**Process:**
1. The partner submits the deal with account name, contact, estimated value, and timeline.
2. The system checks whether the account is already in the pipeline.
3. If it is not, the deal is registered and assigned to the partner.
4. The partner manager reviews within one business day (default).
5. The registration holds for a period set by deal size (default 60 to 120 days). If the deal does not progress, it expires and can be re-registered.

**Conflict rules (defaults):**
- First to register wins, if the registration is inside a seven-day window.
- If the account already has an open direct opportunity, the direct team owns it, unless the partner shows prior relationship with evidence.
- If both sides are actively engaged, the deal becomes co-sell with an agreed split.
- Unresolved conflicts go to the partner manager and sales manager, who decide within 48 hours. After that, an executive decides.

**CRM fields required on the opportunity:** a partner-sourced flag, a partner-influenced flag, the partner record, the partner's contact at the account, the registration identifier and date, the expiry date, the commission rate taken from the tier, the commission amount, and the tier. Set these as required before the opportunity moves past the qualification stage.

### Step 5: Onboard and enable partners

**Onboarding sequence (default, four weeks):**
- Week 1: welcome call, signed agreement, portal access, and product overview.
- Weeks 2 and 3: product certification, ICP and persona training, and competitive positioning. The certification is a scored exercise, not attendance.
- Week 4: joint account mapping to find the first five to ten target accounts, agree the co-sell motion, and write a ninety-day partner plan.
- Weeks 5 and 6: support the first registration, joint calls where needed, and weekly check-ins.

**Ramp targets (defaults to calibrate):** first registration within 60 days, first closed deal within 120 days, certification completed within 30 days, and at least 60% of partners active within 90 days.

**Enablement content the partner needs:** a one-page product summary, an ICP and persona guide, a competitive battlecard, a demo environment, a co-branded slide template, case studies, an ROI calculator, a sales playbook, an objection guide, and a restricted pricing guide. The pricing guide is restricted to certified partners.

Do not expect partners to self-serve. Partners need more enablement than most programmes budget for.

### Step 6: Define the co-sell motions and their rules

Three motions. Name which one applies to each deal at registration.

- **Partner-sourced.** The partner finds the deal, registers it, and introduces the direct team. The direct team runs discovery and the solution. The partner supports the relationship. Full commission applies.
- **Partner-influenced.** The direct team found the deal and invites the partner to add expertise or credibility. The partner joins calls, gives implementation perspective, and builds trust. Reduced commission applies (a default of about half the sourced rate).
- **Co-sell.** Both teams work the same account from joint account mapping. They coordinate outreach, prepare joint proposals, and share a revenue split.

Rules for every co-sell deal: one named lead (the client or the partner), a weekly sync between the account executive and the partner contact on active deals, shared deal notes in the CRM updated by both sides, and an escalation path if the deal stalls.

### Step 7: Attribute revenue correctly

Track two categories and report them separately. Never add them together without saying so.

- **Sourced:** the partner registered the deal, and the first meeting came from the partner's introduction.
- **Influenced:** the direct team originated the deal, and the partner was actively involved in the sales process: joined calls, provided references, or supported the evaluation. A relationship in name alone does not count.

Total partner contribution is sourced plus influenced. Influenced is harder to track, because it depends on reps tagging deals honestly. Enforce the tag in the weekly deal review, and tag at the point of origin, not afterwards.

### Step 8: Score partner health

Score each partner from 0 to 100 on five dimensions. The weights are defaults.

- **Pipeline activity, 35%:** registrations per quarter, pipeline value created, and deals moving through stages.
- **Revenue production, 25%:** closed-won revenue over the trailing twelve months, win rate on registered deals, and average deal size.
- **Engagement, 20%:** portal activity, training and certification completion, event attendance, and responsiveness.
- **Relationship, 15%:** executive sponsor engaged, attendance at reviews, joint planning completed, and escalations (fewer is better).
- **Strategic fit, 5%:** customer profile overlap, product roadmap alignment, and market momentum.

Bands: 80 and above healthy (invest more); 50 to 79 watch (diagnose and coach); below 50 at risk (intervene or exit). Review tier 1 quarterly, tier 2 twice a year, and tier 3 once a year.

Note: this 0 to 100 partner score is a separate field from the deal health score and the account scores in this library. Do not average them.

### Step 9: Run the review cadence

- **Weekly:** the partner manager reviews the registration pipeline (about fifteen minutes) and syncs with sales on active co-sell deals.
- **Monthly:** review partner activity across all tiers, identify inactive partners for outreach or exit, and review the onboarding pipeline.
- **Quarterly, tier 1:** a partner business review. Agenda: revenue against plan (sourced and influenced), the active and stuck pipeline, programme feedback, a refresh of account mapping, the next quarter's target accounts and co-marketing, and an executive alignment on direction and roadmap.
- **Annually:** tier reassignment on performance, a review of commission structure, programme return on cost, and strategic partner planning for the coming year.

## Maturity

Four levels. Move up only when the level below is working.

1. **Fundamentals (months 0 to 6).** One person, a few tools. Define the ideal partner profile, document the partner sales process and deal registration, sign a basic agreement, set up CRM tracking, and recruit and enable the first three to five partners.
2. **Adoption (months 6 to 18).** One or two people and a partner portal. Tiers in place, a content library, reporting and dashboards live, a regular management review, and partner health scoring running.
3. **Optimisation (months 18 to 36).** A dedicated team. Partner insights shape programme decisions, partner messaging is tested, a governance council reviews performance, account mapping is in use, and attribution is trusted.
4. **Acceleration (month 36 onward).** A full partner organisation. Recruit, ramp, and retire partners on economics and impact. Automate registration triage and onboarding where volume justifies it.

Expect six to twelve months from launch to meaningful partner revenue. Track the leading indicators (registrations and pipeline) before the lagging one (revenue).

## Common pitfalls

- **Many partners, none producing.** Measure activation rate, not partner count. Ten active partners are worth more than fifty dormant ones.
- **Sales and partners fight over accounts.** Set registration rules, use first-to-register, and make the economics fair to both sides.
- **Partners do not understand the product.** Invest in certification, demo environments, and regular training.
- **Partner revenue cannot be tracked.** Add the CRM fields and enforce the tags in deal reviews.
- **Equal investment in unequal partners.** Tier them. Invest most in tier 1. Move partners to lower-touch treatment after two quarters of no activity.
- **Partners bring poor-fit deals.** Define qualification for registered deals, reject deals outside the ICP, and train partners on the ICP.

## Output

- The partner type and economics for each partner, with the tier.
- The ideal partner profile and its scoring sheet.
- The deal registration process, its conflict rules, and the CRM field list.
- The onboarding and enablement plan for the first cohort.
- The co-sell rules and the attribution definitions.
- The partner health score and the review cadence.
- The maturity level, with the next step.

## Diagnostic questions

1. How many partners registered a deal in the last ninety days, and how many have never registered one?
2. How many registered deals ended in a conflict with a direct rep, and how long did each conflict take to resolve?
3. Can sourced and influenced partner revenue be reported for the last four quarters, from the CRM alone?
4. Which tier-one partner has a signed joint plan and a named owner on each side?
5. What did the partner programme cost last year, and what partner-attributed revenue did it produce?

## Quality bar

Every partner has a tier, a score, and a named owner. Registration decides every shared account within 48 hours. Sourced and influenced revenue are reported separately, from CRM data. Watch for recruitment without activation, partner revenue reported from memory, unresolved account conflicts, and programmes judged in month three.

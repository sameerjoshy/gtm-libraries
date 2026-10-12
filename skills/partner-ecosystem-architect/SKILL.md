---
name: partner-ecosystem-architect
version: 1.0.0
status: draft-for-review
description: Use to decide whether and how a B2B SaaS company should build a partner ecosystem: what problem partners would solve in the revenue system, which partner types fit the motion and stage, whether the direct motion is ready to be multiplied, how ecosystem-led growth plays fit alongside outbound, inbound, and customer success, and what a 90-day partner plan looks like. Use when someone says partners should be the next motion, when a partner programme is not producing, or when account mapping is being considered. Not for the operational mechanics (see partner-channel-operations).
sources:
  - "Partner ecosystem architect (MIT, Rutger Katz / Neon Triforce): five diagnostic questions, stage-appropriate partner strategy, the three ecosystem-led growth plays (nearbound sales, marketing, and customer success), the ecosystem maturity levels, the partner type architecture by motion, the operator's three-layer model, the account mapping process, partner attribution rules, the signal-based decision rules, and the 90-day programme"
  - "Removed as unverified: all benchmark statistics attributed to research reports and vendor studies, the at-scale revenue figures attributed to public company reports, the per-dollar partner revenue figure from an older industry study, the AI adoption and partner-count forecasts, the market-size and marketplace figures, the tool landscape with prices and merger news, and the 'nearbound' book reference. Treat these as market context to verify, not as inputs"
  - "Corrected: the source's stage bands and partner revenue ranges are kept as planning defaults, not as benchmarks. The source described the same partner-influenced commission as both 'typically 50%' and 'reduced'. This skill states it as a default for the client to set"
  - "Adapted for GTM-360: the stage bands, the investment levels, the 90-day success targets, and the signal thresholds are author defaults to calibrate per client"
---

# Partner ecosystem architect

## Purpose

Partner programmes fail when they start with "let's recruit partners" rather than "what job does a partner do in our revenue system?" The answer decides the partner type, the economics, the enablement investment, and the timeline. This skill makes that answer explicit before anything is built.

Partners multiply what the company already does. If the direct motion is unpredictable, partners bring more unpredictable deals. So the first question is whether the direct engine works well enough to be multiplied.

This skill covers strategy and design. For the operational mechanics (registration, scoring, cadence, CRM fields), use `partner-channel-operations`.

## When to use

- Someone proposes partners as the next growth motion.
- A partner programme exists, but its purpose was never written down.
- The company is deciding between partner types, or between a partner motion and more direct capacity.
- Account mapping with partners is being considered as a sales tool.
- A 90-day ecosystem plan is needed.

Route elsewhere when:

- The question is registration, tiers, onboarding, or partner health scoring. Use `partner-channel-operations`.
- The question is the GTM structure and capacity across functions. Use `gtm-planning-org-design`.
- The question is the handoff between partner and direct teams inside a deal. Use `revenue-handoffs`.

## Inputs

- ARR, growth rate, and GTM headcount.
- The current motion: self-serve, sales-assisted, enterprise, or channel-heavy.
- Typical deal size and sales cycle, by segment.
- Existing partner relationships, formal or informal, and any deals they have referred.
- The direct sales process and its forecast accuracy. A working direct engine is a precondition.
- The reason partners are being considered: distribution, credibility, delivery capacity, new markets, or product stickiness.

## Procedure

### Step 1: Answer the five diagnostic questions

1. **What problem does a partner solve?** Pick one primary: distribution (cannot reach the market directly), credibility (buyers trust a third party), delivery capacity (cannot implement or support at scale), new market (geography, vertical, or segment), or ecosystem stickiness (integrations that raise switching cost). If none fits, do not start a programme.
2. **What is the current motion?** Self-serve points to technology partners and integrations. Sales-assisted points to referral and co-selling partners. Enterprise points to systems integrators and consulting partners with co-delivery. Channel-heavy points to resellers, value-added resellers, and managed service providers.
3. **What is the stage?** Below about €5M ARR, run three to five informal partnerships and no programme. Around €5M to €15M, add a formal referral programme and a first partner hire. Around €15M to €50M, build a tiered programme with co-selling operations. Above about €50M, run an ecosystem-led growth strategy with account mapping at scale and a partner organisation. These bands are defaults.
4. **Does the direct motion work first?** If forecast accuracy is poor, deal stages are inconsistent, or win rates are unknown, fix the direct motion first. Partners will bring more of whatever the sales process already produces.
5. **Who owns it?** A programme without a dedicated owner tends to stall within six months. From about €15M ARR, the owner should be a partner manager, not someone for whom partners are one task among many.

If question 4 fails, the recommendation is to fix the direct motion, not to recruit partners.

### Step 2: Match the stage to the investment

| ARR stage | Partner motion | Investment (default) | Time to first revenue (default) |
|---|---|---|---|
| Below €5M | Informal referrals. Three to five warm relationships. No programme. | Founder time | Not yet measurable |
| €5M to €15M | Formal referral programme. First partner hire. Five to ten partners. | One person | Around 90 to 120 days to a first partner-sourced deal |
| €15M to €50M | Tiered programme, co-selling, account mapping. Fifteen to thirty partners. | Two to three people | Three to six months to pipeline, six to twelve to meaningful revenue |
| €50M to €150M | Ecosystem strategy, a partner organisation, thirty to a hundred partners. | Five or more people | Ongoing; partner revenue becomes a planned share of the target |
| Above €150M | Ecosystem-led growth across the company. Nearbound as an overlay on every motion. | A partner organisation | Partners are a core revenue motion |

### Step 3: Choose the partner type by motion

The right type depends on the motion, not on ambition.

- **Self-serve, product-led buyers.** Start with technology partners (integrations). Add a marketplace and a referral network later.
- **Mid-touch sales, roughly €10K to €50K contract value.** Start with referral and consulting partners. Add co-selling and technology partners.
- **Enterprise sales, above roughly €50K.** Start with systems integrators and consultancies, plus co-selling partners. Add global systems integrators and regional resellers later.
- **Geographic expansion.** Start with regional resellers and local consultancies. Add regional integrators later.
- **Vertical expansion.** Start with vertical specialists and domain experts. Add industry integrators and value-added reseller networks later.
- **Implementation-heavy product.** Start with implementation partners and training partners. Add integrators as the delivery volume grows.

Partner types and their economics are detailed in `partner-channel-operations`, Step 1.

### Step 4: Pick the ecosystem-led growth plays

Ecosystem-led growth is not "more partnerships." It uses partner intelligence to make every motion work better. Choose one play to start, not three.

**Play 1: nearbound sales.** Use partner relationships to warm up accounts and to strengthen active deals.
1. Map account overlaps between your CRM and each partner's (see Step 5).
2. Find accounts where a partner already has a relationship.
3. Ask the partner for a specific introduction.
4. Involve the partner in active deals where their credibility helps.

Test this with your own data. Compare win rate, cycle length, and deal size for partner-involved deals against direct deals in the same segment, before claiming a benefit.

**Play 2: nearbound marketing.** Co-create content and events with partners who share the ICP. Create something neither company could make alone: a joint research piece, a shared webinar, or a framework used by both audiences. Logo swapping and newsletter mentions are not co-creation.

**Play 3: nearbound customer success.** Use partner relationships in shared accounts. Coordinate reviews where both products are in the same account. Use partner usage data as a health signal. Co-sell expansions, where each party sells its own part.

### Step 5: Run account mapping

Account mapping answers the question: which of my target accounts does this partner already know?

1. **Prepare the data.** Export active customers (name, contract value, segment, health), active pipeline (name, stage, value, close date), and target accounts (ICP fit but not yet in pipeline). Remove duplicates first. Many partner submissions turn out to be existing customers.
2. **Share securely.** Use a privacy-preserving account overlap service, or a manual exchange for the first few partners. Share only the segments both sides have agreed.
3. **Map the overlaps.** Three types. Prospect-customer: your target is their customer (the warmest introduction). Customer-customer: a shared customer (a co-expansion opportunity). Prospect-prospect: both are targeting it (coordinate outreach).
4. **Prioritise.** Rank by your deal stage (active pipeline above target list), the depth of the partner's relationship (champion access above casual contact), the combined contract value, and the ICP match for both sides.
5. **Activate.** Ask for a specific introduction, not "can you introduce me to company X." Give the partner context they can use. Record the introduction in the CRM. Follow up within 48 hours.
6. **Measure.** Track the funnel from introduction requested, to introduction made, to meeting booked, to pipeline, to closed won. Conversion by partner shows which partners produce pipeline and which produce noise.

Cadence: refresh the mapping monthly with the top five partners, fully each quarter across all active partners, and review at year end which partnerships produced pipeline.

### Step 6: Set the economics and the attribution

- **Track two categories and report them separately.** Sourced: the partner originated the opportunity and the first meeting came from them. Influenced: the direct team originated it and the partner actively helped it along.
- **Attribution rules (defaults).** First registration wins, with a protection window of around 90 days. The partner must show active involvement, not just a connection. Tag at origin, not retrospectively. Enforce the tag in weekly deal review.
- **Commission (default, to set by the client).** Full rate for sourced, a reduced rate for influenced. Partner commission rates vary widely, so set them from the client's margin and the tier, not from another company's programme.

Economic benchmarks from the source are not reproduced here. Build the client's own baseline from their first four quarters of partner data.

### Step 7: Set the signal-based decision rules

Connect partner metrics to the operating cadence, so that problems trigger a named action.

| Signal | Trigger | Action | Owner |
|---|---|---|---|
| Partner activation below target at 90 days | Monthly partner review | Diagnose: enablement gap, wrong partner, or missing incentive | Partner manager |
| Tier-one pipeline below the quarterly target for two months | Dashboard alert | Joint executive call within a week; reset the target or escalate | Partner lead and CRO |
| Mapping finds many high-fit overlaps (default: more than 20) | Quarterly mapping refresh | Request introductions for the top ten within two weeks | Partner manager |
| Partner-sourced win rate well above direct (default: 15 points) | Quarterly review | Invest more: enablement, co-marketing, mapping frequency | Partner lead |
| Direct and partner reps work the same account | Registration conflict alert | Resolve within 48 hours | Partner manager and sales manager |
| New integration goes live | Product release | Enable partners on it and co-market within 30 days | Partner manager and product |

### Step 8: Run the 90-day programme

**Weeks 1 to 4: strategy and foundation.**
- Week 1: score current partner maturity, list every existing partnership (formal and informal), identify partners already referring deals, and check whether the direct motion is ready.
- Week 2: answer the five diagnostic questions, define the partner types needed, write the ideal partner profile (see `partner-channel-operations`), and set six-month and twelve-month targets.
- Week 3: design the tiers, the economics, and the attribution rules. Define the partner data needed in the CRM.
- Week 4: identify the first five partners, prioritising those already referring informally. Create a minimum enablement pack (one-pager, ICP guide, registration form). Sign the first three agreements. Run the first mapping session with the top two partners.

Output: a partner ecosystem blueprint with strategy, architecture, economics, and the first five partners.

**Weeks 5 to 8: activate and enable.**
- Weeks 5 and 6: onboard the first five partners, run product and ICP training, run joint mapping with each, and set ninety-day targets per partner.
- Weeks 7 and 8: support the first registrations, co-sell the first two or three opportunities, install registration tracking, and set up the partner pipeline dashboard.

Output: five active partners with account maps and the first pipeline.

**Weeks 9 to 12: operate and scale.**
- Weeks 9 and 10: review the first partner pipeline (which partners produce, which do not). Recalibrate the profile. Adjust enablement from partner feedback. Identify the next five partners.
- Weeks 11 and 12: add partner pipeline to the weekly deal review, add a partner panel to the revenue dashboard, install the monthly partner review, hold the first tier-one review, and report to leadership with pipeline created, deals in progress, and a six-month projection.

Success targets (defaults):

| Measure | Baseline | Ninety-day target | Six-month target |
|---|---|---|---|
| Active partners producing pipeline | Current count | Five | Ten to fifteen |
| Partner-sourced pipeline | Often unknown | Set from the client's contract values | Ten to fifteen percent of total pipeline |
| Partner activation (active within 90 days) | Not applicable | Above 60% | Above 70% |
| First registered deal | Not applicable | Within 60 days | Five or more registered deals |
| Accounts mapped with top partners | None | Top two | Top five |

## Choosing how far to go

Start with the smallest motion that answers the question. A company with three partners should make those three succeed before recruiting more. Case studies from a few successful partners make the next recruitment easier than a larger list of inactive ones. Scale only what has produced pipeline at small size.

Use `partner-channel-operations` for the operating detail once the strategy is agreed.

## Output

- The diagnostic answers, with the recommendation: build, defer, or fix the direct motion first.
- The stage, the investment level, and the expected timeline.
- The partner types chosen, with the reason for each.
- The ecosystem-led growth play chosen to start, with its test.
- The account mapping process and cadence.
- The attribution and economics rules, for the client to set.
- The signal rules and the 90-day plan with targets.

## Diagnostic questions

1. Which problem would a partner solve that direct sales cannot, and how would you know it had been solved?
2. Is the direct motion's forecast accurate enough to be multiplied?
3. Which partners already refer deals informally, and what did those referrals produce?
4. Who owns the programme, and how many hours a week do they have for it?
5. What partner-influenced revenue would you need to see in twelve months to call the programme a success?

## Quality bar

The strategy names the job partners do, the stage fits the investment, and the direct motion has been checked first. The 90-day plan has owners and measures. Watch for recruitment before a job is defined, benchmark percentages used as targets, partners recruited faster than they can be enabled, and a programme with no owner.

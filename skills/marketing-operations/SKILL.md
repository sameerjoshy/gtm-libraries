---
name: marketing-operations
version: 1.0.0
status: draft-for-review
description: Use to make marketing accountable for pipeline: shared lifecycle definitions, dual-axis lead scoring (fit and engagement) with quarterly calibration and governed versions, the marketing-to-sales handoff SLA with rejection reasons, lead recycling, attribution (sourced, influenced, and a multi-touch model), campaign and UTM taxonomy, and the maturity path. Use when sales says leads are poor or revenue cannot be attributed to campaigns. Covers marketing operations, not brand, creative, or ICP methodology (see icp-builder), and not the CRM build (see the platform skills).
sources:
  - "Marketing operations (MIT, Rutger Katz / Neon Triforce), lead lifecycle stages, dual-axis scoring with weekly decay, quarterly calibration with holdout, scoring versioning and rollback, MQL to SQL SLA and rejection categories, lead routing models, lead recycling, W-shaped attribution, sourced and influenced definitions, UTM governance, dark funnel, shared definitions, maturity levels"
  - "Percentages and external statistics in the source (acceptance benchmarks, channel mixes, dark-funnel shares, vendor and survey figures) are treated as starting points or context only. The AI-scoring case study is removed as an unverified anecdote"
  - "Adapted for GTM-360: the W-shaped weights are an author default; the decay half-life and rollback thresholds are defaults to test; the SPICED fit matrix and the campaign taxonomy references are not in this library and are not relied on"
---

# Marketing operations

## Purpose

Marketing operations makes marketing measurable against pipeline and revenue. It does not do brand or creative work. It builds the systems that decide what counts as a lead, how leads are scored, how they are handed to sales, how results are attributed, and how the two teams agree on the definitions.

Without shared definitions, the handoff cannot be measured, and without measurement, the argument between marketing and sales never ends.

## When to use

- Sales says the leads are poor, and marketing says sales is not following up.
- The team cannot say which campaigns produced pipeline.
- MQL definitions differ between regions or teams.
- Lead scoring has not been reviewed in a long time, or was changed without a record.
- A marketing-to-sales SLA is needed, or the current one is ignored.

Route elsewhere when:

- The question is the ICP itself. Use `icp-builder`.
- The question is routing rules in detail. Use `lead-routing-design`.
- The question is the funnel maths. Use `revenue-metrics`.
- The question is enrichment of lead records. Use `data-enrichment`.
- The question is which accounts to target. Use `prospect-list-building` or `abm-strategy-planner`.

## Inputs

- The current lifecycle definitions, and how each team applies them.
- Lead records for the last 90 days, with source, scores, status, and outcome.
- The scoring model in use, its version history, and who owns it.
- Campaign and UTM data, and the budget per campaign.
- The CRM lead source and opportunity fields, and how they are populated.
- Any existing SLA between marketing and sales, and its record of compliance.

## Procedure

### Step 1: Agree the lifecycle definitions

Write one definition per stage, and get both teams to sign it.

- **Subscriber:** an email has been captured, with no validation yet.
- **Lead:** the email is confirmed or enriched, and basic company data is valid.
- **Marketing-qualified lead (MQL):** meets the engagement and fit criteria.
- **Sales-accepted lead (SAL):** reviewed and accepted by sales. Tracked as pipeline from this point.
- **Sales-qualified lead (SQL):** in an open opportunity, with discovery scheduled or done.

If the definitions differ by region or team, the handoff cannot be measured. Fix that first.

### Step 2: Score on two separate axes

Mixing "is this the right customer" with "are they interested now" produces scores that do neither job well. Build two independent scores.

**Fit score (account level, 0 to 100).** Company size, geography, industry match, technology signals, and growth-stage fit.

**Engagement score (behaviour level, 0 to 100).** Website visits, email clicks (not opens), depth of content consumed, event attendance, and trial activation where a trial exists.

Example rule: an MQL is a fit score of at least 40 and an engagement score of at least 30. These are starting values to test, not standards.

This split routes "right customer, wrong time" and "active but wrong fit" differently. Both are cheaper to find in the scores than in sales calls.

**Decay.** Engagement fades. Use a half-life, such as 30 days: a score is half its peak after 30 days without activity, and a quarter after 60. Without decay, last year's activity keeps routing stale leads.

### Step 3: Calibrate quarterly, with evidence

Every quarter:

1. Pull the MQLs from the last 90 days, and record each outcome: accepted, rejected, recycled, converted to SQL, or won.
2. Check which scoring factors predicted wins, and which produced false positives, meaning high scores that were rejected or churned.
3. If volume allows, hold back 10 to 15% of inbound on the current model and test a challenger for 30 days. Compare acceptance, SAL rate, and close rate. The source requires at least 500 MQLs per quarter for this; below that, use the smaller test in Step 4.
4. Adjust the weights toward the factors that predict outcomes. Do not change a weight on a sample under 100 MQLs per tier, since the result will not be reliable.
5. Track the SAL rate over time. A falling trend is an early sign that the model is decaying, even before the quarter ends.

### Step 4: Govern the scoring model

Changes to scoring are the most common hidden cause of a broken pipeline. Put these controls in place.

- **One owner.** One named person approves every change.
- **Versions.** Each model has a version number, a date, and a note on what changed. Never edit a live model in place.
- **Staged rollout.** A new version goes to 10 to 20% of inbound for about a week, then 50%, then 100%. Compare acceptance against the previous version at each step.
- **Rollback rule.** Roll back, and write a post-mortem, if acceptance falls more than about 10% below the previous model, if rejections change by more than about 15%, or if inbound quality falls for three or more days in a row. These thresholds are defaults to test.
- **Monthly review.** Plot the SAL rate, the rejection rate, and the lead-source mix. Investigate a downward trend before the quarter-end calibration.

### Step 5: Set the marketing-to-sales SLA in writing

Each side commits to something specific.

**Marketing commits to:**

- A stated number of MQLs per month, meeting the scoring criteria.
- Complete data on each lead: name, email, company, title, scores, and source.
- Delivery of each MQL to sales within one business hour.
- A weekly report of rejection reasons.
- Attribution clarity within five working days of month end.

**Sales commits to:**

- Reviewing each MQL within 24 hours, and accepting or rejecting it.
- Recording every rejection with a reason from a fixed list: bad fit, low intent, wrong timing, duplicate, or wrong role.
- Following up each SAL within four hours.
- Weekly pipeline updates on the leads passed to them.
- Quarterly feedback on wins and losses.

Reading the acceptance rate:

- A healthy acceptance rate sits roughly between 60 and 80%. The source's range.
- Below 50%: the scoring is broken, or sales and marketing define the MQL differently.
- Above 85%: the threshold is too low, and unqualified leads are passing.
- Acceptance rises for niche products, and falls for high-value deals where the fit bar is stricter.

Speed to first contact: target a median under four hours, from capture to first sales contact. The source's research on speed is older and mostly from a single study, so use it as direction. Measure the client's own figures.

If either side breaks the SLA, the cause is discussed on the record. If sales ignores MQLs, they recycle and the budget should move. If rejections exceed about 70%, the scoring is audited.

### Step 6: Recycle leads that are not ready

Not every rejected lead should be discarded.

- **Disqualify (remove):** no budget for 12 months or more, a competitor in use and working, no role in buying, or a timeline beyond 18 months.
- **Recycle (nurture):** not disqualified, just not now. Mark it as on nurture hold, contact it on a one- to two-week cadence, and re-score after 60 days. Re-activate it if engagement returns.

The source cites reactivation of 8 to 15% within six months, when contact is tied to a trigger event. Treat that as a hypothesis, and measure it.

### Step 7: Build the attribution model

**Single-touch models mislead.** First-touch credits content and search and ignores the middle of the journey. Last-touch credits sales outreach and ignores awareness. Linear treats a first visit and the fifteenth visit as equal. None of them describes the truth alone.

**Multi-touch model.** The W-shaped model in the source gives credit to four moments:

- First touch: what brought the buyer in. Default share 30%.
- Lead creation: what made them raise their hand. Default share 20%.
- Opportunity creation: what triggered the deal. Default share 30%.
- Close: the last marketing touch before the buy. Default share 20%.

These shares are an author default. Test them against the client's own deals, and document the choice.

Example: a LinkedIn ad (first touch), blog reads (middle, no credit under W-shape), a webinar that produced the MQL (lead creation), an email nurture sequence that created the opportunity (opportunity creation), and a retargeted ad before the close at 95,000. Credit under the default shares: 28,500 to the LinkedIn ad, 19,000 to the webinar, 28,500 to the email nurture, and 19,000 to the retargeting ad. Blog reads get nothing, which is a known limit of this model.

**Two definitions, both needed.**

- **Sourced:** an MQL created by marketing scoring, accepted by sales. Lead generation.
- **Influenced:** closed revenue where the account had any marketing touch. Pipeline development.

Sourced is usually a minority of pipeline, and influenced is usually a large majority in B2B. Each serves a different audience. Report both, and label them.

**Standard UTM tags.** Use four: source (channel type), medium (media type), campaign (a structured identifier), and content (the variant). Limit the campaign values to a fixed number per quarter. Uncontrolled campaign values multiply quickly and make attribution unusable. Every touch should trace back to a budget line.

**Dark funnel.** A share of pipeline has no tracked source: word of mouth, direct visits, and research that was never tracked. The source gives 25 to 45% as a practice estimate. Measure the client's own share, add a "how did you hear about us" field to forms, and check a sample of closed deals by asking the buyer.

**Self-reported sources** are often wrong. A sales rep may claim a deal, though the contact was in a nurture sequence three weeks earlier. Use the multi-touch data, not the source field alone.

**Multi-device research.** A buyer may research on a phone and buy on a laptop. Match on email, not cookies, and accept that some touches will always be missed.

### Step 8: Run campaign operations

Use one naming convention, such as channel, year, quarter, segment, and offer, carried from the marketing plan into the CRM campaign, the attribution, and the budget.

Report every campaign in four layers, in this order:

1. **Volume:** reach.
2. **Quality:** MQL and SAL rates.
3. **Pipeline:** influenced pipeline.
4. **Revenue:** attributed revenue.

A campaign can look strong on volume and weak on quality. The layers exist so that this is visible.

### Step 9: Allocate budget with three inputs

Blend three measures: the historical return on each channel, the pipeline each channel contributes, and the strategic goals. Avoid putting most of the budget into one channel, because it creates concentration risk.

The source's channel mix (outbound, inbound, paid, events and partners, product-led) is an example for one kind of company. Do not adopt it without the client's own return data.

### Step 10: Use customer interviews as marketing input

The most useful input for marketing is often the least used: what customers say when asked directly. Sales and customer success hear this every day, and it rarely reaches the scoring model or the campaign targeting.

A practice-based approach: eight to twelve structured interviews a quarter with current customers, across company sizes. They give three things marketing can use: the buyer's own words for ad copy, the pain priorities that should set the scoring weights, and the decision criteria that test the engagement model. Method detail is in `icp-builder`.

### Step 11: Know the maturity level

- **Level 1, manual.** No scoring, manual routing, no SLA, attribution by guesswork. Symptom: each side blames the other.
- **Level 2, basic.** One-axis scoring, automated routing, first-touch attribution only, SLAs written but not enforced. Symptom: numbers exist but nobody trusts them.
- **Level 3, operational.** Two-axis scoring, calibrated each quarter, SLAs enforced with escalation, multi-touch attribution, campaign naming mostly followed, and feedback loops in use. Symptom: the team knows what works.
- **Level 4, strategic.** Predictive scoring, full attribution, budget adjusted in near real time, pipeline forecast three to six months ahead. Symptom: marketing is a growth engine, not a cost.

Aim for Level 3 within about a year. Level 4 usually needs a large team. Do not aim for it without that capacity.

## Output

- The agreed lifecycle definitions, signed by both teams.
- The scoring model: both axes, the decay rule, the version, and the calibration results.
- The SLA in writing, with the acceptance range and the rejection categories.
- The attribution model: the multi-touch shares chosen, the sourced and influenced definitions, and the UTM standard.
- The campaign dashboard in four layers.
- The maturity level today, with the next step.

## Quality bar

Marketing and sales share the same definitions. The scoring model has a named owner, versions, and a record of changes. The handoff is timed, and every rejection has a reason. Attribution is reported with its method stated. Watch for an MQL definition that differs by team, scores that are edited in place, campaign values that multiply, and attribution reported without its method.

---
name: paid-account-audit
version: 1.2.0
description: "Use when auditing a search or social paid media account at depth for a graded, read-only recommendation list. Classifies search terms into intent tiers, separates rank pressure from budget pressure before recommending a change, grades product listings for kill, downgrade, or promote, gates automated-campaign changes on maturity and asset coverage, checks tracking health and the primary conversion metric, and reads video creative through hook and hold rates. Never changes the account; the team applies each recommendation itself. Not for planning a new campaign (see `paid-campaign-plan`) or for the LinkedIn-specific audit (see `linkedin-ads-audit`)."
---

# Paid account audit

## Purpose

A paid account that is not audited tends to drift. Wasted spend hides in search terms, budgets are raised for a rank problem, and creative that has died keeps running. This skill audits the account at depth and returns a graded list of recommendations. It does not change anything. The team applies each change itself.

## When to use

- A paid search or social account is underperforming, and the team wants to know why.
- Spend has risen and results have not.
- A new owner inherits an account and needs an honest read.

Route elsewhere when:

- The question is a new campaign. Use `paid-campaign-plan`.
- The question is LinkedIn specifically. Use `linkedin-ads-audit`.
- The question is one campaign's quality score. Use `paid-search-quality-diagnosis`.
- The question is whether an agent may write to the account. Use `paid-account-change-safety`.

## Inputs

- Search term or query reports, with spend, clicks, and conversions.
- Keyword and campaign settings, including bid strategy and budget.
- Product feed or catalog data, if the account runs product ads.
- Automated campaign settings and asset coverage, if used.
- Tracking and event configuration, and the conversion actions counted.
- Creative performance, with video hook and hold figures where available.

## Procedure

1. **Check tracking health first.** Confirm the conversion actions counted are the ones the business values, and that event matching works. An audit built on broken tracking is wrong.
2. **Set the primary conversion metric** for the account type. A lead-generation account and a sales-led account should not be judged on the same metric.
3. **Classify search terms into intent tiers,** from purchase-ready queries down to unrelated ones. Quantify the spend on each tier. Spend on the lowest tiers with no conversions is wasted spend, and it goes into the negative list recommendation.
4. **Separate rank pressure from budget pressure.** Before recommending a budget change, check whether the campaign loses impressions to budget or to rank. Raising budget fixes only the first.
5. **Grade product listings,** if used: kill listings that spend without return, downgrade listings with weak return, and promote listings that return well at low spend.
6. **Gate automated-campaign changes.** Do not recommend structural changes to an automated campaign until it has matured and has enough asset coverage. Compare its return with the search campaigns on the same measure.
7. **Apply Pareto analysis to ads.** Identify the small share of ads producing most of the results, and the ads consuming spend with little return.
8. **Read video creative** through hook and hold rates, where available. A low hook rate points to the opening. A low hold rate points to the body.
9. **Grade the account** on each area, with the evidence, and rank the recommendations by effect on the primary metric.

## Output

- A graded report for each area, with evidence.
- A prioritized list of recommendations, each with the expected effect and the person who should apply it.
- A note on any area that could not be assessed, and why.

## Quality bar

Tracking is checked before results are judged. Budget recommendations follow a rank-versus-budget check. Every recommendation cites its evidence. The audit changes nothing in the account. Watch for a budget raised on a rank problem, a conversion metric that does not match the business, and an automated campaign restructured before it has matured.

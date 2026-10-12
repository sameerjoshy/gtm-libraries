---
name: paid-automated-campaign-structure
version: 1.1.0
description: "Use to structure or troubleshoot an automated paid campaign that serves across the platform's inventory from a set of asset groups and audience signals. Covers splitting asset groups by product line or segment, filling every asset slot with a deliberately chosen real video, judging new groups only after a settling period, and guarding against the automated campaign cannibalising brand search that a dedicated campaign already covers at a better cost. Not for search-only campaigns (see paid-search-budget-reallocation) or for the account-wide audit (see paid-account-audit)."
---

# Paid automated campaign structure

## Purpose

An automated campaign serves across many placements from a set of inputs the team supplies: asset groups, copy, images, video, and audience signals. Delivery quality depends on those inputs as much as on the platform's own targeting. A single asset group that tries to speak to every product or buyer cannot be coherent to any of them. This skill fixes the structure first, then the inputs, then the cannibalisation risk.

## When to use

- An automated campaign is underperforming, and the team suspects its inputs.
- A new automated campaign is being set up across product lines or segments.
- Brand search is converting through the automated campaign at a worse cost than a dedicated brand campaign.

Route elsewhere when:

- The campaign is search-only. Use `paid-search-budget-reallocation`.
- The question is the whole account. Use `paid-account-audit`.
- The question is whether an agent may change the campaign. Use `paid-automation-controls`.

## Inputs

- The list of products, product lines, or buyer segments the business sells to.
- The asset groups in place, with their assets and each asset's performance label.
- Video assets in place, and whether any are auto-generated.
- Brand search coverage: whether a dedicated brand campaign exists, and its cost per conversion.
- Search term insights for the automated campaign.

## Procedure

1. **Split asset groups by product line or segment first.** One group serving every product or buyer is a structural problem, and no extra copy fixes it. Name the product or segment each group exists for.
2. **Fill every asset slot the platform offers,** not only the minimum. Include headlines, long headlines, descriptions, and images and video across horizontal, square, and vertical formats. A group short on assets or asset variety has a lower performance ceiling, whatever its targeting.
3. **Upload a real video for each group,** chosen deliberately. If a group has none, the platform assembles one from other assets. Treat that as a fallback accepted by default, and replace it.
4. **Give new or heavily changed groups a settling period** before judging them. As a default, check after about two weeks, not two days. Do not restructure on early volatility, because that resets the learning the change needed.
5. **Clear weak assets as a standing queue.** Each asset labelled low is replaced with a named candidate. Replacing one asset is cheaper than restructuring a group later.
6. **Check brand cannibalisation.** If branded queries convert through the automated campaign at a worse cost than a dedicated brand campaign already covering them, the demand is not new. Exclude the brand terms from the automated campaign once that pattern is visible.
7. **Read search term insights as a search terms report.** Clicks with cost and no conversions are negative candidates. Record them, and apply them through the route the platform provides.

## Output

- The asset group structure, with the product or segment each group serves.
- A fill list for each group: missing asset types, and each weak asset with its named replacement.
- The settling-period review date for each new or changed group.
- The brand cannibalisation finding, with the cost comparison, and the exclusion recommendation if it holds.
- The negative candidates from search term insights.

## Quality bar

Every group maps to one product or segment. Every group has a deliberate video. No group is judged inside its settling period. Brand cannibalisation is checked wherever a dedicated brand campaign exists. Watch for one group covering the whole catalog, auto-generated video accepted by default, and a group restructured on its first few days.

---
name: paid-search-quality-diagnosis
version: 1.2.0
description: "Use when paid search keywords are expensive relative to competitors, ads are not showing as expected, or someone asks why ads are not showing without a budget explanation. Treats the keyword quality score as a diagnostic, not a target, breaks it into its three components (expected click-through rate, ad relevance, and landing page experience), weights the fix list by spend, and routes each below-average component to a different fix. Not for the budget envelope (see `paid-search-budget-reallocation`) or the forecast math (see `paid-search-unit-economics`)."
---

# Paid search quality diagnosis

## Purpose

When paid search costs are high or ads stop showing, teams often answer with a vague instruction to improve relevance. That does not say what to fix or in what order. This skill uses the keyword quality score as a diagnostic to find which of three components is holding a keyword back, then ranks the fixes by how much money each keyword is spending.

## When to use

- Cost per click is high compared with what the team expects or sees from competitors.
- Ads are showing less often than the budget and bids suggest they should.
- A campaign is spending well but returning poor results on specific keywords.

Route elsewhere when:

- The question is the budget split across campaigns. Use `paid-search-budget-reallocation`.
- The question is what the forecast implies. Use `paid-search-unit-economics`.
- The question is whether the account is safe to change. Use `paid-account-change-safety`.

## Inputs

- The keyword list with spend, clicks, conversions, and the quality score and component ratings for each.
- The ad groups and the ads they contain, with the landing page each one sends traffic to.
- The search terms that triggered each keyword, where available.
- The minimum volume the team treats as reliable for diagnosis.

### The three components

- **Expected click-through rate:** how likely the ad is to be clicked for this query. Below average means the ad is not compelling enough for the query it shows on.
- **Ad relevance:** how closely the ad matches the query. Below average usually means the ad group covers too many themes, so the ad and the query have drifted apart.
- **Landing page experience:** how well the page serves the visitor who clicked. Below average means the page does not deliver what the ad promised, or is slow or hard to use.

Each component has its own cause and its own fix. Do not apply one generic fix to all three.

## Procedure

1. **Treat the score as a diagnostic.** Do not optimize toward it or report it as a headline metric. It exists to show which component is weak.
2. **Set the reliability threshold.** Exclude keywords below the minimum volume, because their ratings are not stable enough to act on.
3. **Weight by spend.** Sort the remaining keywords by spend. A below-average component on a keyword that spends heavily matters more than the same rating on a keyword that barely spends.
4. **Route each below-average component:**
   - Expected click-through rate: rewrite the ad headline and description to match the specific query and its intent.
   - Ad relevance: split the ad group so that each group covers one theme, and rebuild the ads for that theme.
   - Landing page experience: change the page so its first screen delivers the promise in the ad, and fix speed or usability problems that stop visitors staying.
5. **Check the search terms** that trigger expensive keywords, and add negative terms for queries that never convert.
6. **Set a re-check date** for each change, and judge it on the component rating and the cost per click for that keyword.

## Output

- The keyword list, ordered by spend, with the weak component for each.
- The fix for each below-average component, with the reason it applies.
- Negative terms proposed from search terms, if any.
- The re-check date for each change.

## Quality bar

Every fix names the component it addresses. Keywords below the reliability threshold are excluded. The order is set by spend. The score is not reported as a target. Watch for one generic "improve relevance" instruction, fixes applied to the cheapest keywords first, and a landing page change judged on the score rather than on conversions.

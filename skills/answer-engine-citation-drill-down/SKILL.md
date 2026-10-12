---
name: answer-engine-citation-drill-down
version: 1.0.0
status: draft-for-review
description: Use when a team wants to know which content shapes AI-generated answers in its category, why a competitor is cited in comparison answers, and where content effort should go to earn mentions. Works top-down in three levels: the domains that co-occur with the brand in AI answers, the specific pages driving those citations, and the full answers themselves. Ends in a ranked hit-list of content patterns and the places the brand can plausibly earn a mention. Not for tracking the brand's visibility over time (see answer-engine-visibility-tracking).
sources:
  - "AEO citation drill-down (MIT, Yahav Fuchs): the three-level investigation (domains, then URLs, then full answers), the rule never to stop at the domain level, the classification of co-occurring domains by type (review platform, competitor, news, or community), and the output of a ranked content hit-list"
  - "Removed: the named AI answer engines, the named monitoring tool, and the example citation counts in the source. The method is restated for any answer engine"
  - "Adapted for GTM-360: the rule that a content pattern is recommended only if the same pattern appears across several answers, not one, is an author default"
---

# Answer engine citation drill-down

## Purpose

AI answer engines cite sources, and those sources shape how a category is described. A team that does not know which sources are cited cannot know where its content effort would change the answer. This skill works from the domains down to the full answers, so the content plan is based on what is actually cited.

## When to use

- A team wants to know which sources AI answers cite about its category.
- A competitor appears in comparison answers where the brand does not, and the team wants to know why.
- Content effort for answer-engine visibility needs to be directed.

Route elsewhere when:

- The question is the brand's visibility over time. Use answer-engine visibility tracking (not yet merged).
- The question is a drop in organic clicks. Use `organic-decline-diagnosis`.

## Inputs

- A set of AI answers in the category, collected for a stated period, including answers that mention the brand and answers that do not.
- The brand's list of competitors.
- Any content the brand already publishes, with its URLs.

## Level one: domains

1. List the domains that co-occur with the brand in the answers, with the number of citations each receives.
2. Classify each domain by type: review platform, competitor, news, community, or the brand itself.
3. Read the shape. A review platform appearing across many answers about the brand tells the team which kind of property owns the category's reputation.

## Level two: pages

1. For the top domains, list the specific pages cited.
2. Note the page type and the claim each page supports in the answer.
3. Identify the pages the brand could plausibly earn a mention on, and the pages it could influence through its own content.

## Level three: full answers

1. Read the full answers in which a competitor is cited but the brand is not.
2. Note what the cited pages say that the brand's pages do not.
3. Note the question the answer was responding to, and whether the brand has a page that answers it.

## The hit-list

Rank the content patterns by how often they appear across the answers. A pattern is recommended only if it appears in several answers, not one. For each recommended pattern, state:
- the pattern,
- the answers it appears in,
- where the brand can earn a mention,
- the content the brand would need to create or change.

## Procedure

1. **Collect the answers** for the period, and record the period.
2. **Run level one,** classifying the domains.
3. **Run level two,** listing the pages behind the top domains.
4. **Run level three** on the answers where a competitor is cited and the brand is not.
5. **Write the hit-list** with the patterns ranked and each one's evidence.
6. **Check plausibility:** for each recommendation, confirm the brand can actually publish or earn the placement.

## Output

- The domains by type, with citation counts.
- The pages behind them, and the claims they support.
- The ranked content hit-list, with evidence and plausibility for each item.

## Quality bar

The investigation goes all three levels, and no recommendation rests only on domain-level data. A pattern counts only if it appears across several answers. Each recommendation names where the brand can earn a mention. Watch for a strategy built on one answer, domain counts treated as page evidence, and recommendations the brand cannot realistically earn.

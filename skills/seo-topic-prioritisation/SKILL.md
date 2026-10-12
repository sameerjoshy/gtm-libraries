---
name: seo-topic-prioritisation
version: 1.0.0
status: draft-for-review
description: "Use to turn a shaped list of SEO topics into a build order. Scores each topic on six dimensions (commercial intent, fit with the ideal customer, feasibility of ranking, effort, leverage from existing authority, and adjacency to existing wins), sorts topics into three tiers, and puts quick wins first so the content roadmap proves itself early. Use when a team asks what to build first. Not for finding topics (see seo-topic-research) or for checking a single keyword's ranking reality (see seo-serp-qualification)."
sources:
  - "Topic prioritisation (MIT, Sam Dunning): the six scoring dimensions (commercial intent, ICP alignment, ranking feasibility, effort, authority leverage, and adjacency to wins), the three tiers, the rule that quick wins come first, and the point that the order of the list matters as much as its contents"
  - "Removed: the command invocation, the named analytics tool and its volume and difficulty outputs, and the pipeline phase numbering. The scoring scales are restated as a method"
  - "Adapted for GTM-360: the tier thresholds and the weight of each dimension are author defaults to set with the business before scoring. The rule that the company's commercial priorities are read before scoring is kept from the source"
---

# SEO topic prioritisation

## Purpose

A list of good SEO topics is not a plan. Building the hardest topics first stalls a content roadmap before it proves anything. This skill scores each topic on six dimensions, sorts them into tiers, and sets a build order that starts with the quickest and most commercially useful wins.

## When to use

- A shaped topic list needs an order.
- A content roadmap is being planned and the team does not know where to start.
- A new topic is proposed and needs placing in the existing order.

Route elsewhere when:

- The question is finding topics. Use `seo-topic-research`.
- The question is whether a keyword can be won in the search results. Use `seo-serp-qualification`.

## Inputs

- The shaped topic list, with search volume, keyword difficulty, and the format for each topic.
- The company's commercial priorities: which products, segments, and outcomes matter most now.
- The ideal customer profile.
- The site's existing content and which pages already perform.

## The six dimensions

Score each topic from one to five on each dimension:

1. **Commercial intent.** How close the topic is to a buying decision.
2. **ICP alignment.** How well the topic matches the ideal customer's problem.
3. **Ranking feasibility.** How realistic it is to rank, based on the search results. Use the qualification step for this.
4. **Effort.** How much work the content needs. A low effort score is better.
5. **Authority leverage.** How much the site's existing pages on related topics help this one.
6. **Adjacency to wins.** How close the topic is to content that already performs.

## Tiers

- **Tier 1:** high commercial intent, strong fit, realistic ranking, and modest effort. Build first.
- **Tier 2:** worthwhile but with higher effort or weaker ranking prospects. Build once Tier 1 is live.
- **Tier 3:** lower intent or weaker fit. Keep on the list, but do not build without a reason.

Thresholds for the tiers are defaults to set with the business.

## Procedure

1. **Read the commercial priorities** before scoring. A topic that matches a priority scores higher on commercial intent.
2. **Score each topic** on the six dimensions.
3. **Compute a total** using the weights agreed with the business.
4. **Assign tiers** using the thresholds.
5. **Put quick wins first:** Tier 1 topics with high adjacency to existing wins and low effort.
6. **Write the build order,** with the reason for each position.
7. **Review the order** after the first quarter, and move topics that did not perform as expected.

## Output

- The scored topic list, with each dimension's score.
- The tiers, and the build order with reasons.
- The quick wins, marked.

## Quality bar

Scores come from the stated dimensions, not from the topic's volume alone. The build order starts with quick wins. Commercial priorities are read before scoring. Watch for a list sorted by search volume, high-effort topics placed first, and no review after launch.

---
name: community-post-preflight
version: 1.0.0
description: "Use immediately before a brand posts anything, or shares a link, in an online community forum, to check whether the post is allowed and likely to stay up. Runs four checks in order (the community's rules, whether it is restricted or private, whether the link has been shared before, and the community's own posting norms), then gives a go or no-go verdict with the specific rule at issue and an alternative where one exists. Not for judging a comment's tone (see community-comment-safety)."
---

# Community post preflight

## Purpose

Most brand removals and bans in community forums come from a post that broke a rule nobody checked. The check is cheap and the cost of skipping it is high. This skill runs the four checks every time, quotes the rule that governs the post, and gives a verdict the poster can act on.

## When to use

- Immediately before any post or link share in a community forum.
- Before a campaign post is scheduled to go into a community.
- When someone asks whether a post will be removed.

Route elsewhere when:

- The question is whether a comment's tone is safe. Use `community-comment-safety`.
- The question is which communities to join. Use `community-channel-research`.

## Inputs

- The post or link to be shared, and the community it goes to.
- The community's rules, its type (public, restricted or private), and its wiki or pinned posts.
- The submission history of the link, to check for duplicates.
- Any campaign schedule the post belongs to.

## The four checks, in order, every time

1. **Rules.** Read the community's rules in full. A rule violation gets a post removed at once, and repeat removals flag the account.
2. **Community type.** If the community is restricted or private, stop. Only approved members can post.
3. **Duplicate link.** Check whether the link has already been submitted to the community. A duplicate post can get the account banned.
4. **Wiki and pinned norms.** Read the community's wiki or pinned posts. Many communities keep their real posting norms there, such as flair requirements, promotion windows, or minimum account history.

## Verdict

- **Go,** with any constraint that applies: a required format, an allowed thread type, or a timing window.
- **No-go,** with the exact rule that blocks the post and an alternative where one exists, such as a comment in an existing discussion or a post in a periodic promotion thread.

## Procedure

1. **Run the four checks** and record the result of each.
2. **Quote the rule** that governs the post, word for word.
3. **Give the verdict** and the constraints or the alternative.
4. **If the verdict is no-go,** do not post. Choose the alternative or drop the post.
5. **Record the check** with the date, so the same community can be re-checked before the next post.

## Output

- The four check results.
- The go or no-go verdict, with the rule quoted.
- The constraints, or the alternative.

## Quality bar

All four checks run every time. The verdict quotes the rule. A no-go is never overridden in the moment. Watch for a post made because the community was checked last month, a duplicate link shared without a reason, and a restricted community posted to anyway.

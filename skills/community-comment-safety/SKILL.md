---
name: community-comment-safety
version: 1.0.0
status: draft-for-review
description: Use to review or write a comment that touches a brand in an online community forum, before it is posted. Runs a six-point check (the community's rules, its self-promotion policy, relevance to what the post actually says, authenticity, tone, and spam-filter risk), switches to a value-first mode where self-promotion is restricted, and sets the rule that a failed comment gets one rewrite before it is dropped. Use it because forum moderation punishes patterns, not just single posts. Not for choosing a community (see community-channel-research) or for pre-posting rule checks (see community-post-preflight).
sources:
  - "Community comment safety (MIT, Yahav Fuchs), restated for community forums in general: the six-point check, the natural-mention mode for restricted self-promotion (stripping product references and external links and leading with expertise), the two-strikes rule (one rewrite, then skip), and the observation that moderation and spam systems react to patterns across comments"
  - "Removed: the platform's account-level terms and the named forum platform. The check is restated for any community forum"
  - "Adapted for GTM-360: the rule that the brand's employees disclose their affiliation where the community requires it is an author addition consistent with the six-point check. The two-strikes rule is kept from the source"
---

# Community comment safety

## Purpose

A brand comment in a community forum is judged twice: by the people reading it and by the moderators and spam systems watching the pattern. A comment that reads like an advertisement, or that repeats the same shape across threads, gets removed and can cost the account its standing. This skill checks each comment before it posts and sets how to rewrite one that fails.

## When to use

- Reviewing a draft comment that mentions the brand or the product.
- Writing a comment for a thread where the brand has a stake.
- Asking why comments keep getting removed.

Route elsewhere when:

- The question is whether a whole post is allowed. Use `community-post-preflight`.
- The question is which community to take part in. Use `community-channel-research`.
- The question is whether an account is ready to comment. Use `community-account-warmup`.

## The six-point check

1. **Community rules.** Does the comment comply with the rules the community states?
2. **Self-promotion.** Does it respect the community's self-promotion policy?
3. **Relevance.** Does it respond to what the post actually says, rather than to a keyword in it?
4. **Authenticity.** Does it sound like a person, with no spam pattern or template phrasing?
5. **Tone.** Does it match how that community talks?
6. **Spam-filter risk.** Does it contain anything that the platform's spam systems tend to flag, such as repeated links, a product name in every comment, or the same phrasing across threads?

Give each comment one of three verdicts: pass, fix, or skip.

## Value-first mode

Where a community restricts self-promotion:
- remove or minimise product references,
- drop external links entirely,
- answer the question fully, and let the brand earn at most a passing mention.

Value first is the only mode that survives in a community that restricts promotion.

## Disclosure

Where the commenter works for the brand, the community's rules may require them to say so. Disclose the affiliation where it is required, and where it is not required, do not imply independence.

## Two strikes, then skip

A comment that fails the check gets one rewrite. If the rewrite also fails, skip it. Do not keep rewriting the same comment for the same thread.

## Procedure

1. **Run the six-point check** on the draft.
2. **Record the verdict** and the point that failed, if any.
3. **If the verdict is fix,** rewrite once, in value-first mode if promotion is restricted.
4. **Run the check again** on the rewrite. If it fails again, skip the comment.
5. **Log the pattern** if the same point keeps failing across comments, because a pattern is what gets accounts removed.

## Output

- The verdict for each comment, with the failing point.
- The rewrite, if one was made.
- A note on any repeated pattern across comments.

## Quality bar

Every brand comment passes the six points before posting. Restricted communities are answered in value-first mode. Affiliation is disclosed where required. No comment goes through more than one rewrite. Watch for a product name in every comment, repeated phrasing across threads, and a comment that is a sales message in a discussion format.

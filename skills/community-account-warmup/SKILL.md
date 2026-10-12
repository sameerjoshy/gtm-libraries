---
name: community-account-warmup
version: 1.1.0
description: "Use when a brand account on an online community forum is new or has little standing, and the team wants it credible before any promotional activity. Sets out a warm-up ladder in which the share of promotional activity is earned step by step through contribution milestones, starting with zero product mentions, spreading across communities, and favoring active threads. Use before any promotion is planned for a new account. Not for monitoring an account that is already active (see community-account-health)."
---

# Community account warmup

## Purpose

A new account that promotes a product in a community forum is the most likely to be flagged. Forums check standing before they trust an account, and moderators look first at accounts with little history. This skill builds standing before promotion, and sets how much promotion the account can carry at each level.

## When to use

- A brand account is new, or has little contribution history.
- A team wants to start promoting through an account that has not been warmed up.
- Promotion from an account has been flagged or removed, and the team wants to know when it can resume.

Route elsewhere when:

- The question is an account that is already active and has moderation signals. Use `community-account-health`.
- The question is a particular post. Use `community-post-preflight`.

## Inputs

- The account's age and existing contribution history.
- The forum's own contribution signals for standing, such as accepted or upvoted posts.
- The rules of each target community, including any eligibility milestones.
- The promotion the team plans, to check against the ladder.

### The promotional ladder

Promotional share is earned, not chosen. Defaults, to calibrate for each forum:

| Standing level | Promotional share of activity |
|---|---|
| Starting, no standing | 0%. Warm-up only. |
| Early standing | About 10% |
| Building standing | About 20% |
| Established | About a third |
| Strong standing | Up to about half |

Standing is measured by the forum's own signals of contribution, such as accepted or upvoted contributions, not by the team's sense of how good the account is. Some forums also set eligibility milestones for certain communities. Check each community's rules before promoting in it.

### Warm-up method

1. **Contribute with zero product mentions.** Every comment is about the topic and the post in front of it.
2. **Favor active threads.** Early comments on threads that are gaining attention collect more standing for the same effort.
3. **Spread across communities.** Do not contribute to one community alone, because a single-community history looks like a promotion account.
4. **Keep the ladder.** Move up a level only when the forum's signals show the account has earned it.
5. **Record each milestone** with its date, so the team can show when the account became eligible.

## Procedure

1. **Assess the starting standing** of the account, using the forum's own signals.
2. **Set the starting share** at zero.
3. **Run the warm-up** for a set period, with the contributions spread across several communities.
4. **Re-assess standing** at each review. Move the promotional share up only when the level is reached.
5. **Stop promotion** if a moderation signal appears, and go to `community-account-health`.

## Output

- The starting standing and the promotional share allowed.
- The milestone log, with dates.
- The planned review dates and the next level.

## Quality bar

Promotion starts at zero. The ladder is applied using the forum's own signals. Contributions are spread across communities. Each level is reached before promotion moves up. Watch for promotion from a new account, a single-community history, and levels claimed without the forum's signals to show them.

---
name: community-account-health
version: 1.0.0
status: draft-for-review
description: Use to monitor the health of a brand's accounts on online community forums, or to respond when something has gone wrong: a comment has disappeared, a community has banned the account, or the account has been suspended. Classifies each moderation signal correctly (a ban, a removal, or a rule note) before reacting, gates posting on confirmed signals only, checks membership before each posting attempt, and sets the recovery path for temporary bans, permanent bans, and site-wide suspension. Not for the warm-up of a new account (see community-account-warmup).
sources:
  - "Community account health (MIT, Yahav Fuchs), restated for community forums in general: the daily scan of moderation messages, the distinction between a ban, a removal, and a rule note, the rule that only confirmed signals gate posting, membership checks before each posting attempt, and the recovery paths for temporary bans, permanent bans, and site-wide suspension"
  - "Removed: the platform's message and moderation names and the named forum platform. The classification is restated for any forum"
  - "Adapted for GTM-360: the rule to log each signal with a date and the community it came from is an author addition. The daily scan cadence is an author default"
---

# Community account health

## Purpose

Most overreactions in community forums come from misreading a signal. A removed comment is treated as a ban, and a ban is treated as the end of the account. This skill sets how to read each signal correctly, which signals should stop posting, and how to recover from each kind of action.

## When to use

- A brand account needs ongoing monitoring.
- A comment has disappeared, and the team is not sure why.
- An account has been banned from a community or suspended.
- A team member is about to post from an account that may have a moderation issue.

Route elsewhere when:

- The question is a new account that needs warming up. Use `community-account-warmup`.
- The question is a particular post. Use `community-post-preflight`.
- The question is a brand mention that needs triage. Use `brand-mention-monitor`.

## Read the signals

Scan the account's messages from moderators daily, and classify each one:

- **Ban.** An explicit ban from a community. Stop posting there. A temporary ban ends on its date. A permanent ban lifts only if the community's moderators remove it.
- **Removal.** A comment or post was removed. This is not a ban. Note the rule it broke, learn from it, and keep the community in rotation.
- **Rule note.** A moderator explains a rule and takes no action. This is free coaching. Feed it back into the content plan.

Only confirmed signals should gate posting. A suspected problem is watched, not acted on.

## Membership and pre-flight

Track which communities the account has actually joined. Confirm membership before each posting attempt, because posting into a community the account has not joined fails or looks like spam.

## Recovery paths

- **Temporary ban:** stop posting in that community until the ban ends. Do not post again on the end date until the community's rules have been re-read.
- **Permanent ban from one community:** remove that community from the plan. Do not appeal with a copy of the removed content.
- **Site-wide suspension:** stop all activity from the account. Review what triggered it. Move any further activity to another account only if the team's policy allows, and never to evade a ban.

## Procedure

1. **Scan the moderation messages** for each account daily.
2. **Classify each signal** as ban, removal, or rule note.
3. **Log each signal** with its date, the community, and the rule cited.
4. **Gate posting** only on confirmed signals.
5. **Check membership** before each posting attempt.
6. **Run the recovery path** for any ban or suspension, and report it to the owner of the account.

## Output

- A health readout per account: confirmed signals, the actions taken, and the communities currently open for posting.
- The log of signals with dates.
- The recovery action for any ban or suspension.

## Quality bar

Each signal is classified before any reaction. A removal is never treated as a ban. Posting is gated on confirmed signals. Membership is checked before every posting attempt. No ban is evaded. Watch for a removal treated as a ban and a ban ignored, posts made after a ban, and a suspension answered by opening a new account.

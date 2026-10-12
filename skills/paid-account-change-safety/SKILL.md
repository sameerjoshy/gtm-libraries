---
name: paid-account-change-safety
version: 1.0.0
description: "Use when an AI agent or automation is about to make a write change to a live paid media account (pausing a campaign, changing a bid or budget, adding negative terms, editing conversion tracking, or launching a campaign). Classifies each change by blast radius, defaults to propose-only, sets explicit limits for the low-risk band, requires a preview and a confirmation for anything executed, and records proof that a change ran. Use it so that a claimed success is backed by a verified change. Not for read-only analysis of an account."
---

# Paid account change safety

## Purpose

An agent that can read and write a paid media account can also spend money badly, quickly, and invisibly. The account is real budget. A reply that says "done" when the change did not run is worse than no reply at all, because the team will act on it. This skill sets the boundaries for writes, the confirmation required before any write runs, and the proof that a write actually happened.

## When to use

- An agent or automation is about to move from reading an account to changing it.
- A team is considering letting an automation adjust bids, budgets, or negative terms.
- A change has been made and someone asks whether it really went through.

Route elsewhere when:

- The question is the analysis that justifies a change. Use the relevant diagnostic skill, such as `paid-search-quality-diagnosis` or `paid-optimisation-signals`.
- The question is data quality in the systems behind the account. Use `revops-data-governance`.

## Inputs

- The proposed change, stated exactly: the object, the field, the old value, and the new value.
- The account's current state, read at the time of the proposal.
- The approval given, and whether it covers this specific change.

## Blast radius

Classify each proposed change before doing anything else:

- **Read-only:** no change to the account. Always allowed.
- **Low-risk:** a single keyword, a negative term, or a bid move within a tight band.
- **Account-level:** budget swings, conversion tracking, campaign creation or deletion, and anything touching billing.

## Default: propose only

Pull the data, calculate, and recommend. Execute nothing without an explicit go-ahead. An approval covers the specific change that was approved. It does not cover the rest of the session, and it does not carry over to a later change.

## Limits for the low-risk band

Keep the low-risk band genuinely low-risk. As defaults:
- bid moves within about twenty percent of the current bid,
- negative terms added only against clear waste, meaning spend with no conversions,
- no whole-campaign pauses,
- no budget changes larger than about twenty percent,
- conversion tracking and billing are never changed without a separate, explicit approval.

## Procedure

1. **Classify the change** by blast radius.
2. **If it is account-level,** stop and ask for approval for that change alone.
3. **If it is low-risk,** check it against the limits above. Anything outside the limits goes to the account-level route.
4. **Preview the change.** Show the object, the old value, the new value, and the expected effect. Ask for confirmation.
5. **Execute only the confirmed change.** Do not bundle additional changes into the same action.
6. **Read the change back from the account.** Confirm the new value is in place. Only then report it as done.
7. **Log the change** with the time, the object, the old and new values, the approval that covered it, and the read-back result.
8. **If the read-back does not match,** report the failure, do not report success, and do not retry without a fresh confirmation.

## Output

- The change's classification and the limits it was checked against.
- The preview shown for confirmation.
- The read-back result, and the log entry.

## Quality bar

No write runs without a confirmation that covers it. Success is reported only after a read-back matches. Account-level changes are never executed under a low-risk approval. Watch for changes reported as done without a read-back, a single approval used for several changes, and budget or tracking changes made inside the low-risk band.

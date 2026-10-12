---
name: leaked-demand-recovery
version: 1.0.0
status: draft-for-review
description: Use to recover demand that was paid for and then lost between systems: a chat or form lead who never booked, a demo request with no meeting, a call with no follow-up, an inbound reply never answered, a trial that ended quietly, or a closed-lost deal whose blocker has since changed. Builds the candidate list from capture systems, verifies each drop against two independent sources, sets the right voice from history, and drafts one recovery message per confirmed drop for human approval. Not for warm-reply cadence (see stage-aware-follow-up) or closed-lost re-engagement campaigns (see closed-lost-revival).
sources:
  - "Leaked demand recovery (MIT, Eliezer Cohen): build candidates from capture systems rather than the CRM, two-system verification as a hard gate, history before voice, hard disqualifiers before fit scoring, one drafted message per confirmed drop, failed-gate candidates kept visible"
  - "Removed: the reference files and the named capture tools. The seam list is restated as generic categories"
  - "Adapted for GTM-360: the one-month window for active leaks and six to twelve months for closed-lost revival are author defaults"
---

# Leaked demand recovery

## Purpose

The cheapest pipeline a company has is demand it already paid for and then lost in the gap between two systems. A chat transcript that never reached the CRM, a demo request that was never booked, a call with no follow-up. This skill finds those drops, proves each one before anyone contacts the person, and drafts a recovery message for approval.

## When to use

- A sweep is wanted for inbound or demo demand that went nowhere.
- Someone asks who fell through the cracks, or what was dropped.
- Before any re-engagement send, to check that the person has not already booked or replied.

Route elsewhere when:

- The thread is warm and a next touch is needed. Use `stage-aware-follow-up`.
- The campaign is for lost deals in general. Use `closed-lost-revival`.

## Inputs

- The window: about one month for active leaks, six to twelve months for closed-lost revival.
- Access to capture systems: mailbox, calendar, call recorder, the chat or form channel, and the CRM.
- The disqualifier list: geography, regulatory coverage, and segment, kept in one current place.

## Procedure

1. **Scope the sweep:** choose the seams to work and the window.
2. **Build the candidate list from capture systems, not from the CRM.** The CRM holds what someone remembered to log. The mailbox, calendar, call recorder, and chat channel hold what happened. Take the union, deduplicate by person and by company, and include people with no CRM record. They are the largest silent group.
3. **Verify every candidate against two independent systems.** This is a hard gate. A record saying someone was dropped is often wrong. Messaging someone who has already booked or replied costs more than a missed recovery. Candidates that fail the gate leave the list with a one-line reason. A failed gate is never softened into a light touch.
4. **Establish history before choosing a voice:**
   - No history: a fresh first touch.
   - Prior conversation: a re-engagement message that refers to that conversation honestly.
   - Existing or churned customer: route to the account owner and stop drafting.
   - Open deal owned by a colleague: flag the owner and stop, to avoid colliding with a live motion.
   - Closed lost: carry the stated reason into the framing, and proceed only if the blocker has genuinely changed.
5. **Apply hard disqualifiers before scoring fit.** Serviceability is binary and cheap. Fit scoring on an account that cannot be served is wasted effort. Thin enrichment is checked, not trusted, because poor records often understate company size.
6. **Draft one message per confirmed drop,** referring to what the person asked about or the exact point the last conversation reached. Where the drop was an internal failure, acknowledge it in one clause. End with one clear next step.
7. **Present for approval.** For each confirmed drop: person, company, type of leak, evidence checked, history, and suggested action. Then the drafts. Failed-gate candidates stay visible at one line each, so the verification is auditable.

## Output

- Confirmed drops with the evidence from both systems.
- One draft per confirmed drop, with its voice and next step.
- Failed-gate candidates, one line each, with the reason.
- If nothing is found, a short statement that the sweep ran and found no confirmed drops.

## Quality bar

Every confirmed drop passes the two-system check. Voice follows the history, not the default. Disqualifiers are applied before fit. Failed candidates are listed, not hidden. Watch for "no activity in thirty days" lists mailed without verification, and recovery messages to people who are already mid-conversation.

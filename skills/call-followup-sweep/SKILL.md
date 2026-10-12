---
name: call-followup-sweep
version: 1.0.0
status: draft-for-review
description: Use when a day or a week of customer calls has happened and the follow-through is owed but unwritten. Asks for the window, reads each call, extracts the commitments (especially the seller's own unshipped promises), triages which calls earn an email, and returns one draft per account that earns one, a list of calls that earn none with reasons, and an ageing report of open promises. Produces drafts only and never sends. Not for the sequence after a booked meeting (see stage-aware-follow-up).
sources:
  - "Call follow-up sweep (MIT, Boaz Descalo): window question before any reading, commitment extraction from both sides, triage that subtracts most calls, one draft per account, draft patterns by call shape, a 150-word cap with three action items, report ordering led by aged commitments, drafts-only rule"
  - "Removed: the source's reference files, which are not used. Writing rules are restated in this library's own terms"
  - "Adapted for GTM-360: the 150-word cap, the three-action limit, and the three-business-day ageing threshold are author defaults"
---

# Call follow-up sweep

## Purpose

After a busy week of customer calls, the follow-through is what decides deals, and it is the first thing to slip. Each call leaves promises on both sides, and the seller's own promises are the ones most often forgotten. This skill reads a window of calls, extracts the commitments, decides which calls warrant a written follow-up, and drafts those emails. Most calls do not need one, and a good sweep says so.

## When to use

- A batch of calls has happened, and follow-ups are owed.
- The user asks what was promised, or what fell through.
- A week needs catching up after travel or a conference.

Route elsewhere when:

- A single booked meeting needs its follow-up. That is `post-meeting-follow-through`.
- A warm reply needs its next touch. Use `stage-aware-follow-up`.

## Inputs

- The window: a single day, or a week (the trailing five business days, or the calendar week). Ask which.
- Access to calls: transcripts, recordings, or notes. A scheduled call with no recording is listed as unverified, not dropped.

## Procedure

1. **Ask the window** before reading anything. Never default to "all recent calls".
2. **Pull every call in the window.** Record account, attendees, date, and duration. Log any call that could not be read, with the reason.
3. **Extract commitments from each transcript**, in four groups:
   - What the seller committed to.
   - What the buyer committed to.
   - Questions the seller did not answer.
   - Dates named aloud.
   The seller's own commitments come first in review, because they are the ones most likely to be missed.
4. **Triage which calls earn an email.** Most calls do not. A follow-up is worth writing when it dates a commitment, puts in writing something that would otherwise be disputed, or gives the champion something to forward. A call that produced none of these earns no email.
5. **Dedupe by account.** Several calls with one account in one week become one email, built from all of them.
6. **Draft to the call's shape.** A stalled renewal, a first discovery, and a post-demo call each need a different email. Cap each draft at 150 words and three action items. Anything longer moves to a named next call.
7. **Assign an owner and a date** to every action item, or state that the call produced none.
8. **Report in this order:** commitments aged more than three business days, then the drafts, then the no-email list with one line of reason each, then any pattern repeated across calls.

## Output

- Ageing commitments first, with owner, date, and the call they came from.
- One draft per account that earns one, with subject, body, and action items.
- The no-email list, with a reason for each call.
- Calls that could not be read.
- Any objection or request that recurred across calls.

## Rules

- Drafts only. Never send, schedule, or write to a CRM as part of a sweep. The user reviews and sends.
- Never invent a commitment, date, or number that was not said on a call. Quote it, or flag it as unclear.
- Do not present a clean report over partial coverage. List the gaps.

## Quality bar

The window was confirmed. Seller commitments are extracted as carefully as buyer commitments. Most calls are shown as needing no email, with a reason. Each draft could not be sent unchanged to a different account. Watch for recap emails that narrate the call, drafts for every call, and missed promises.

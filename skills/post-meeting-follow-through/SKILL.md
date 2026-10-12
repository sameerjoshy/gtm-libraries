---
name: post-meeting-follow-through
version: 1.0.0
status: draft-for-review
description: "Use to make every external sales meeting produce its follow-through in a fixed sequence: pull the meeting record, check the account and its stage, classify the meeting outcome, record the meeting for metrics without double-counting, route the deal decision to a person, and draft a follow-up in the owner's voice for approval. Designed for one person taking many external meetings, so follow-up quality and CRM hygiene do not depend on memory. Not for the sweep of a whole week's calls (see call-followup-sweep)."
sources:
  - "Post-meeting execution (MIT, Jeremy Hurst): the two-phase workflow (deal decision, then follow-up), non-blocking errors for memory, enrichment, and CRM writes, a missing meeting record as the only blocking failure, an account enrichment step with an estimated deal size, the metrics log with a rule against counting an auto-created deal as a prior meeting, and the review post where the owner decides"
  - "Removed: the named meeting-note, CRM, and chat tools, the template placeholders, and the voice-guide and lead-scoring sub-skills. The method is restated as a generic sequence"
  - "Adapted for GTM-360: the deal-size threshold for full sales treatment is an author default. The rule that a drafted follow-up is never sent without approval is kept as a hard rule"
---

# Post-meeting follow-through

## Purpose

Follow-up after a meeting depends on memory, and memory fails on busy weeks. Notes are missed, the CRM is out of date, and the follow-up is written hours later from partial recall. This skill runs the same sequence after every external meeting, so the record, the decision, and the draft are ready within minutes, and a person decides what happens next.

## When to use

- Each external sales meeting, once its record exists.
- A team where one person takes many external meetings.
- When a review of how follow-ups are being handled is needed.

Route elsewhere when:

- The question is the follow-up for a whole batch of calls. Use `call-followup-sweep`.
- The question is the next touch on a warm thread. Use `stage-aware-follow-up`.
- The question is how the call went. Use `call-scoring`.

## Inputs

- The meeting record: summary, transcript, action items, attendees with their titles and companies, and any decisions logged.
- The account in the CRM: its stage, size, industry, prior history, and any open deal.
- The owner's approved voice, from examples of their past sent messages.
- The metrics log, if the team keeps one.

## Procedure

1. **Pull the meeting record.** If the notes tool already emails attendees a summary, do not duplicate it in the follow-up. If the record is missing, stop. This is the only blocking failure.
2. **Enrich the account.** Look up the company's stage, size, prior relationship, and open deal. Estimate the deal size from company size, the use cases raised, and any pricing signal. Flag the estimate if confidence is low. Tag the account as in a live sales conversation if at least one attendee is external.
3. **Classify the meeting** for metrics, if a log is kept:
   - Customer already: a current customer.
   - Active deal: a qualifying prior meeting exists within the last six months.
   - First touch: anything else.
   An open deal is not evidence of a prior meeting, because deals are often created automatically when a meeting is booked. A deal created on the same day as the meeting counts as a first touch.
   Write one row per meeting, with a unique identifier, so no meeting is counted twice.
4. **Make the deal decision for a person.** Score qualification against the team's method. Present the score and the reasons. The owner decides whether a deal is created. Nothing is written to the CRM without that decision.
5. **Draft the follow-up** in the owner's voice, using the outcome class from step 3 and the team's approved framework for it. Keep it to what the attendees need: dates, actions, and one next step.
6. **Post for review.** One review item contains the deal decision, the account enrichment, the metrics row, and the draft. The owner answers the decision questions, and only then do the downstream steps run.
7. **Record failures without stopping.** A failed memory, enrichment, or CRM step is logged on the review item, and the rest of the sequence continues.

## Output

- The review item for the owner: the meeting summary, the deal decision with its reasons, the account enrichment with confidence, the metrics row, and the draft follow-up.
- A list of any steps that failed, with the reason.

## Quality bar

No follow-up is sent without the owner's approval. The meeting is classified without counting an auto-created deal as a prior meeting. Every step failure is logged. The owner's voice comes from approved examples. Watch for drafts sent without review, deals created in the CRM without a decision, and metrics rows duplicated for the same meeting.

---
name: reply-handling
version: 1.1.0
description: "Use when a prospect has replied to an outbound sequence and you need to decide what to do next. Classifies the reply into one of six intent buckets, drafts the matching response or stop action, and records the outcome in the CRM after approval. Never sends on its own. For batches of more than about five replies, classifies first and then works one bucket at a time. Not for writing the first sequence (see outbound-cold-email)."
---

# Reply handling

## Purpose

A reply is the most valuable moment in outbound, and the easiest to mishandle. A rushed reply can lose an interested buyer. A wrong unsubscribe can lose a referral. A missing note means the next touch has no context. This skill classifies each reply, drafts the right response or stop action, and records the outcome, so that a human approves every step.

## When to use

- A prospect has replied to an outbound sequence.
- An out-of-office or auto-reply has arrived and affects the schedule.
- A batch of replies needs triage.

Do not use it for first-touch copy. That belongs in `outbound-cold-email`.

## Inputs

- The full thread: the original outbound message and the reply.
- The sequence the contact is in, and where it stands.
- The CRM record: lifecycle stage, owner, and any open deal.
- The org's voice: sender instructions and approved message examples.
- The CRM connection, if one exists. Without one, draft the reply and tell the user the CRM steps were skipped.

If there are no sender instructions, ask the user to define the voice once. Do not fall back to a generic tone.

## Procedure

### Step 1: Load the thread

Pull the sequence, the full thread, and the CRM state for the contact and the company. Read the last two or three turns and the sequence goal. Do not read every past message unless the classification depends on it.

### Step 2: Classify the intent

Read the reply once, then pick exactly one bucket. Write the classification as one line.

| Intent | Signals | Next action |
|---|---|---|
| Interested | Asks a question, requests a meeting, asks about pricing, "tell me more" | Draft a fast, positive reply. Propose times. Offer a short overview. |
| Objection | Concern about price, fit, or timing. "Not now." "We use X." | Reframe the objection in one sentence. Offer one specific next step. |
| Wrong person | "Not me." "Talk to X." A referral to a colleague. | Route to the named person. Ask for the introduction. Thank the sender. |
| Unsubscribe | "Stop emailing." "Remove me." "Unsubscribe." | Stop the sequence. Mark do-not-contact. Send no reply. |
| Out of office | Auto-reply with a return date or an alternate contact. | Pause the sequence until the return date. Route to the alternate if one is given. |
| Neutral or soft no | "Reaching out later." "Send info." A vague reply. | Send one short value note tied to a specific signal. Move to the next step. |

If the reply does not clearly fit a bucket, ask the user which one applies. Do not guess.

### Step 3: Draft the response

Draft in the conversation, not in the sequence tool. Match the sender's voice. Keep it short. Most replies need two to four sentences.

- **Interested:** propose two specific time windows or a calendar link, and name the next concrete step.
- **Objection:** acknowledge the concern in one sentence. Reframe it with one specific data point or example that you can source. Propose one small next step, such as a 15-minute call, a short recorded walkthrough, or a one-page brief.
- **Wrong person or referral:** thank them. Ask for the right contact's name and email. Offer to take the conversation off their plate.
- **Unsubscribe:** no reply. Stop the sequence, and write a note instead.
- **Out of office:** no reply. Change the sequence schedule only.
- **Neutral:** one line of value tied to a specific, real signal on the account. Do not pile on.

Never invent a data point, a customer, or a quote to make the reply stronger.

### Step 4: Record the outcome, after approval

Only after the user approves the draft or the stop action:

- **Unsubscribe:** stop the sequence. Set the do-not-contact flag the org uses. Add a note recording the reason.
- **Wrong person with a named contact:** find or create the new contact. Link them to the company. Add a note on the original contact recording the referral.
- **Interested or objection:** add a note summarizing the reply in one or two lines. Move the lifecycle stage if it has changed, for example from lead to opportunity. Create a follow-up task for the owner.
- **All buckets:** update the company record if the reply reveals new facts, such as a use case, the current vendor, or timing.

For a batch of more than about five replies, prepare all CRM updates as one set, show the set for approval, and write them together.

### Step 5: Handle batches

If there are more than about 20 unread replies:

1. Export the list to a file.
2. Classify each reply and add an intent column.
3. Print the count for each bucket.
4. Work one bucket at a time, starting with interested and referral replies, since they carry the most value.

## Rules

- Never send a drafted reply on your own. Show it and wait for approval.
- Never unsubscribe a contact without an explicit unsubscribe request. "Not interested" is an objection, not a stop.
- Never ignore a wrong-person reply. The referral is often the highest-value outcome of an outbound sequence.
- Write a note on every classified reply, so the next touch has context.
- Never treat a reply from an automated system as a human reply without checking.

## Output

- The classification and the reason, in one line.
- The draft, or the stop action, with the reason.
- The CRM changes that would be made, awaiting approval.
- A single question for the user, but only if the bucket or the voice is unclear.

## Quality bar

A good reply handler makes the next touch feel informed. Interested buyers get a fast, specific answer. Objections get one reframe and one small step, not a debate. Referrals turn into a named contact. Opt-outs are honoured the same day and recorded. Every reply leaves a note behind. Watch for replies sent without a reading of the thread, unsubscribes triggered by "not interested", and referrals that die in the inbox.

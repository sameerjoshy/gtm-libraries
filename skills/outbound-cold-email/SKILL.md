---
name: outbound-cold-email
version: 1.0.0
status: draft-for-review
description: Use when writing or reviewing a cold email or a multi-step cold sequence for a named account, contact, list, or signal. Picks the hook from the strongest real trigger, matches the org's voice, sets the sequence shape and cadence, applies a seven-point final gate, and stages every message for approval. Covers the deliverability limits that cap volume. Not for replies to existing threads (see reply-handling) or for LinkedIn and phone outreach.
sources:
  - "Reach out (MIT, Ido Goldberg / Swan), hook ladder, signal never as opener, voice precedence, draft rules, cadence defaults, seven-point final gate, stage for approval"
  - "Cold email 4-sequence (MIT, Alex Vacca / Frontal), trigger opener, pain email, delegation ask, break-up, BTL and ATL length rules, timing"
  - "Cold email strategist (MIT, Alex Vacca / Frontal, contributor Ivan Falco), value prop changes between emails, plain text, one CTA, deliverability limits (per-inbox volume, domain count, warmup, verification, bounce ceiling)"
  - "Email metrics and benchmarks (MIT, Alex Vacca / Frontal), reply-rate baselines by outreach type, deliverability warning thresholds"
  - "Adapted for GTM-360: CRM and sequence-tool calls generalised, vendor benchmarks labelled as starting points to calibrate per client, no invented proof points or customers"
---

# Outbound cold email

## Purpose

Write cold email that a named person could only receive from you, that has a real reason to arrive this week, and that asks for one small thing. Every draft is staged for a human to approve. Nothing is sent from this skill.

## When to use

- Writing a first-touch email or a full sequence for an account, contact, list, or signal.
- Reviewing an existing draft before it is approved.
- Setting the cadence or copy standards for a segment.

Route elsewhere when:

- The contact has replied. Use `reply-handling`.
- The request is for LinkedIn or a phone script. Those are separate motions.
- The request is about inbox setup or domain health alone. That is an infrastructure task for the client's ops owner.

## Inputs

- The target: company, contact role or name, and whether the contact is senior (VP and above) or practitioner (manager and below).
- The hook: a trigger event, a relationship, the contact's own published content, a company initiative, or a persona pain.
- The org's voice: approved past sends, any stated voice rules, and the offer's one-line value proposition.
- The cadence recorded for this motion. If none is recorded, use the defaults below and say so.
- Any existing unsent sequence to this contact. Edit it. Do not duplicate it.

If there is no hook, push back before drafting. A message with no reason to arrive now is a blast.

## Procedure

### Step 1: Choose the hook

Use the strongest hook you have, in this order:

1. A trigger event (a funding round, a leadership change, a product launch, a hiring spree).
2. A relationship (a shared contact, a prior conversation, an event you both attended).
3. The contact's own published content (a post, an article, a talk).
4. A company initiative visible in public sources.
5. A persona pain. Usable, but say so in the reasoning, because it is the weakest hook.

Never invent a signal. Tracking-type data (website visits, intent scores, profile views) never appears in the message, whatever the hook.

The hook shapes the angle. It rarely appears in the copy. Open with what the hook means for the reader, not with the news itself. An email that opens by congratulating someone on a funding round or a new hire is the clearest sign that a machine wrote it.

### Step 2: Match the voice

- Approved past sends are style examples. Imitate their tone and rhythm.
- The skill's strategy rules outrank the examples. If an example breaks a rule, follow the rule.
- Never copy wording from another organisation's material.
- If there are no examples yet, draft plainly from the ICP pains, the value proposition, and the persona. Tell the user the voice is provisional.
- Draft in the language the prospect buys in. A wrong-language sequence is an error.

### Step 3: Write the email

- **Opener:** one sentence on the hook's implication, in the contact's frame. The event itself never opens the message.
- **Body:** one researched detail at most, referenced rather than displayed. One proof point at most, attributed and sized to the company. No feature list. No invented customer, statistic, or quote. A proof point that is only "helps teams like yours" does not count.
- **Call to action:** one ask, the smallest real thing that could happen this week. A short list to review, one account to check, or a sample to look at. Offering concrete work beats asking for someone's time.
- **Altitude:** pitch to the reader's level. Senior readers hear risk and strategy. Directors hear operational pain. Practitioners hear the day-to-day problem.
- **Shape:** choose one of three shapes per email.
  - Signal, then proof, then ask (for a fresh trigger).
  - Problem, then cost, then fix (only when the pain is documented in the ICP).
  - Before, then after, then bridge (for a change that is easy to picture).
- **Plain text:** no HTML, no images, no tracked links where avoidable. Link instead of attaching.

### Step 4: Set the sequence and cadence

Use the cadence recorded for this motion. Otherwise use these defaults:

| Step | Day | Angle |
|---|---|---|
| 1 | 0 | Trigger opener with one proof point and one ask. |
| 2 | 3 | Primary pain. A new angle, not a repeat of step 1. |
| 3 | 7 | Value on its own, with no ask. A useful insight or peer story. |
| 4 | 14 | Break-up. Clean exit that leaves the door open. |

Rules for the sequence:

- Each follow-up is shorter than the one before. Each one stands on its own and brings something new: new proof, a sharper insight, a useful asset, or a peer story. A follow-up with nothing new is skipped.
- Change the value proposition between emails. A useful default: step 1 on saving money, step 2 on making money, step 3 on saving time.
- The break-up asks a timing question, such as "Is this not a priority right now?" Once it is sent, honour it. No further messages.
- One channel per sequence unless the motion says otherwise. Do not reference one channel from another.
- Multi-thread only for large accounts (around 200 or more employees), committee signals, or when asked. Use a different angle for each contact. Never send the same email twice into one company.

### Step 5: Set length limits

These are starting defaults. Calibrate them to the client's own results.

- **Practitioners (managers and below):** up to 90 words, 3 to 4 sentences.
- **Senior readers (VP and above):** up to 60 words, 2 to 3 sentences.
- **Follow-ups:** shorter than the first email, in every case.
- **Subject line:** 2 to 5 words, lower case, looks internal.

### Step 6: Run the final gate

Run all seven checks on every message before it is staged. A failed check means rewrite, not tweak.

1. **Delete the opener.** Does the email still make sense? If not, the personalisation is decoration. Rebuild it around the hook.
2. **Check the close for "worth".** "Worth 15 minutes", "worth a quick look", and "worth a conversation" are common enough that they reduce replies. Ask for the thing itself.
3. **Check sentence one.** If it names a funding round, a launch, a hire, or any other event, rewrite it. Open with what it means for the reader.
4. **Check uniqueness.** Could this email go to anyone else this week? If so, it is a blast in disguise.
5. **Check the ask and the length.** One call to action. Within the per-seniority word caps in Step 5, and shorter for follow-ups. Subject line 2 to 5 words, lower case. More "you" than "I" or "we".
6. **Check the proof.** For an email, the proof must be a named or measured result. "Helps teams like yours" is not proof.
7. **Read as the recipient** with a full inbox. Is there any reason to reply beyond politeness?

### Step 7: Stage for approval

- Check for an existing unsent sequence to the same contact, and edit it rather than create a second one.
- Stage each message with its reasoning: who it is for, why now, which hook, which shape, and which cadence.
- Never send without explicit approval in the current conversation. Never attach files. Link instead.
- A channel with missing contact data is fixed or dropped. Do not guess an address.
- If the org has a sending tool, stage the sequence there as unsent. Do not start it.

## Deliverability limits

These cap volume, whatever the copy quality. They apply to the sending domains and mailboxes the client uses.

- Cold email goes from outreach domains only, never the primary company domain. Plan for 3 to 5 outreach domains.
- Cap each mailbox at about 30 emails a day.
- Warm new domains for 4 to 8 weeks before the first cold send.
- Verify 100% of addresses before a campaign starts.
- Keep the bounce rate below 2%. Stop and investigate above 5%.
- Keep the spam-complaint rate below 0.1%, and the unsubscribe rate below 0.5%.
- Keep sustained reply rates above 5%. Below 2% for a campaign is a diagnosis trigger, not a reason to add volume.
- Set SPF, DKIM, and DMARC correctly on every sending domain before the first send.

## Benchmarks

Reply-rate baselines by outreach type. Use them to set expectations and to spot problems. Replace them with the client's own results as they come in.

| Outreach type | Typical reply rate |
|---|---|
| Cold, no signal | 6 to 8% |
| Signal-based | 18 to 22% |
| Multiple signals stacked | 35 to 40% |
| Website visitor follow-up | 25 to 30% |
| Champion job change | 20 to 25% |

Diagnose by symptom:

| Symptom | Likely cause | Fix |
|---|---|---|
| Low opens | Subject line or deliverability | Test subject lines, check sender reputation and placement |
| Opens, no replies | Weak relevance | More specific hook, shorter copy |
| Replies, no meetings | Unclear or weak ask | Smaller, clearer ask |
| High unsubscribes | Wrong audience or too much volume | Narrow the list, reduce frequency |

## Output

For each sequence, staged for approval:

- The target, the hook used, and the reason it is timely now.
- Each email: subject line, body, word count, and the seniority cap it was checked against.
- The cadence and the angle of each step.
- Any gate check that failed on the first pass, and what was changed.
- Placeholders for any proof point or figure the approved material does not provide. Do not fill them with estimates.

## Quality bar

A strong email has a hook that fits almost no one else that week, substance that traces back to the ICP and the value proposition, and nothing that reads like a template. Watch for the proof point growing into a feature list, the call to action shrinking to a calendar link, a segment blast presented as personalisation, and feedback that is given but never written into the org's voice notes.

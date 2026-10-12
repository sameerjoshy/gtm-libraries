---
name: cold-call-outreach
version: 1.0.0
status: draft-for-review
description: "Use when building, reviewing, or training on phone outreach to prospects: an opening script, a no-show call, a voicemail, or objection handling. Keeps every script to a short, permission-based opener with a real trigger and a specific ask, requires approved proof points, and applies consent and do-not-call rules before any call. Not for email or a social message."
sources:
  - "Cold call scripts (MIT, Alex Vacca / Frontal), five-step one-minute opener (pattern interrupt, permission, relevance, social proof, open question), no-show script, voicemail under 20 seconds"
  - "SDR outbound rules (MIT, Alex Vacca / Frontal), review checklist and tone by offer type, applied to call scripts as the same writing rules"
  - "Adapted for GTM-360: placeholders replace the sample company and its invented result, a compliance step is added before any call, approval required for every script"
  - "Pre-call script (MIT, Dyanesh Perumal): preparing a script for one named prospect from the account research, the checks on prior contact and warm routes, the stop conditions, and the two-to-three-minute meeting-selling call with every line traced to a researched fact"
---

# Cold call outreach

## Purpose

A cold call is the most interrupting form of outreach, so it has to earn the next thirty seconds. Keep the opener short. Ask permission. Show a real reason for the call. End with one question that opens a conversation. Every script is written from approved material, and no call is placed by this skill.

## When to use

- Building an opening script for a segment or a persona.
- Writing a no-show call or a voicemail.
- Training SDRs or reviewing a script before it is used.
- Preparing responses to common objections.

Route elsewhere when:

- The work is email or a social message: use `outbound-cold-email` or `linkedin-outreach`.
- The prospect has already replied or been on a call: use `reply-handling` or the deal process.

## Inputs

- The segment and the persona, with their likely pain in their own terms.
- The trigger for this call: an event, a visit, a referral, or a signal. A call with no trigger is weaker. Say so.
- Approved proof: a named customer with permission to reference, or a measured result the org can support. Without it, use a placeholder.
- The compliance rules that apply to the call. Check the rules for the prospect's country and region before any call is made. Also check the org's do-not-call list.
- The org's voice and offer type, for the tone (see Step 4).

## Procedure

### Step 1: Check consent and compliance first

Before writing a script, confirm:

- The number is one the org is permitted to call for this purpose, under the rules for the prospect's location.
- The number is not on the org's do-not-call list or the national one that applies.
- Call-recording and consent rules for the region are known and followed.
- The call has a logged owner and a record of the outcome.

If any of these are unknown, stop and ask. Do not write a script for a list you are not cleared to call.

### Step 2: Write the opening (five steps, under one minute)

| Step | Purpose | Shape |
|---|---|---|
| 1. Name and reason to call | Interrupt the pattern and make the caller clear | "Hi [first name], this is [name] from [company]. I know I'm catching you out of the blue." |
| 2. Ask permission | Earn 30 seconds | "Mind if I take 30 seconds to say why I called? Then you can decide whether it's worth continuing." |
| 3. Relevance | Say who you help and with what | "I work with [role or company type] who are dealing with [specific problem]." |
| 4. Proof | Show a result from approved material | "We recently helped [similar company type] with [measured result, from approved material]." |
| 5. Open question | Start a conversation | "Is [problem] something you're dealing with right now?" |

Rules for the opener:

- Use the trigger in step 3 when there is one, for example "I saw your team is hiring for [role]". Never invent a trigger.
- The proof in step 4 must be a real, approved result with the customer's permission. If none exists, use a placeholder and do not run the script until it is filled.
- The question in step 5 must be answerable with a short reply.
- Keep the whole opener to one minute at a natural pace.

### Step 3: Write the other scripts

**No-show call.** Assume good intent. Do not add guilt. Offer an easy reschedule.

> "Hi [first name], it's [name] from [company]. We had a call scheduled for [time], and I wanted to make sure everything's all right. No worries if something came up. Would [alternative time] work better?"

**Voicemail (under 20 seconds).** Leave the name, the company, one line of relevance, the trigger if there is one, and a promise of a follow-up email. Do not leave a pitch.

> "Hi [first name], [name] from [company]. I work with [role] on [problem]. Given [trigger], I thought it might be relevant. I'll send you a short email with a couple of times. Talk soon."

### Step 4: Match tone to offer type

- **Consultative offer:** calm and strategic. Position the caller as a trusted adviser.
- **Accelerator or fast-moving product:** friendly, curious, approachable.
- **Outbound cold:** direct and clear, with a short pattern interrupt. Not aggressive.

Use the same writing rules as email. Short sentences. No buzzwords. No fake enthusiasm.

### Step 5: Prepare objection responses

Write one response for each common objection, and keep it short. Each response should be one acknowledgement, one specific point from approved material, and one question. Never argue with the prospect.

Examples of objections to prepare for: "We already have a solution," "Not a priority right now," "Send me something," "I'm not the right person."

For "we already have a solution," the question to ask is what is working and what the prospect would change. For "send me something," the question is what would be most useful to send. Ask before sending anything.

### Step 6: Review the script before use

Check each script against this list.

- [ ] Under one minute when read aloud?
- [ ] One question at the end?
- [ ] Trigger or relevance included, and real?
- [ ] Proof is approved and specific, or a placeholder is clearly marked?
- [ ] Tone matches the offer type?
- [ ] No buzzwords, no invented claims, no fake enthusiasm?
- [ ] Compliance check in Step 1 completed?
- [ ] Would a busy person keep listening after the first sentence?

## One named prospect

Use this section when a rep is calling one named person, not a list. Before writing the script, load the account research, the contact's role, and the measure the contact was hired to move.

Check the CRM for prior contact. A logged earlier call makes this a follow-up: acknowledge the last conversation, lead with something new, and do not restart the pitch. Check for a warm route, such as a referral, a mutual connection, a prior touch or an event. A warm route leads the opener, and nothing else competes with it.

If the contact is marked not interested, or already sits in an open opportunity, stop and confirm with the rep before writing anything.

The call runs two to three minutes and sells the meeting, not the product. Keep discovery-grade questions out of the script. Every line of the script should trace to a fact from the research. If the prospect cannot answer why you and why now within the first twenty seconds, the call is a cold read that wastes a rare live connection.

## Output

For each script:

- The script itself, with placeholders in square brackets.
- The trigger it depends on, and the approved proof it uses.
- The compliance status for the list.
- The objection responses prepared alongside it.
- A list of open placeholders that must be filled before the script is used.

## Quality bar

A good cold call script sounds like a short, polite, specific message from someone who has a reason to call. It does not sound like a recording, and it does not claim results the org cannot support. Watch for scripts that open with "how are you," that run past a minute before any question, that include a result nobody has approved, and that are used on numbers the org is not cleared to call.

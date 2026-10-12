---
name: reply-pull-gate
version: 1.1.0
description: "Use to score a drafted outbound message before it is sent, and to write a cold or re-engagement touch that must earn a reply from someone who owes the sender nothing. Checks four moves (show the work, poke rather than pitch, one line that could only have been written this week, and writing to be forwarded), calibrates the ask to how well the sender knows the recipient, and returns SEND or SEND BACK with the named rewrite. Clean copy is treated as the minimum, not the goal. Not for the offer's design (see cold-offer-architect)."
---

# Reply pull gate

## Purpose

Most cold messages are clean and forgettable. They are polite, short, and specific enough to avoid being rejected, and they still get no reply, because they give the reader no reason to answer. This gate checks whether a draft has pull: a reason for a stranger to spend five seconds on it and answer. It returns a verdict and says exactly what is missing.

## When to use

- Before any cold or re-engagement message is sent.
- When a sequence's reply rate is flat and the copy looks clean.
- When a subject line is being written.

Route elsewhere when:

- The offer itself is weak. Use `cold-offer-architect`.
- The campaign's numbers are the problem. Use `outbound-performance-diagnosis`.

## Inputs

- The draft, with its subject line.
- The recipient's name, role, and company.
- How well the sender knows the recipient: cold, has accepted a connection or opened a thread, or has had a reply or a prior conversation.
- The artefact the sender could offer, if any.

## Procedure

1. **Check the one-line law.** The recipient owes the sender nothing. The first touch is to earn five seconds and a reason to answer. It does not describe the sender and does not ask for a meeting.
2. **Check the four moves.** Each touch needs at least two. A first touch in a sequence needs three.
   - **Show the work:** the ask names a concrete artefact made for this account, such as a list pulled for them, a short teardown, or what a named non-competitor in their category did. "More information" is not an artefact.
   - **Poke, don't pitch:** the opening raises a cost or blind spot the reader may not have priced, as an observation or a genuine question. A sweeping market claim or a statistic in the opening line fails this move.
   - **One unscrapeable line:** one sentence, dated within about three months, that shows someone did homework this week, such as a campaign, a hire, a role change, or a launch. A generic compliment fails.
   - **Write to be forwarded:** the message makes sense to a colleague with no context, names the company in plain words, and carries a single ask small enough that forwarding costs nothing.
3. **Calibrate the ask to the rung:**
   - Cold: the ceiling is permission to send the named artefact. Never a call.
   - Warmed (accepted a connection, opened a thread, or recent history): the artefact plus a soft "worth a look?"
   - Engaged (replied, or prior conversation): a meeting ask belongs here, and only here.
   An ask above the rung reads as desperation.
4. **Return the verdict.** SEND if the draft has at least the required moves and the ask fits the rung. SEND BACK if not, naming each missing move and the rewrite that would supply it.
5. **For a subject line,** check that it names something specific, not a generic benefit, and that it could not be sent to every company in the list.

## Output

- Verdict: SEND or SEND BACK.
- For each move: present or missing, with the line that shows it.
- The ask, checked against the rung.
- For SEND BACK: the named rewrite for each missing move.

## Quality bar

Every verdict cites the move it checked. The ask fits the rung. No opening line contains a statistic or a sweeping market claim. A SEND BACK always names its rewrite. Watch for drafts that are clean but have no artefact, asks above the rung, and generic compliments presented as homework.

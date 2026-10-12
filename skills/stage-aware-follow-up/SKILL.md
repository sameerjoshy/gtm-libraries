---
name: stage-aware-follow-up
version: 1.0.0
description: "Use when a live deal needs its next touch and the move is not obvious: a prospect replied warmly but never booked, a call happened and the thread went quiet, an agreement is out and unsigned, a meeting was missed, or the deal has gone cold. Identifies the deal's stage, then produces the next message with a direct booking ask where one is needed, and the date and hook of the touch after it. Not for the first cold touch (see outbound-cold-email)."
---

# Stage-aware follow-up

## Purpose

A deal that has produced a reply needs a next touch, and the next touch depends on the stage. A warm reply that never reaches the calendar is the most common loss, because the thread reads friendly and nobody asks for the meeting. This skill names the stage, writes a message that carries the right ask, and dates the touch after it so no warm thread is left undated.

## When to use

- A prospect replied warmly and nothing is booked.
- A call happened and the thread went quiet.
- A proposal or agreement is sent and unsigned.
- A booked meeting was missed.
- A deal has gone cold and may be revived.

Route elsewhere when:

- The first cold touch is needed. Use `outbound-cold-email`.
- A reply needs classifying. Use `reply-handling`.

## Inputs

- The thread so far, with dates.
- The current stage, or the facts needed to place the deal in one.
- Anything promised in the last exchange, and any asset the prospect asked for.

## Stages and cadence (defaults)

| Stage | Situation | Touch rhythm |
|---|---|---|
| 0 | Warm reply, nothing on the calendar | Day 0, 2, 4, 7, then demote |
| 1 | Between booked meetings | Same day, day before, meeting day |
| 2 | Decision pending, no agreement | Same day, 2, 4, 7, 14 |
| 3 | Agreement out, unsigned | Hour 0, 24 hours, day 2, 4, 7, 14 |
| 4 | Written proposal, no meeting held | Same day, asking for the meeting, then stage 2 |
| 5 | Long-term nurture | Every 30 to 45 days |

If the cadence says a touch is early, say so and offer to draft it anyway.

## Procedure

1. **Name the stage.** The stage determines the message. Get it wrong and the draft is wrong.
2. **For stage 0, make every touch do two jobs:** give a new, concrete reason to meet, and carry a direct booking ask. Never send one without the other.
3. **Ask directly.** Avoid soft closes that give an exit: "whenever works", "no rush", "happy to chat sometime".
4. **Answer buying questions briefly, then ask for the meeting** in the same message. Do not open unpaid question-and-answer.
5. **If a promised asset is the reason for the meeting,** present it in the meeting. Sending it ahead removes the reason to meet. Send it standalone only after two explicit refusals.
6. **When a buyer asks for a call,** send the booking link and what the call will cover. Do not ask which day works or request their availability in writing.
7. **A missed meeting is treated as a scheduling miss.** Same day, no blame, a fresh link.
8. **Never end the thread with a breakup message,** and never announce a change of cadence. Slow the rhythm quietly and demote to nurture after the stage's touch cap (seven by default).
9. **Before finalising, ask:** would this message be worth sending even if the prospect never buys? If not, rewrite it.
10. **End every draft with** `NEXT-TOUCH: [date], [specific hook]`.

## Output

- The stage and the reason for it.
- The message, with its booking ask where one is needed.
- The `NEXT-TOUCH` line.

## Quality bar

Every touch to a warm reply carries a booking ask. Every draft ends with the next date and hook. No breakup messages, and no repeated value drop to the same prospect. Watch for "just checking in", "circling back", invented deadlines, and drafts that could go to any account.

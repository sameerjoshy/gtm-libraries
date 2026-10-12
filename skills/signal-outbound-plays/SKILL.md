---
name: signal-outbound-plays
version: 1.1.0
description: "Use to choose a signal-based outbound play: a reason to contact a prospect that is tied to an observable event, such as a new hire, a departure, a role that signals priority, a review that names a problem, or a new follower. Gives eleven plays, each with its signal, its timing, and its value-first angle, and a rule for when each play should not be used. Not for detecting signals in depth (see signal-detection-and-timing)."
---

# Signal-based outbound plays

## Purpose

A message with a reason behind it, tied to something that just happened to the prospect, gets read. A message with no reason gets deleted. This skill gives the team a set of signal plays: each has a trigger, a timing window, and an angle that gives value before asking for anything. It also says when a play should not be used, because a poorly timed play reads as surveillance.

## When to use

- The team wants outbound that is timed to an event.
- A rep has a signal and needs to know whether a play fits.
- A campaign needs a set of plays, each with its own message frame.

Route elsewhere when:

- The question is detecting and interpreting a signal. Use `signal-detection-and-timing`.
- The question is a hiring signal. Use `hiring-signal-tracking`.
- The question is a champion who has moved. Use `champion-job-change-tracking`.

## Inputs

- The signal for each prospect: what happened, and when.
- The play that matches the signal, and its timing window.
- The prospect's role and company, to check the angle fits.
- Any reason the play should not be used, such as a sensitive event or a recent contact.

### The plays

| Play | Signal | Timing (default) | Angle |
|---|---|---|---|
| 1. New team members | Company has added people to a relevant team | 2 to 4 weeks after the hire | Help the new person get up to speed on the problem |
| 2. Skills targeting | Public skills match the product's use | Ongoing | Speak to the work the skill implies |
| 3. Role targeting | An uncommon title shows the function is a priority | Ongoing | Ask how the role is set up to succeed |
| 4. Industry research | A survey or study of the buyer group | Value first | Share the findings and ask for their view |
| 5. Resources for new practitioners | New people starting in a role | Evergreen | Useful starter material, no pitch |
| 6. Departed employee | A person in a relevant role has left | 1 to 2 weeks after | Offer cover for the gap in their work |
| 7. Missing role | A function with no dedicated owner, at a company of a size where one is expected | Ongoing | Describe the gap and what it costs |
| 8. Public negative review | A public review names a problem your product solves | Within days | Acknowledge the problem, describe how others solved it |
| 9. Generated ideas | Personalized ideas about the prospect's business | Ongoing | Two specific ideas, then the offer |
| 10. Visitor activity | Prospect has visited pricing or a high-intent page | Real time | Helpful, short follow-up by the most relevant channel |
| 11. Inbound followers | A new follower on a relevant social account | 24 to 48 hours | Thank them and offer a relevant resource |

### Rules for each play

- **Use the play only when the signal is observable and current.** A signal older than its timing window is not a signal.
- **Do not reference how the prospect was found** beyond what is public. Never imply monitoring of private activity.
- **Play 8 uses only public, cited reviews,** and names the problem rather than the reviewer.
- **Play 10 is for prospects who opted in or whose activity is on the company's own site,** and follows the team's consent rules.
- **Do not use a play for a person who has asked not to be contacted.**

## Procedure

1. Name the signal, with its source and date.
2. Match it to a play. If none fits, do not force one.
3. Check the timing window.
4. Write the angle in the team's voice, value first.
5. Apply the rules above, and check the offer against `cold-offer-architect` before sending.
6. Route the draft for approval. Nothing is sent without it.

## Output

- The signal, its source and date, and the play it matched.
- The draft, with its angle and timing.
- A note if the signal was too old, or no play fitted.

## Quality bar

Every play is tied to a dated, observable signal. Timing windows are respected. The angle gives value before asking. No message reveals private monitoring. Watch for plays used on stale signals, messages that quote a prospect's activity back to them, and reviews used without citation.

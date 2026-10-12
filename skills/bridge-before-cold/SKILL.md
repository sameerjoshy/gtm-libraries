---
name: bridge-before-cold
version: 1.1.0
description: "Use before staging a prospect and before drafting any first touch, when a segment has gone quiet, and when deciding whether an account is genuinely cold. Walks a ranked ladder of bridges the team can verify (prior contact, past delivery, a reference, a network edge, a shared conversation, a shared event, a peer's reply, a dated trigger), stops at the first verified rung, and writes a one-line premise for each contact. A contact is declared cold only after the search fails. Not for the message itself (see reply-pull-gate or personalized-first-touch)."
---

# Bridge before cold

## Purpose

Most outbound treats cold as the starting point. It is the ending point, what remains when no honest connection can be found. This skill makes the connection search a step with a checkable output. Each contact leaves with either a verified bridge and a premise, or a declaration that the account is cold, with the rungs that were tried.

## When to use

- Before a contact is staged for outreach.
- Before any first touch is drafted.
- When a segment has gone silent and the team wants to know whether it is truly cold.
- When someone asks whether an account is cold.

Route elsewhere when:

- The question is the message wording. Use `reply-pull-gate` or `personalized-first-touch`.
- The question is which contacts to target. Use `prospect-list-building`.

## Inputs

- The contact: name, company, role, and email domain.
- The team's own records: email and CRM history, delivered work, reference accounts the team is cleared to name, event attendance, and any shared network the team can see.
- The segment and the angle, if one exists.

### The lanes

Classify the recipient before writing. Each lane licenses a different opener and ask:

| Lane | The opener stands on | The ask may reach |
|---|---|---|
| Inbound | Their own action, quoted | A meeting |
| Postbound | Something they engaged with | A light question |
| Bridgebound | A verified bridge, stated as dated fact | One step above cold |
| Cold | An observation about their business that could be checked | The smallest yes |

Cold is permitted only after the search below fails.

### The ladder

Walk it top down. Stop at the first rung that returns a verifiable fact with a date and a source.

1. **Prior one-to-one contact with this person,** by name and by email domain, in the inbox or the CRM.
2. **Past delivery to this company,** read from the revenue record, not from a label.
3. **Their company is a cleared reference.** Only if the team may name it. State it as a company fact.
4. **A live network edge.** A first-degree connection is a bridge. A second-degree connection counts only when the mutual contact can be named.
5. **A prior conversation on a social channel,** read from the sent-message record. A prior direct message means "reaching out" is not accurate.
6. **A shared room.** Met at, attending, and registered for are three different facts. State which one the team has.
7. **A peer replied to this angle.** This is not a bridge to the person, but it calibrates the angle for their segment.
8. **A dated why-now event at their company,** such as a launch or hire, within the freshness window.

## Procedure

1. **Classify each contact** into a lane.
2. **Walk the ladder** and record the rung reached, the fact, its date, and its source.
3. **Write the premise line** for each contact: one sentence stating the bridge or the observation the message will stand on. The writer and the reviewer both work from it.
4. **Declare cold only after the ladder fails.** Record the rungs tried and why each failed.
5. **Count the declarations.** Report how many contacts in the batch were declared cold. A high count is a finding about the list, not a reason to write colder messages.

## Output

- Per contact: lane, rung reached, fact, date, source, and the premise line.
- The count of cold declarations, with the rungs tried for each.
- A note on any segment where most contacts are cold, and what that suggests about targeting.

## Quality bar

Every bridge is a dated fact with a source. "Met at an event" is not a bridge unless the specific event is named. No contact is declared cold before every rung has been tried. Watch for bridges inferred from shared attributes, a prior message claimed as no contact, and a cold count that is not reported.

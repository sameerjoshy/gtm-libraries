---
name: event-logistics-planning
version: 1.0.0
status: draft-for-review
description: Use to set up the scheduling and calendar side of a conference for a participant or a team. Covers booking links with event dates, venue time zone, buffers, and host model (personal, collective, or round-robin); a personal or team itinerary that resolves overlapping sessions, booth shifts, dinners, and travel without blocking everyone for every session; and a shared reference calendar built from the official agenda with duplicate-safe updates. Not for the attendee dossier (see event-attendee-prep).
sources:
  - "Conference booking links, personal conference plan, and shared conference calendar (MIT, Ariel Cohen): the rule to reuse known event facts before asking, to inspect existing event types and calendars before creating anything, the host-model choice (one participant, standardised per-person links, all hosts required, or any suitable teammate), the rule that an agenda entry does not prove attendance, the instruction to reuse original invitations rather than copy them, the protection of confirmed commitments before optional sessions, and the normalisation of agenda entries with a source trail"
  - "Removed: the named scheduling tool and its plan limits, the calendar product, the browser steps, and the worksheet and reference file contents. The three outputs are restated as one planning workflow"
  - "Adapted for GTM-360: the default twenty-minute meeting with ten-minute buffers and two hours' minimum notice are starting suggestions only, and are labelled as such. The rule never to infer the time zone from the operator's computer is kept as a hard rule"
---

# Event logistics planning

## Purpose

Conference logistics fail in predictable ways. Booking links show no slots, the team's calendars fill with sessions nobody is attending, and the shared agenda is out of date by the time people import it. This skill covers the three outputs that prevent that: working booking links, a realistic personal or team itinerary, and a shared reference calendar.

## When to use

- A team is attending a conference and needs booking links for prospects.
- A participant needs a plan that works around speaking slots, booth duty, and dinners.
- A shared calendar of sessions is wanted for a group.
- Booking availability is missing or wrong for an event.

Route elsewhere when:

- The question is the people to meet at the event. Use `event-attendee-prep`.
- The question is the follow-up after a meeting. Use `post-meeting-follow-through`.

## Inputs

- The official event source, the event dates, and the venue's IANA time zone.
- The in-person location, daily meeting windows, and the meeting length.
- The hosts and the calendar owner or destination.
- The intended readers and editors of any shared calendar.
- Confirmed invitations, assigned duties, and the sessions each person has chosen.

Ask only for facts that change the result: the official source, the dates, the time zone, the calendar destination, and the readers. Do not infer the time zone from the operator's own computer.

## Procedure

### A. Booking links

1. **Reuse known facts.** Take dates, time zone, location, hosts, windows, duration, buffers, and notice from the inputs. Starting suggestions if nothing is given: a twenty-minute meeting, ten minutes of buffer after, and two hours' minimum notice. Label these as suggestions.
2. **Inspect what exists** before creating anything. Check existing event types and schedules, so duplicates are not created and unrelated links are not changed.
3. **Choose the host model:**
   - one participant: a personal event type,
   - separate links per teammate with the same settings: a shared template where the tool supports it, otherwise matching personal types,
   - all named hosts must attend: a collective event,
   - any suitable teammate may take it: round-robin.
4. **Check plan limits** for the chosen model before setting it up. Do not purchase a plan or create accounts without approval.
5. **Verify each public booking page** shows real availability for each host on the event dates.

### B. Personal or team itinerary

1. **Gather what is confirmed.** Read the agenda, the existing calendar where accessible, confirmed invitations, selected sessions, and assigned duties. Check source timestamps. An agenda entry does not prove the person will attend.
2. **Protect the fixed commitments first:** speaking slots, booth shifts, travel, and confirmed meetings.
3. **Choose among overlapping sessions** by the person's stated priorities. Keep unresolved choices as options until the person selects one.
4. **Add optional sessions and networking time** last, and leave gaps between commitments.
5. **Reuse original invitations** for dinners and meetings. Do not create a personal copy of a commitment that already exists. If a placeholder conflicts with an organiser update, propose updating the mapped placeholder and keep the source trail.
6. **Leave unknown session times unresolved.** Do not invent blocks.

### C. Shared reference calendar

1. **Inspect the destination and prior imports** before creating anything. Prefer an authorised existing calendar where it serves the purpose.
2. **Normalise each session** with its source identifier, title, date, start and end, time zone, room, speaker, source link, and confidence. Keep concurrent sessions. This is a reference calendar, not one person's itinerary.
3. **Prefer explicit organiser updates** over stale listings. Keep a change log.
4. **Do not copy private notes** into shared descriptions.
5. **Separate a private team calendar from a publicly shared one.** Check the sharing permissions match the intended readers.
6. **Make updates duplicate-safe** by matching on source identifier, not title.
7. **Without live access,** produce an importable file and exact setup steps, and state that the live setup is not done.

## Output

- Booking links with verified availability, or the configuration and setup steps if live access is missing.
- The itinerary: fixed commitments, chosen sessions, and open options.
- The shared calendar, or an importable file with its setup steps.

## Quality bar

Existing event types and calendars are inspected before anything is created. No plan is purchased and no account is created without approval. Time zone comes from the venue, never the operator's machine. Original invitations are reused. Confirmed commitments are protected before optional sessions. Watch for booking links that show no real availability, itineraries that block people for sessions they have not chosen, and duplicate calendar entries created on each import.

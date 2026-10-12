---
name: event-selection-scoring
version: 1.0.0
status: draft-for-review
description: "Use to choose which conferences, trade shows or vendor events a company should attend, exhibit at or sponsor next. Locks the buyer classification first, then scores each event on relevance, decision-maker access and engagement mode, applies a bonus only for organiser-run matchmaking, and returns a short tiered list. Not for preparing a team for an event already chosen (see event-attendee-prep) or for the logistics of attending (see event-logistics-planning)."
sources:
  - "Conference recommendation (MIT, Dave Engel): the buyer-classification step that decides where buyers stand, the discovery categories and the aim for breadth, the famous-event audit, the 40, 40 and 20 scoring with tiers, the organiser-run matchmaking bonus, the cross-client check, the two-sentence description, and the review of outcomes after attendance"
  - "Removed: the named events, vendors, organisers and matchmaking programmes, the named tools, and the setup script. Event names were not verified and are not restated"
  - "Adapted for GTM-360: the tier cut-offs (80 and 70), the fifteen-event default cap and the ten-point bonus are the source's defaults, kept as author defaults to calibrate. The rule that budget is never scored is kept as a hard rule"
---

# Event selection scoring

## Purpose

Event spend is often chosen by habit: the best-known flagship, or the same circuit every year. This skill scores events against the buyer the company actually sells to, so the list differs from client to client and the spend can be justified.

## When to use

- A field sales or field marketing motion needs events chosen for the next year or quarter.
- Event spend has to be justified to a budget holder.
- A conference calendar is being planned for a team.

Route elsewhere when:
- The question is preparing for an event already chosen. Use `event-attendee-prep`.
- The question is the logistics of attending or exhibiting. Use `event-logistics-planning`.

## Inputs

- The ICP: buyer roles, target verticals, deal size range and sales cycle length.
- The geographic scope and the time window. The default window is the next twelve months.
- Events to force-include or force-exclude, including events already attended and events known to return little.
- The maximum number of events to return. The default is fifteen.
- The classification in step 1, confirmed with the user.

## Procedure

1. **Lock the buyer classification before scoring.** Decide where buyers stand at an event: in the audience, or behind the booths. Where the company sells to marketing, growth or sales roles, buyers often staff the booths, so the booth floor is the scoring target. Where it sells to other functions, the session tracks and the audience are the target. Ask the user if it is unclear. Do not guess.
2. **Confirm the intake.** Do not begin discovery until the classification and the inputs are confirmed. Budget is recorded as context for the final decision and is never scored.
3. **Discover with breadth, not habit.** Search current event listings rather than relying on recall. Cover six categories: industry flagships; narrow vertical summits with a specific buyer role; regional flagships in the target geography; free vendor-hosted conferences; emerging events in their first few years; and side events around the larger ones. In a fifteen-event set, aim for at least two per category. Where a category is empty for this client, record why.
4. **Audit the famous events.** For each well-known event on the list, write one line on why it beats a more targeted alternative for this client's ICP. Replace it with the targeted option where that line cannot be written.
5. **Score each event on a 100-point base.** Relevance (40): how closely the attendees match the ICP. Decision-maker access (40): the density of real buyers and the structural reach to them. Engagement mode (20): whether attendees are in a buying mindset or a learning mindset. Show the three sub-scores. Priority one is 80 and above. Priority two is 70 to 79. Events below 70 are excluded. These cut-offs are author defaults to calibrate.
6. **Apply the matchmaking bonus only where it is earned.** Add ten points only where the organiser runs matchmaking as a service and takes responsibility for pairing attendees with stated criteria. Self-serve booking in an event app does not qualify.
7. **Run the cross-client check.** If the same list would suit a different client in a different vertical, it is too generic. Replace the generic entries with vertical or regional alternatives.
8. **Write the output.** A summary, then a ranked table capped at the maximum count, with no padding. Each event gets two sentences. The first covers the audience and format, with numbers where they are verified. The second covers why this client's buyers need this offer now, and must not be interchangeable across events.
9. **Review after attendance.** After three to five events, compare the leads, meetings and pipeline per event with the predicted tier. If the predictions and results diverge, adjust the weights.

## Output

- The client profile and the locked buyer classification.
- The scoring method as applied, with the cut-offs used.
- Assumptions, data gaps and any unverified attendee or booth counts.
- The top five must-attend events, each with its score and a one-line reason.
- The ranked table: event, priority, location, dates, the three sub-scores, the total, and the two-sentence description.

## Quality bar

The classification is locked before scoring. Discovery covers every category by search. Each famous event passes the targeted-alternative test. Budget never moves a score. The list is not padded to a count. Watch for a list that would fit two different clients, attendee figures presented as fact when they are unverified, and self-serve app booking counted as matchmaking.

## Rules

- Lock the buyer classification before scoring.
- Search current listings. Do not rely on recall of well-known events.
- Never let budget move a score.
- Never pad the list. Events below the cut-off are excluded.
- Never reuse one client's list as another client's template.
- Show the three sub-scores, not only the total.
- Mark unverified attendee or booth counts as unverified.

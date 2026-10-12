---
name: gtm-command-center
version: 1.0.0
description: "Use when one GTM operator's work is spread across many tools and the day is spent switching between them. Builds one personal operating view that shows only the lanes the operator acts on, with one source of truth per lane, read-mostly, and a daily roll-up of what needs attention today. Includes a rule for keeping any shared view free of private working notes. Not for building a team dashboard of metrics (see revenue-metrics)."
---

# GTM command centre

## Purpose

An operator who checks four tools to find out what to do today is losing time reconstructing their own day. A command centre puts the lanes they act on in one place and shows what needs them now. Its value comes from what it leaves out. A surface that copies every tool becomes one more thing to keep in sync, and people go back to the tabs.

## When to use

- One person's work is spread across a task board, an outreach queue, research, content, and pipeline views.
- Important items get missed because they sit in a tool nobody checked.
- A morning view is wanted for prioritising the day.

Route elsewhere when:

- The question is a metrics dashboard for leadership. Use `revenue-metrics`.
- The question is the team's operating cadence. Use `revenue-operating-cadence`.

## Inputs

- A list of every surface the operator checks in a normal day.
- For each surface: the system of record, and whether the operator acts on it or only monitors it.
- Any audience who will see any part of the view.

## Procedure

1. **List the lanes, then cut.** Keep only the lanes where the operator takes action. Drop anything only monitored, unless it has a threshold that should trigger action.
2. **Assign one source of truth per lane.** Each lane mirrors one system of record. Never let a lane hold state that is also kept elsewhere. When two places disagree, the operator stops trusting the view.
3. **Keep the view read-mostly.** It shows status and links out. Allow only a few low-friction actions, such as marking an item done or adding a note. Anything heavier is done in the system of record.
4. **Set a refresh cadence** for each lane that matches how fast its data changes.
5. **Build the daily roll-up.** Each morning, assemble only the items that need the operator that day: overdue actions, replies waiting, deadlines this week, and any alert. Leave out anything that can wait.
6. **Separate private and shared views.** If any part of the view will be seen by a teammate, manager, or client, it must carry none of the operator's private working notes, raw scores, or internal labels. Build the shared view from a separate, clean source.
7. **Review the view every month.** Remove any lane that has not been acted on, and add one only when a recurring action needs it.

## Output

- The lane list, with the action taken on each and the source of truth for each.
- The refresh cadence per lane.
- The daily roll-up format, with its inclusion rules.
- The separation rule for any shared view.

## Quality bar

Every lane has one source of truth and an operator who acts on it. The view is read-mostly. The daily roll-up contains only what needs action today. Any shared view contains no private notes or raw scores. Watch for lanes that copy data already held elsewhere, views that have become editing tools, and private labels leaking into shared views.

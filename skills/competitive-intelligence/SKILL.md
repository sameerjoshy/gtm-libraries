---
name: competitive-intelligence
version: 1.0.0
status: draft-for-review
description: Use to track what named competitors are doing (funding, leadership, hiring, launches, partnerships), in a dated briefing that reports only new signals, or to prepare a competitor brief for a specific deal such as a displacement or renewal defence. Not for positioning or messaging analysis, which is competitive-white-space.
sources:
  - "Competitor monitoring (MIT, Alon Goldenberg), date verification, dedup memory, signal validation, quiet-period rule"
  - "Competitor intel (MIT, Yoni Tserruya), deal-context framing, displacement angles"
  - "Competitive intelligence radar (MIT, Sabahudin Murtic), monitoring cadence"
---

# Competitive intelligence

Tracks competitor moves with dated, verified signals, and produces either a periodic briefing or a deal brief.

## Purpose

Tell the team what changed at each competitor since the last report. Stale news presented as new is the main failure mode, so event dates are checked against the source, and quiet periods are reported as quiet.

## Inputs

- **Competitor list.** Confirmed by the user before the first run. Never research a list the user has not approved. If the user does not have one, propose three to five from searches on "[company] competitors", "vs" and "alternatives", then confirm.
- **For each competitor:** name, domain, category (direct, adjacent, incumbent), and two or three keywords for trend searches.
- **Mode.** Periodic briefing, or deal brief. For a deal brief, the deal context is required: displacement, renewal defence, or general prep.
- **Memory.** A per-competitor file of signals already reported, used for deduplication. Created on first run.

## Periodic briefing

1. **Choose the mode.** Full, if the last run was more than 14 days ago or this is the first run (window: 14 days). Quick, if last run was within 14 days (window: since last run, minimum 7 days). If a report already exists for today, ask before re-running.
2. **Load memory** and build the known-signal list for each competitor.
3. **Research** each competitor: news, funding and M&A, hiring, their changelog or release notes, and review-site movement. Also run two searches on the industry trends in the profile.
4. **Validate each signal.** Record the article date and the event date, separately. Take the event date from the article body, not the page header. Classify the source as primary (the company's own release or filing) or derivative (coverage of it). Priority: P1 for M&A, leadership changes, major funding, and direct product competition; P2 for launches, partnerships, and hiring waves; P3 for blog posts and minor hires.
5. **Classify** each signal as NEW, UPDATED, STALE, or UNCERTAIN. Only NEW and UPDATED are reported.
6. **Corroborate P1 signals.** A P1 signal sourced only from derivative coverage is dropped unless a primary source confirms it.
7. **Write** the briefing: TL;DR of three to five P1 signals, a section per competitor (with where they win and where the user wins), industry trends, a cross-competitor pattern if three or more competitors were covered, and implications. Competitors with no new signal are listed as quiet.
8. **Save** the briefing, and append only validated signals to each competitor's memory file. STALE and UNCERTAIN signals never enter memory.

## Deal brief

1. **Restate the deal context** in one line. If it is missing, ask once, then default to general and say so.
2. **Resolve** the competitor. Confirm the match if the name is ambiguous.
3. **Pull:** firmographics, news from the last 90 days, leadership moves, hiring by function (a surge is an investment signal, a gap is a weakness signal), and customer intent signals where a data source offers them.
4. **Triage against the deal context.** For displacement, a leadership departure outranks a launch. For renewal defence, a new feature outranks routine hiring.
5. **Displacement angles** (three to five), only if the user has supplied their own product context. Each angle names a specific signal happening at the competitor now, a way to use it, and one discovery question that brings it out without stating it.

## Output

- Periodic: a dated briefing file, with the memory updated.
- Deal: a brief with a TL;DR, company snapshot, leadership and hiring, news, intent (if available), displacement angles (if context supplied), and key takeaways.

## Quality checks

- Every reported signal has an event date and a source.
- A P1 signal from derivative coverage only is not reported.
- Nothing from a previous report repeats.
- Quiet competitors are listed as quiet.
- Contact names are shown as initials in any shared brief.
- Nothing is sent to a distribution list until the user approves the destination.

## Boundaries

- Monitoring and deal prep only. For positioning and messaging gaps, use `competitive-white-space`.
- Do not present a speculation about a competitor's plans as a signal. Label it as a hypothesis.

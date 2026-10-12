---
name: competitive-intelligence
version: 1.0.0
status: draft-for-review
description: Use to track what named competitors are doing (funding, leadership, hiring, launches, partnerships), in a dated briefing that reports only new signals, to prepare a competitor brief for a specific deal such as a displacement or renewal defence, or to create or update a six-section battlecard. Not for positioning or messaging analysis, which is competitive-white-space.
sources:
  - "Competitor monitoring (MIT, Alon Goldenberg), date verification, dedup memory, signal validation, quiet-period rule"
  - "Competitor intel (MIT, Yoni Tserruya), deal-context framing, displacement angles"
  - "Competitive intelligence radar (MIT, Sabahudin Murtic), monitoring cadence"
  - "Battlecard (MIT, Ido Goldberg / Swan): six-section format, evidence rule for strengths and weaknesses, rumour labelling, date-stamping, one-page length. Knowledge-store tool names and the traffic-estimate step are removed"
---

# Competitive intelligence

Tracks competitor moves with dated, verified signals, and produces either a periodic briefing or a deal brief.

## Purpose

Tell the team what changed at each competitor since the last report. Stale news presented as new is the main failure mode, so event dates are checked against the source, and quiet periods are reported as quiet.

## When to use

- The team needs a dated briefing on what has changed at its competitors since the last report.
- A live deal needs a brief on a named competitor, or a standing battlecard is needed.

Route elsewhere when:
- The question is where the market leaves room for a position. Use `competitive-white-space`.
- The question is the deal's qualification. Use `deal-qualification-gates`.

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

## Battlecard

Use when a team needs a standing competitor reference for live deals, not a dated report. Create one from scratch, or update an existing one by keeping what is still true and revising only what has gone stale.

1. Confirm the competitor's name and primary domain. Load any existing notes first.
2. Gather a small number of high-signal facts: the headline value proposition, the target customer, named customers from a case-study page, recent leadership, funding and partnership moves, and hiring by function. Do not pull everything.
3. Write six sections, in this order:
   - One-line description: what they sell and to whom.
   - Where they win: three to five genuine strengths. Do not strawman.
   - Where they lose: three to five weaknesses, each evidenced.
   - Common objections: "objection → response", three to six entries, each response under thirty words.
   - Win conditions: buyer profile, deal size, technical or regional factors where we win.
   - Where to push in a deal: demo emphasis, pricing posture, proof points.
4. Date-stamp it. Competitive facts go stale quickly.
5. Save it to the team's shared competitive knowledge, and return it to the user.

Battlecard rules:

- Every strength and weakness has a source. A rumoured point is labelled as reported, with where it was reported.
- Do not include legally sensitive claims, such as "their product is insecure", without a citation.
- Keep it to about one page (roughly 600 words).
- If the competitor has almost no public footprint, say so. The team may be preparing for a rival that rarely appears in deals, and should check that before investing in a card.

## Output

- Periodic: a dated briefing file, with the memory updated.
- Deal: a brief with a TL;DR, company snapshot, leadership and hiring, news, intent (if available), displacement angles (if context supplied), and key takeaways.

## Quality bar

- Every reported signal has an event date and a source.
- A P1 signal from derivative coverage only is not reported.
- Nothing from a previous report repeats.
- Quiet competitors are listed as quiet.
- Contact names are shown as initials in any shared brief.
- Nothing is sent to a distribution list until the user approves the destination.

## Boundaries

- Monitoring and deal prep only. For positioning and messaging gaps, use `competitive-white-space`.
- Do not present a speculation about a competitor's plans as a signal. Label it as a hypothesis.

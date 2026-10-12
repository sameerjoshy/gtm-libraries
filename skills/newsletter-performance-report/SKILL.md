---
name: newsletter-performance-report
version: 1.0.0
description: "Use to build a performance report for a newsletter sponsor, client, or owner that a non-technical reader can understand in under a minute and still trust. Covers audience growth, open and click rates with their denominators stated, audience segmentation, a month-over-month summary, an engaged-reader list, per-issue measures, and a refresh pattern that keeps the narrative in step with the numbers. Not for writing the issues (see newsletter-issue-formats) or the sponsor's own pitch."
---

# Newsletter performance report

## Purpose

A sponsor or client wants to know whether a newsletter is working, and they want to trust the numbers. A raw export does not do that. This skill builds a report that states what each figure means, shows the growth and the readers who engage, and stays accurate when it is refreshed.

## When to use

- A sponsor or client needs a regular report on a newsletter.
- A newsletter owner wants a clearer view of their own performance.
- A reporting process is being automated and the narrative risks drifting from the numbers.

Route elsewhere when:

- The question is what to write in the next issue. Use `newsletter-issue-formats`.
- The question is the welcome sequence. Use `newsletter-subscriber-onboarding`.
- The question is the sponsorship pitch. That is outside this library.

## Inputs

- Subscriber counts by date, with new subscribers and unsubscribes.
- For each issue: sends or deliveries, opens, clicks, and unsubscribes.
- Audience segments, if the publication holds them.
- The list of readers who clicked, for the engaged-reader export.
- The previous period's report, for comparison.

## The click-rate trap

Platforms often report a click rate whose denominator is opens, not deliveries. A low open rate then makes click rate look high, and the figure is misread. Always:
- state the denominator beside every rate,
- show the click rate on deliveries as well as on opens if the platform allows,
- never compare a click rate on opens with one on deliveries.

## Procedure

1. **Build the audience growth view.** Show subscriber count, net growth, and new subscribers by month, with unsubscribes shown beside them.
2. **Build the per-issue view.** For each issue: deliveries, opens, clicks, unsubscribes, with each rate's denominator stated.
3. **Build the segment view,** if segments exist. Show engagement by segment, with the minimum volume the team accepts before judging a segment.
4. **Write the month-over-month synopsis.** Three to five sentences: what grew, what fell, and the one thing to watch. Draft it from the figures, not from memory.
5. **Produce the engaged-reader export,** listing readers who clicked in the period, for the owner's own use. Check the export against the privacy rules that apply to the list.
6. **Add the per-issue measures** that matter to the sponsor, such as clicks on the sponsored item, set out separately from newsletter-wide figures.
7. **Set up the refresh.** Regenerate the narrative from the figures each time the report runs. Do not edit the narrative by hand between runs, because it drifts from the numbers.

## Output

- The report, with the growth view, the per-issue view, the segment view, and the synopsis.
- Every rate shown with its denominator.
- The engaged-reader export, for the owner.
- The refresh plan, with the rule that narrative is regenerated from the figures.

## Quality bar

Every rate states its denominator. No click rate on opens is compared with one on deliveries. The synopsis is drafted from the current figures. The engaged-reader export respects the list's privacy rules. Watch for a click rate presented without its denominator, a narrative left over from a previous period, and segments judged on a handful of readers.

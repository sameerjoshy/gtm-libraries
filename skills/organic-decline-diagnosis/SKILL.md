---
name: organic-decline-diagnosis
version: 1.2.0
description: "Use when B2B organic search traffic has fallen, to decide whether the loss is a healthy shift in how people consume answers (more answers shown without a click, while visibility holds) or a real threat to pipeline (visibility is falling too). Runs two stages: first compare impressions with clicks for identical queries, then split queries into brand, non-brand commercial, and non-brand informational, and correlate each with pipeline before routing the fix. Not for finding new topics (see `seo-topic-research`)."
---

# Organic decline diagnosis

## Purpose

A fall in organic traffic does not always mean lost demand. When search engines answer more questions directly, impressions can hold while clicks fall, and that is a different problem from losing visibility. Treating the two the same leads to the wrong fix. This skill separates them, then checks whether the loss touches pipeline.

## When to use

- Organic clicks have fallen, and the team is deciding what to do.
- A report shows less traffic, and leadership asks whether the channel is in trouble.
- A content investment is under review after a fall in clicks.

Route elsewhere when:

- The question is which new topics to build. Use `seo-topic-prioritization`.
- The question is whether a specific keyword can be won. Use `seo-serp-qualification`.
- The question is how the business is cited in AI answers. Use `answer-engine-citation-drill-down`.

## Inputs

- Impressions and clicks for the same queries over two matching periods.
- Search queries grouped by intent: the brand, the non-brand commercial, and the non-brand informational.
- Pipeline or conversion data for the same periods, linked to organic landing pages if possible.

### Stage one: visibility against clicks

1. **Use matching periods** of equal length, and compare the same queries across both.
2. **Calculate the click-through rate** for each query in each period.
3. **Classify:**
   - If impressions hold or grow while clicks fall, label it **Zero-Click Shift**. People are still seeing the business, but fewer click through.
   - If impressions and clicks fall together, label it **Visibility Loss**. The business is being seen less.
   - If neither pattern is clear, say so, and do not label.

### Stage two: intent and pipeline

1. **Segment queries** into brand, non-brand commercial, and non-brand informational.
2. **Correlate each segment with pipeline** for the same period. A fall in informational clicks with no change in commercial pipeline is a different situation from a fall in commercial clicks that reduces pipeline.
3. **Route the fix:**
   - **Zero-Click Shift** on informational queries: keep the content for visibility and brand, and move effort to commercial pages where clicks still matter.
   - **Visibility Loss** on commercial queries: this is a pipeline threat. Review the pages that have lost visibility, their relevance, and their competitors.
   - **Loss on brand queries:** check the brand's own search presence and the pages that should rank for the company name.

## Procedure

1. **Confirm the periods** match and the queries are the same.
2. **Run stage one** and record the label for each query group.
3. **Run stage two,** segmenting by intent and linking to pipeline where the data allows.
4. **Route the fix** using the table above.
5. **Set a re-check date** for the chosen actions.

## Output

- The label for each query group, with the figures behind it.
- The intent segmentation, with the pipeline link or a note that it is not available.
- The routed fix, and the re-check date.

## Quality bar

Matching periods and identical queries are used. A label is applied only when the pattern is clear. Pipeline is checked before the decline is called a threat. Watch for a fall in total clicks treated as a visibility loss without checking impressions, and a Zero-Click Shift labeled where the commercial pipeline has also fallen.

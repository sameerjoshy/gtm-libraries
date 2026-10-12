---
name: paid-audience-segment-diagnostic
version: 1.0.0
status: draft-for-review
description: "Use when a team has demographic performance data for paid ads (results broken down by industry, country, company size, job title, function, and seniority) and needs to know who is engaging, which segments convert efficiently at an acceptable cost, and what to change. Requires a minimum volume per segment before any segment is judged, separates engagement from conversion, and ends with a short list of segment changes. Not for reach and frequency (see paid-audience-reach-diagnostic) or for choosing the offer (see paid-offer-strategy)."
sources:
  - "Audience segment diagnostic (MIT, Justin Rowe): the question of who the buyers are, how efficiently they are reached, and what to change, applied across six demographic dimensions (industry, country, company size, job title, function, and seniority) with cost per lead and conversion measures"
  - "Removed: the named signals tool and its dashboard and document outputs, and the external link. The six dimensions are kept as the breakdown"
  - "Adapted for GTM-360: the minimum volume per segment before judgement, and the rule that a segment with high engagement but poor conversion is reported as an engagement finding, not a success, are author defaults and additions"
---

# Paid audience segment diagnostic

## Purpose

Paid campaigns can attract many clicks from the wrong people. A segment that engages is not the same as a segment that converts at an acceptable cost. This skill breaks the results down by who the audience is, judges each segment on conversion and cost, and gives a short list of changes.

## When to use

- A team has demographic performance data and wants to know which personas convert.
- Cost per lead is rising, and the team does not know which audience is responsible.
- A new audience is being tested, and the team wants to know which segments to keep.

Route elsewhere when:

- The question is how often people see the ads. Use `paid-audience-reach-diagnostic`.
- The question is the offer or message. Use `paid-message-validation`.
- The question is the ICP definition itself. Use `icp-builder`.

## Inputs

- Performance by segment across the six dimensions: industry, country, company size, job title, function, and seniority.
- For each segment: impressions, clicks, cost, click-through rate, conversions, leads, and cost per lead.
- The business's acceptable cost per lead or per opportunity.
- The minimum volume the team will accept before judging a segment.

## Procedure

1. **Set the minimum volume.** Exclude any segment below it from judgement. A segment with a handful of conversions is noise, not a finding. Report excluded segments as untested.
2. **Separate engagement from conversion.** For each segment, compare click-through rate with conversion rate. A segment with strong engagement and weak conversion is an engagement finding, not a success.
3. **Judge cost against the acceptable figure.** Mark each qualifying segment as efficient, acceptable, or expensive, against the business's cost limit.
4. **Look across the six dimensions.** A pattern that appears in several dimensions, such as one seniority band converting well in several industries, is stronger than a single high result.
5. **Identify the winners and the losers.** List the segments that are efficient and volume-sufficient, and those that are expensive and volume-sufficient.
6. **Recommend changes:**
   - shift budget toward efficient segments, within the limits the team already uses for budget moves;
   - exclude or reduce expensive segments with sufficient volume;
   - test untested segments that share a pattern with the winners;
   - check whether a losing segment is losing because of the offer rather than the audience.
7. **Set the re-check** after the changes have run for a stated period.

## Output

- The segments judged, with volume, engagement, conversion, and cost against the limit.
- The untested segments, with the volume they lack.
- A short list of changes, each with its reason and re-check date.

## Quality bar

No segment is judged below the volume minimum. Engagement is never reported as success without conversion. Recommendations follow a pattern across dimensions where one exists. Watch for a winning segment chosen on a few conversions, clicks treated as results, and a losing audience cut when the offer is the real problem.

---
name: pipeline-review
description: Use when reviewing a live pipeline for coverage, stage aging, and risk before a forecast call.
version: 0.0.0-placeholder
status: PLACEHOLDER
---

# pipeline-review

Status: PLACEHOLDER. The steps below are assumed for structure only and must be replaced with the real procedure before use on client data.

## Purpose

Review pipeline health and name the deals that need action this week.

## Inputs

CRM opportunity export with stage, amount, close date, last activity date, and owner.

## Steps (assumed)

1. Validate inputs against `context/` and `definitions/`. Stop if required context is missing or dated more than 90 days.
2. Run the core analysis described in Purpose. Thresholds and weights are PLACEHOLDER values and must be recorded with a reason.
3. Produce the output below.
4. Run the eval cases in `evals/pipeline-review/` before this version is tagged.

## Output

Coverage ratio, stage aging table, top risks by deal name with one next action each.

## Boundaries

- Covers this one job only. Hand off other work to the named skill, not inline.
- Never state a benchmark or threshold as an industry standard unless the source is cited.
- Never claim causation from correlation in output.

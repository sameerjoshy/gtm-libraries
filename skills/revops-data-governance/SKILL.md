---
name: revops-data-governance
description: Use when CRM data quality, field definitions, or data ownership are causing forecast or reporting errors.
version: 0.0.0-placeholder
status: PLACEHOLDER
---

# revops-data-governance

Status: PLACEHOLDER. The steps below are assumed for structure only and must be replaced with the real procedure before use on client data.

## Purpose

Audit CRM data quality and propose governance rules for key fields and stages.

## Inputs

CRM field list, sample records, stage definitions, reporting issues reported by the client.

## Steps (assumed)

1. Validate inputs against `context/` and `definitions/`. Stop if required context is missing or dated more than 90 days.
2. Run the core analysis described in Purpose. Thresholds and weights are PLACEHOLDER values and must be recorded with a reason.
3. Produce the output below.
4. Run the eval cases in `evals/revops-data-governance/` before this version is tagged.

## Output

Data quality scorecard by field, governance rules with owners, and a prioritized fix list.

## Boundaries

- Covers this one job only. Hand off other work to the named skill, not inline.
- Never state a benchmark or threshold as an industry standard unless the source is cited.
- Never claim causation from correlation in output.

---
name: icp-builder
description: Use when building, validating, or scoring an ideal customer profile, or when the user says ICP is too broad, unclear, or missing.
version: 0.0.0-placeholder
status: PLACEHOLDER
---

# icp-builder

Status: PLACEHOLDER. The steps below are assumed for structure only and must be replaced with the real procedure before use on client data.

## Purpose

Build or validate a client's ICP from closed-won data, interviews, and firmographics, and produce a scoring rule for accounts.

## Inputs

Closed-won and closed-lost deals with firmographics. Customer interview notes if available. Existing ICP draft if any.

## Steps (assumed)

1. Validate inputs against `context/` and `definitions/`. Stop if required context is missing or dated more than 90 days.
2. Run the core analysis described in Purpose. Thresholds and weights are PLACEHOLDER values and must be recorded with a reason.
3. Produce the output below.
4. Run the eval cases in `evals/icp-builder/` before this version is tagged.

## Output

ICP document in context/icp.md format, scoring rule with weights and thresholds, and a list of open validation questions.

## Boundaries

- Covers this one job only. Hand off other work to the named skill, not inline.
- Never state a benchmark or threshold as an industry standard unless the source is cited.
- Never claim causation from correlation in output.

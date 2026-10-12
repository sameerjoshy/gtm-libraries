---
name: account-tier-scoring
description: Use when tiering accounts into Bronze, Silver, Gold, or Diamond based on fit and intent signals.
version: 0.0.0-placeholder
status: PLACEHOLDER
---

# account-tier-scoring

Status: PLACEHOLDER. The steps below are assumed for structure only and must be replaced with the real procedure before use on client data.

## Purpose

Assign each account a tier with a short reason, using a documented scoring rule.

## Inputs

Account list with firmographics and intent signals. ICP from context/icp.md. Scoring weights (PLACEHOLDER).

## Steps (assumed)

1. Validate inputs against `context/` and `definitions/`. Stop if required context is missing or dated more than 90 days.
2. Run the core analysis described in Purpose. Thresholds and weights are PLACEHOLDER values and must be recorded with a reason.
3. Produce the output below.
4. Run the eval cases in `evals/account-tier-scoring/` before this version is tagged.

## Output

Tiered account list with score, tier, and the top two drivers per account. Weights and thresholds listed at the top of the output.

## Boundaries

- Covers this one job only. Hand off other work to the named skill, not inline.
- Never state a benchmark or threshold as an industry standard unless the source is cited.
- Never claim causation from correlation in output.

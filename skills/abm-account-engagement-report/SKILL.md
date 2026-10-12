---
name: abm-account-engagement-report
description: Use when the user has account-level LinkedIn ad data (rate accounts CSV) plus pipeline data and wants a client-facing ABM engagement dashboard with funnel, leaderboard, segments, and action plan.
version: 0.0.0-placeholder
status: PLACEHOLDER
---

# abm-account-engagement-report

Status: PLACEHOLDER. The steps below are assumed for structure only and must be replaced with the real procedure before use on client data.

## Purpose

Produce a client-facing ABM account engagement dashboard from ad platform exports and pipeline data.

## Inputs

Rate accounts CSV (required or pipeline data required). Pipeline rows: company, contact, source, stage, keyword, campaign. Client context from context/client-*.md.

## Steps (assumed)

1. Validate inputs against `context/` and `definitions/`. Stop if required context is missing or dated more than 90 days.
2. Run the core analysis described in Purpose. Thresholds and weights are PLACEHOLDER values and must be recorded with a reason.
3. Produce the output below.
4. Run the eval cases in `evals/abm-account-engagement-report/` before this version is tagged.

## Output

One self-contained HTML dashboard named [Client]_ABM_Account_Engagement_Dashboard.html plus a three to four sentence chat summary. Full spec: paste the complete SKILL text here, replacing these assumed steps.

## Boundaries

- Covers this one job only. Hand off other work to the named skill, not inline.
- Never state a benchmark or threshold as an industry standard unless the source is cited.
- Never claim causation from correlation in output.

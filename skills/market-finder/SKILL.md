---
name: market-finder
version: 1.0.0
status: draft-for-review
description: "Use to map every business of one type in one geography, for territory planning, market sizing, or building an account universe. Also audits an existing account list against fresh discovery, showing which accounts match, which were found only by discovery, and which were on the list but not found, with a coverage figure. Produces a deduplicated, source-linked inventory with a confidence rating per entity. Not for monitoring named competitors over time or for deep research on one company (see account-research-brief)."
sources:
  - "Market finder (MIT, Uri Knorovich): mode detection between discovery and audit, scoping to business type and geography, quick-scan versus comprehensive depth, three-way comparison in audit mode (matched, discovered only, reference only) with a coverage score, mandatory source link per entity, never running an audit against an imagined list"
  - "Removed: the vertical presets and per-metro query patterns in the source's reference file, and the named data sources, which are replaced by a generic source-selection step"
  - "Adapted for GTM-360: quick scan is the default depth; the top-five enrichment and verification limit in quick scan is an author default"
---

# Market finder

## Purpose

A territory plan, a market size, or an account list is only as good as the universe behind it. This skill lists every business of the target type in the target area, from several sources, removes duplicates, and rates how sure the team can be of each one. It can also check an existing list, so gaps are found before a campaign relies on the list.

## When to use

- Territory planning or market sizing for a business type in a geography.
- Building an account universe from scratch.
- Checking an existing account list for gaps.

Route elsewhere when:

- The question is the ideal customer profile. Use `icp-builder`.
- The question is scoring accounts already on the list. Use `account-tier-scoring`.
- The question is one company in depth. Use `account-research-brief`.

## Inputs

- The business type (required), and the geography (required, unless the market is software and is not bound by place).
- Any qualification criteria, such as a minimum size or a required web presence.
- Depth: quick scan or comprehensive.
- In audit mode: the existing list, as a file or a list of at least three businesses.

## Procedure

1. **Detect the mode.** If a list is supplied, or the request is to audit or compare, use audit mode. Otherwise use discovery. If the mode is unclear, ask one question. If audit language is used without a list, ask for the list. Never audit against a list that does not exist.
2. **Scope the request.** Confirm the business type and geography in one line, or ask one combined question. Do not ask a series of small questions.
3. **Choose the depth.** Quick scan: one discovery pass, with enrichment and verification for the top five only. Comprehensive: all sources, retries, full enrichment, and verification of every entity. Use quick scan unless the user wants the complete universe.
4. **Run discovery** across the relevant sources. Deduplicate by name and address, or by domain where the business has one.
5. **Rate each entity** on how sure the team can be of it: whether it is confirmed by more than one source, whether it is current, and whether it meets the qualification criteria. Keep a source link for every entity. Entities without a source link are not listed.
6. **In audit mode, compare the lists.** Sort every business into one of three groups:
   - Matched: on both the existing list and in discovery.
   - Discovered only: found by discovery, missing from the list.
   - Reference only: on the list, not found by discovery.
   Report a coverage figure: matched divided by the existing list's size, with the size stated. Check the reference-only group before removing anything, since discovery can miss a business that is real.
7. **Stop at the inventory.** Scoring, tiering, and outreach are separate steps.

## Output

- Discovery: the deduplicated inventory, with source links and a confidence rating for each entity, and the depth used.
- Audit: the three groups, the coverage figure with the list size, and the reference-only businesses for review.
- A note on any source that could not be reached.

## Quality bar

Every entity has a source link. Audit results are reported in three groups, with a coverage figure and its base. The reference-only group is reviewed before any removal. Watch for audits run against no list, entities listed without a source, and coverage figures given without their base.

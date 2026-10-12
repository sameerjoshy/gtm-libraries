---
name: tam-build-and-sizing
version: 1.0.0
status: draft-for-review
description: Use to size a total addressable market and turn it into a company list with honest coverage. Covers the ICP definition, company enumeration with provenance, TAM, SAM, and SOM, revenue sizing with a confirmed contract value, and coverage of the existing CRM. Companies first; contacts are a later stage. Not for the ICP definition on its own (see icp-builder) or account research (see account-research-brief).
sources:
  - "Build and fill a TAM (MIT, Ryan Iyengar), governed batches, coverage burn-up, rules on capped results"
  - "TAM builder (MIT, Tanyo Gochev), companies-first stage, root-domain dedup, saturation logging, unknown tier"
  - "TAM from verified data (MIT, Yoni Tserruya), TAM, SAM, SOM layers and segment ranking"
---

# TAM build and sizing

Produces a defensible market size and a company list, with each number's source and limits stated.

## Purpose

Give a market number that a finance lead can check, and a company universe that can be filtered into a campaign without cleaning.

## Inputs

- **ICP definition.** Industry, company size, geography, business model, disqualifiers. Ask for the minimum (industry, size, geography) if missing.
- **Counting unit:** companies, not contacts. Decide how subsidiaries, franchises, and multi-brand groups are counted.
- **Contract value.** Median or trimmed mean of comparable closed-won deals, annualised. Never use a price-page maximum or an unlabelled range.
- **Existing CRM export** (optional), to measure coverage.

## Procedure

1. **Freeze the ICP.** Write inclusion and exclusion rules before counting. Separate required filters from preferences, and note which filters each source can measure.
2. **Enumerate companies.** Retrieve from a source that returns matching companies. Record the source, query date, filters applied, filters omitted, and any cap. A count alone is a count estimate, not a list.
3. **Deduplicate on root domain,** not company name. Name variants are common; domains are stable.
4. **Cross-check** with a second method (registry, known-account sample, or CRM classification). Investigate large gaps before averaging.
5. **Record provenance** on every field: source, date, and confidence. Do not infer a field that can be retrieved.
6. **Log saturation.** Run additional queries until new domains per query approach zero. Record the yield curve. If the run was capped, say so.
7. **Separate the tiers.** Verified-size companies and unknown-size companies are reported as separate numbers. Unknown is not disqualified.
8. **Size revenue:**
   - Account TAM = eligible accounts.
   - Revenue TAM = eligible accounts multiplied by confirmed annual contract value.
   - Contact target = eligible accounts multiplied by buying roles per account.
9. **SAM and SOM.** SAM applies the must-have criteria and removes thin-coverage segments. SOM keeps only accounts with active signals in the last 90 days. Note that SOM changes each quarter.
10. **Measure current coverage** (if a CRM export is given). Classify each CRM account as in-TAM, out-of-TAM, or unknown against the same ICP. Only in-TAM accounts count as coverage. Report account, contact, and role coverage separately.
11. **Rank segments** by company count, coverage ease, and signal density. Name the top three.
12. **Plan any fill in governed batches.** Resolve identity before creating records. Review cost and sample quality before each batch. Creation and spend require approval. Research and planning can run freely.

## Output

- A TAM summary table: TAM, SAM, SOM, each with companies, contact target, and notes.
- Breakdown by industry, size, geography, and funding stage, each with a signal-density column.
- Segment ranking with the reason for each.
- Coverage report: verified and unknown tiers, saturation log, cap disclosure, CRM coverage (if measured).
- A list of companies, one row per company, deduplicated on domain, with provenance columns.
- Recommended next step: which segment to build a territory from first.

## Quality bar

- Each number names its source, date, unit, and main limitation.
- Account, revenue, contact, and role coverage are never combined.
- Any capped result is labelled a floor, not the universe.
- A CRM account counts as coverage only if it is in-TAM.
- If verified in-TAM accounts already exceed the estimate, revise the estimate upward rather than forcing the count down.
- No ETA is projected from fewer than three comparable snapshots.

## Boundaries

- Sizing and enumeration only. Contact finding and email verification come after the list is approved.
- Contract value is the input to revenue sizing. Do not guess it.

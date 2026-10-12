---
name: meddpicc-gap-audit
version: 1.0.0
description: "Use before a forecast call, a stage change, or after a new call or email that could change qualification. Maps MEDDPICC evidence (Metrics, Economic buyer, Decision criteria, Decision process, Paper process, Identify pain, Champion, Competition) from the call and email record, cites the exact line behind every mapping, flags reversals between calls, and reconciles against CRM values where they exist. Not for scoring call behaviour (see call-scoring) or for the evidence gates in deal-qualification-gates."
---

# MEDDPICC gap audit

## Purpose

A deal's qualification field says what the rep believes. A gap audit checks what the buyer actually said. The audit maps each MEDDPICC component to evidence, shows the evidence, and separates three states: verified, unverified, and confirmed risk. A confirmed risk is a finding; an unverified component is a data gap. Both need different actions.

## When to use

- A deal is headed into a forecast call.
- A stage change is proposed.
- A new call or email might change the qualification picture.
- Someone asks what is actually missing on a deal.

Route elsewhere when:

- The question is how the rep performed on the call. Use `call-scoring`.
- The question is the evidence gate before a stage advances. Use `deal-qualification-gates`.

## Inputs

- At least one call transcript or email thread for the deal. Without one, stop: there is nothing to audit.
- The current CRM qualification values, if available, as the baseline to reconcile against.
- The deal stage and the forecast date.

## Procedure

1. **Order the sources chronologically.** The most recent statement is the current status, unless it reverses an earlier one.
2. **Attribute the speaker.** Resolve who said each line from metadata, then CRM contacts, then a guess that must be confirmed before use.
3. **Check the speaker's side.** A seller describing their own product is not evidence of the buyer's pain or criteria. Discard or re-flag any mapping that fails this check.
4. **Map each component with a quote.** A paraphrase is not a citation. Quote the line or lines that support each mapping.
5. **Flag reversals.** If a budget confirmed earlier is now unconfirmed, cite both statements. Added detail that does not conflict is enrichment, not a reversal.
6. **Grade each component on two axes.** Defensible: a real citation exists, not a restated field. Favourable: the answer is good for the deal. A well-cited "no budget confirmed" is defensible and is a confirmed risk, not a data gap.
7. **Reconcile against the CRM, if values were supplied.** Where the CRM is blank and the source speaks to the component, that is a fillable gap with its citation attached. Where they disagree, name the type of disagreement: a hard conflict (a number or a name) is different from a maturity mismatch (a status the source does not support). Apply the defensibility test to the CRM entry too. If no CRM values were supplied, say so.
8. **Stop at the next action.** Name the one or two gaps that matter most at this stage and who could close each one.

## Stage weighting

Weight gaps by stage. Before a forecast, the economic buyer, decision process, and paper process carry the most weight, because a deal without them cannot be forecast. Early discovery can tolerate open paper process. Say which weighting you applied.

## Output

- A table with one row per component: status, the cited evidence, its date and speaker, and whether it is defensible and favourable.
- Reversals, with both quotes.
- Confirmed risks and data gaps, listed separately.
- Reconciliation against CRM values, if supplied, with conflict type named.
- The two or three actions that would close the highest-weighted gaps.

## Quality bar

Every mapping has a quote and a speaker. No component is marked verified from a restated CRM field. Reversals are shown, not hidden. Watch for mappings taken from the seller's own pitch, CRM values copied as evidence, and gaps treated as risks, or the reverse.

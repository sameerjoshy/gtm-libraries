---
name: candidate-sourcing-and-ranking
version: 1.0.0
status: draft-for-review
description: Use when a hiring manager or founder needs to source candidates for an open role, but the brief is incomplete, over-titled, or likely to produce a noisy list. Diagnoses the role's real scope against the company's stage, sets must-haves apart from transferable evidence, previews the market before any paid lookup, ranks candidates in three evidence-based tiers, and returns a shortlist the hiring team can defend. Not for offer and close (see sales-hire-offer-close) or for scoring interviews (see sales-hire-scorecard).
sources:
  - "Source and rank candidates from a hiring brief (MIT, Nylan Richard): diagnosing the role before searching, challenging title inflation against company stage, confirming a five-part search thesis, a small preview with a calibration question, enrichment limited to a reviewable pool, ranking on professional evidence in three tiers, separating role fit from contactability, and requesting approval before any message or system write"
  - "Removed: the named data source, the named candidate workbook, and the reference files for intake and scoring. Scoring is described in general terms, and each team sets its own weights"
  - "Adapted for GTM-360: the rule that a missing contact detail is not a sign of a weak candidate is kept as a hard rule. The review capacity guidance is the source's, with the twenty-candidate figure as an author default"
---

# Candidate sourcing and ranking

## Purpose

A job title is a poor search filter. Many candidate lists are long because the brief is vague, not because the market is large. This skill fixes the brief first, then searches, then ranks on evidence, so the hiring team can see why each candidate is on the list and disagree with any one criterion without starting again.

## When to use

- An open role has an incomplete, inflated or contradictory brief.
- A search has already produced a long list that the hiring team cannot evaluate.

Route elsewhere when:

- The question is closing a candidate. Use `sales-hire-offer-close`.
- The question is scoring interviews. Use `sales-hire-scorecard`.
- The question is hiring signals inside accounts. Use `hiring-signal-tracking`.

## Inputs

- Why the role exists now, and what must change after the hire.
- The real scope: individual contributor, team lead, or manager of managers.
- The company's stage, team size, reporting line, and working model.
- Must-have capabilities, and the evidence that would only reassure.
- Location, time zone, and pay constraints.
- Talent pools the team admires, companies to exclude, and the company's own domain.
- What failed in the last search for this role, if there was one.

## Procedure

1. **Diagnose the role.** Challenge title inflation and stage mismatch. A "VP" at a fifteen-person company may be a hands-on lead. A "senior" at a large enterprise may own less than a lead at a start-up. Translate the title into outcomes and scope before using it as a filter.
2. **Confirm the search thesis** in five parts: outcomes in the first twelve months; non-negotiable evidence; transferable evidence and acceptable neighbours; context constraints; exclusions and the target count. Ask the user to correct the weakest assumption.
3. **Build the search ladder:** title families, seniority range, the experience evidence required, the company contexts, and the geography. Use broad title families. Titles are noisy and should not carry the whole search.
4. **Preview the market before any paid enrichment.** Ask whether the search returns enough plausible candidates, not merely enough rows. If the pool is empty, loosen one constraint and say which. If it is too small, separate an unrealistic brief from a thin dataset. If it is too large, tighten on outcome evidence, not on prestige.
5. **Calibrate.** Show five representative profiles and ask which is closest and which is clearly wrong. Refine the thesis once before scaling.
6. **Exclude** current employees of the hiring company, and anyone already rejected for this role where that history exists. Remove duplicate profiles.
7. **Set the review capacity before collecting contact data.** Twenty well-researched candidates are more useful than two hundred thin ones. As an author default, cap the paid enrichment at the number the team can actually review.
8. **Request approval before any paid lookup,** showing the candidate count, the fields requested, and the cost or quota impact. Enrich only the approved pool. Keep the source and retrieval date for each record.
9. **Rank on professional evidence,** using a scorecard the team agrees. Score only what is visible in the evidence. Keep role fit separate from contactability.
10. **Tier the candidates:**
    - Tier 1, contact first: meets the non-negotiables and has specific evidence for the core outcome.
    - Tier 2, validate: credible transferable fit, with one question to test.
    - Tier 3, reserve: partial fit, relevant only if the thesis broadens.
11. **Write a rationale for each Tier 1 candidate:** current scope, career path, evidence against each must-have, the largest unknown, and why this person comes before the next. A senior title or a famous employer is never a rationale on its own.
12. **Recommend the next action** from verified availability and role context. Do not infer willingness to move, notice period, pay expectations or personal circumstances.
13. **Request separate approval** before any message is sent, any record is written to an applicant system or CRM, or any sequence starts.

## Output

- The search thesis, the funnel counts, and the tier breakdown.
- Tier 1 profiles with their rationales, and short summaries of Tiers 2 and 3.
- Data coverage, reported separately from candidate quality.
- The unresolved questions for the hiring team.

## Quality bar

Every Tier 1 recommendation cites evidence and names one uncertainty. Titles are checked against stage and scope. Paid lookups happen only on an approved pool. A missing contact detail is not treated as a weakness. Watch for a long list that copies the job title, enrichment before the preview, and a ranking that uses a famous employer as its only reason.

## Rules

- Capture the hiring company's domain and exclude its current employees.
- Keep must-haves, transferable evidence and preferences apart.
- Calibrate titles against company stage and actual scope.
- Never infer personal circumstances, pay expectations or intent to move.
- Get approval before any paid lookup, message, system write or sequence.

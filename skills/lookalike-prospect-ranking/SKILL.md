---
name: lookalike-prospect-ranking
version: 1.0.0
status: draft-for-review
description: "Use when one proven person (a customer champion, a closed-won buyer, a strong operator) is the model and the team wants more people with the same useful characteristics. Defines a similarity signature from the attributes that plausibly explain the success, agrees hard constraints with the user, widens the search one dimension at a time with a record of each step, scores candidates with visible components, and returns a shortlist where every inclusion can be challenged. Not for account-level lookalikes (see closed-won-replication-play) or for paid audience building (see paid-social-audience-strategy)."
sources:
  - "Rank people who resemble a proven profile (MIT, Nylan Richard): reading the seed from the current role record rather than the headline, separating outcome-linked, contextual and incidental attributes, confirming the signature and which dimensions are hard constraints before searching, widening one dimension at a time and recording each relaxation, scoring with visible components, quality bands, a limited manual adjustment, and tuning the definition of similarity from user feedback"
  - "Removed: the named data source, the named scoring workbook, and the worked example file. The 100-point model and its weights are not restated; a team sets its own weights"
  - "Adapted for GTM-360: the quality bands are author defaults, and the rule that resemblance never implies willingness to buy or move is an author addition consistent with the library's approval rule"
---

# Lookalike prospect ranking

## Purpose

"Find more people like this one" is a request that often returns twenty people who share a job title. This skill makes the search explainable: it decides which attributes made the seed person useful, searches on those, and shows why each shortlisted person resembles the seed. Every inclusion and every score can be challenged.

## When to use

- One customer champion, buyer or operator is a proven fit, and more of the same are wanted.
- The team wants to test whether a profile is a repeatable pattern or a one-off.

Route elsewhere when:

- The model is an account rather than a person. Use `closed-won-replication-play`.
- The output is an ad audience. Use `paid-social-audience-strategy`.
- The question is the buying committee in one account. Use `account-org-map`.

## Inputs

- The seed person's current role record: title, employer, location, tenure, and the relevant skills and history. Prefer the role record to the profile headline, which may be stale or aspirational.
- The purpose of the search, such as prospecting, peer mapping, or a partner shortlist.
- Any exclusions, including the seed's own employer. For net-new prospecting, exclude it by default.
- The target count, and the constraints the user will accept.

## Procedure

1. **Sort the seed's attributes into three groups:**
   - outcome-linked: plausibly connected to why the seed worked, such as owning the relevant function at a company of the right stage;
   - contextual: constraints such as geography, language or market;
   - incidental: details that are present but have no demonstrated connection to fit.
2. **Propose a similarity signature.** Cover the function and title family, seniority and scope, the company's sector or model, its size band or stage, geography, and career pattern where it matters. Use only the outcome-linked and contextual attributes.
3. **Confirm with the user** which dimensions are hard constraints and which are scoring preferences, and the target count. Ask: which two characteristics made this person a success? If the user cannot say, keep the first run small and treat it as a test of the hypothesis, not as a settled ideal profile.
4. **Preview before any paid lookup.** Search on the core role family, not the full title string. Apply hard constraints in the search and keep soft dimensions for scoring.
5. **Widen one dimension at a time** if the pool is too small, in this order unless the user says otherwise: title wording within the same function, an adjacent company size band, an adjacent sector, broader geography, one seniority level up or down. Record which relaxation produced each new candidate. Never drop all filters to manufacture volume.
6. **Score transparently.** Use a weighted model that the team agrees, adjusted to the confirmed outcome-linked attributes. Show the total and each component score. Remove the seed and duplicates before ranking.
7. **Apply quality bands,** as author defaults: strong at 75 to 100 for immediate review; directional at 60 to 74, where one important dimension differs; weak below 60, excluded unless the user wants exploration. Career trajectory may move a candidate by at most 10 points, with the reason stated.
8. **Present the shortlist** with the name, current role, company context, location, total score, component scores, and one sentence on why the person resembles the seed. Name the largest mismatch.
9. **Stop for approval.** Do not enrich contact details, export a paid dataset, write to a CRM, or start outreach until the user approves the shortlist. Enrich only the approved names.
10. **Learn from disagreement.** Ask which top result is surprisingly good and which is clearly wrong. Change a weight or a constraint, rerank the same pool, and search again only if the pool is still too thin.

## Output

- The similarity signature, with its hard constraints and scoring preferences.
- The search log, with each relaxation and the candidates it added.
- The scored shortlist, with components, the largest mismatch, and the reason for each inclusion.
- The count shortfall, if fewer candidates clear the bar, with a specific widening plan.

## Quality bar

Each row answers: what specifically makes this person like the seed? Incidental resemblance is not used. Every relaxation is recorded. Scores show their components. Nothing is enriched or activated without approval. Watch for twenty people who share a title, a silent drop of filters, and resemblance treated as evidence of intent to buy or move.

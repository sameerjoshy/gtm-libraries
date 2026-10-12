---
name: signal-campaign-build
version: 1.1.0
description: "Use to turn an observable market event, such as a funding round, a regulatory change, or a hiring pattern, into a small, defensible outbound campaign. Produces a signal thesis with its false-positive definition, an evidence record for each account, a buyer map for accounts that pass, staged channel drafts, and a quality gate before launch. Use when someone asks who to contact now, which companies show a problem, or how to build a campaign around an event. Not for choosing among ready-made plays (see signal-outbound-plays) or for detecting signals in depth (see signal-detection-and-timing)."
---

# Signal to campaign

## Purpose

A visible event is not a buying signal. Teams often collect a list of companies that match a trigger, enrich hundreds of contacts, and write personalization from one keyword. This skill works the other way round. It first proves the signal carries a real problem, removes false positives, and only then spends effort on contacts and copy.

## When to use

- A team has an offer and wants to know which accounts show the problem it solves.
- A market event has happened, and the team wants to act on it quickly.
- An outbound list exists but has no evidence behind each row.

Route elsewhere when:

- The question is which play to run from a ready list. Use `signal-outbound-plays`.
- The question is how to detect signals in the first place. Use `signal-detection-and-timing`.
- The question is the wording of a single cold email. Use `outbound-cold-email`.

## Inputs

- The offer, and the operational problem it solves.
- Candidate signals for the target accounts, with the evidence for each.
- Any existing outbound list, and whether each row has evidence behind it.
- Access to the evidence for each account, so another person can inspect it.

## Procedure

### Stage one: prove the signal

1. **Translate the offer** into the operational problem it solves.
2. **Generate several candidate signals.** Score each on six questions:
   - Specificity: does it point to this problem, or only describe the company?
   - Observability: can another person inspect the evidence for each account?
   - Timing: does it explain why action makes sense now?
   - Ownership: is there a recognizable buyer who owns the implied problem?
   - Offer fit: does the offer resolve the situation without a logical leap?
   - Noise: which common cases would produce a false positive?
3. **Choose one primary signal and one backup.** Funding, generic hiring, technology use and broad growth become useful only when combined with current evidence of the relevant workflow, constraint or complexity.
4. **Define the false positives** before building the cohort.

### Stage two: build the evidence layer

5. **Create an evidence record for each candidate account:** normalized company name and domain, the source and the exact excerpt, the observation date or a verified current status, the operational implication, the likely owner of the pain, a false-positive note, and a decision of keep, investigate or remove.
6. **Apply the sentence test.** Keep an account only if this sentence can be completed: "This company belongs because the evidence shows ___, which likely creates ___ for ___."
7. **Replace weak rows** rather than padding the cohort to reach a volume target.

### Stage three: map buyers and enrich

8. **Map buyers only for kept accounts.** Identify the role that owns the affected process, the role that feels the consequence, and any likely blocker. A job title is a clue to ownership, not proof of it.
9. **Map one to three contacts per account.** Deduplicate against existing relationships, and record why each person belongs.
10. **Enrich contact details only after the account and persona gates pass.** Keep strong accounts with missing contact data in a separate research queue. Do not weaken the cohort to fill it.

### Stage four: write and gate

11. **Write the thesis in one sentence:** "Companies showing [observable situation] are likely dealing with [operational consequence]; [offer] helps them reach [credible outcome]."
12. **Draft one core message per persona,** one proof point that matches the account's scale, and one low-friction ask. Adapt the thesis to each channel. Do not copy one message everywhere.
13. **React to the business situation.** Turn the evidence into a short, human context line. Do not quote scraped facts back to the reader, and do not announce that the company was watched.
14. **Run the quality gate** before launch: the thesis and its false-positive definition, the kept cohort with evidence, the buyer map and its reasons, the drafts with required variables, and a small learning cohort.

## Output

- The signal thesis and its false-positive definition.
- The kept account cohort, each row with its evidence and decision.
- The buyer map, with the reason for each contact.
- The staged drafts, with their variables.
- A QA report and the reply-learning goal for the first cohort.

## Quality bar

Every account has source evidence and a reason for inclusion. False positives are defined before the cohort is built. Fit, signal strength and contactability are scored separately. Enrichment happens after the account gate. Outreach is staged for human approval. Watch for an enrichment run before the cohort is proven, personalization from a single keyword, and a launch set by a lead-count target.

---
name: champion-job-change-tracking
version: 1.0.0
description: "Use to track when past buyers, power users, or key contacts at customers or prospects change jobs. Confirms each move against hard identifiers (domain, profile page), follows the mover into the new company, flags any vacated seat at the old account, and proposes CRM changes for approval. Not for general contact cleanup or for finding new prospects by persona."
---

# Champion job change tracking

Watches the people who already know the product, follows them when they move, and flags the seat they leave.

## Purpose

A champion who moves is warm pipeline: someone who already bought or used the product, now inside a new account, often with a window in which tooling decisions are open. Each move creates two actions. **Follow** the mover to the new company. **Backfill** the vacated seat at the old account, which is also a relationship risk.

## When to use

- Past buyers, power users or deal contacts have changed employer, and the team needs to follow them and backfill the seat they left.
- A champion list needs a regular check against current employers.

Route elsewhere when:
- The question is which signals to detect for outreach in general. Use `signal-detection-and-timing`.
- The question is hiring patterns at target accounts. Use `hiring-signal-tracking`.

## Principles

- **Compare on domains, never on company names.** Names vary ("Acme Ltd" vs "Acme"). Domains do not.
- **A move needs evidence.** Quote the old and new employer with dates. Never infer a move from a name mismatch. Acquisitions and rebrands create mismatches constantly.
- **Unverified is not unchanged.** If the lookup fails, or returns a status of success with no employer, the record is "could not verify". It is not "no change" and not "moved".
- **Confirm the person.** Check the name on any profile against the contact. A mismatch means the URL is wrong, so stop and re-find it.
- **Propose, then confirm.** Every CRM change goes into a single review table. Nothing is written without approval. Nothing is sent without approval.
- **Never drop a contact silently.** Every row ends as current, moved, out-of-ICP, or could-not-verify.

## Inputs

- Champion list, from a CRM export, an existing table, or a saved segment. Minimum: name, company domain, and profile URL, or an email to resolve one.
- Definition of a champion: past buyer, power user, or deal contact on a closed-won account. Do not widen the list without saying so.
- ICP filter for the follow play: industry, size, region.
- Cadence: weekly by default, monthly for lists under about 200.
- Destination for the digest, and CRM write permission (on or off).

## Procedure

### 1. Confirm the setup

Check that the data and enrichment tools work, and confirm the workspace with the user before touching anything. Tell the user the cost before the first full run.

### 2. Resolve the current employer

In this order, using the first method that gives an answer:
1. profile URL on file: pull the profile.
2. No URL: search by name and last known company, then validate the match.
3. Email lookup last, since coverage is weakest.

Validate the returned name against the contact. On mismatch, mark "could not verify" and stop.

### 3. Compare, deterministically

- Normalise both domains and compare them. Do not compare company names.
- Find the current role. Use its start date for ranking.
- Assign one verdict: **current**, **moved**, or **could not verify**.
- For "moved", record the evidence and dates.

Use a rule-based comparison for this step, not a language model. Rules are reproducible and do not wander into web search.

### 4. Route the verdict

- **Current:** record it, and refresh title or tenure if they changed. Done.
- **Could not verify:** record it, and propose re-finding the URL or flagging for review. Done.
- **Moved:** continue to both plays.

For an ambiguous move (acquisition or rebrand suspected), flag it for human review instead of deciding.

### 5. Follow play (the mover's new company)

1. Check whether the new company is already in the CRM, using the same domain rule.
   - In the CRM and a customer, a competitor, or otherwise disqualifying: flag, record the move, and stop outreach.
   - In the CRM and not disqualifying: update the contact to the new company and title.
2. Not in the CRM: enrich the company, check it against ICP and tier rules.
   - Fit: propose creating the account, then attach the contact.
   - Not fit: log "moved, out of ICP", and do not create the account. Still update the contact's company and title so the record is accurate.
3. For fit accounts, write a follow note anchored in the shared history: which product, at which account, roughly when. Suggest two or three buying-committee titles to find at the new account.

A note without shared history is generic outreach.

### 6. Backfill play (the seat left behind)

This runs for every real move, whether or not the new company is in ICP.

1. Find people at the old account who match the vacated title or persona.
2. Pick the likeliest successor and say why.
3. Flag the account as "seat vacated" so the account owner can protect the relationship.

### 7. Propose and approve

Present one table, covering every contact:
contact, old company, new company, verdict, evidence with dates, fields to change, follow note, backfill suggestion, and confidence.

Apply only what a human approves. If CRM writes are off, export the table instead.

### 8. Digest

Each run ends with a summary: champions checked, moves found, follow notes drafted, seats flagged, and rows needing review.

## Output

- A digest table with one row per champion:
  champion, old account, verdict, evidence, new company, new title, ICP fit, follow note draft, suggested committee titles, backfill successor, seat-vacated flag.
- A summary line: checked, moved, follow notes, flagged seats, rows needing review.
- A CRM change proposal, awaiting approval.

## Quality bar

- Every "moved" verdict cites dated evidence.
- No company match is made on a name alone.
- Name validation has run on every profile used.
- Every champion appears in the digest with a verdict.
- The follow note refers to shared history.
- No CRM write or outreach has happened without approval.
- No account has been duplicated under a different name or domain.

## Boundaries

- Champions and contacts already in the CRM only. For finding new people by persona, use the list-building skill.
- Not a general CRM cleanup or whole-list email re-verification.
- The digest ends at play-ready. The skill never sends outreach.

---
name: hiring-signal-tracking
version: 1.0.0
status: draft-for-review
description: Use to watch job postings as buying signals across target accounts, and to verify any hiring claim before it is used as fact in a score, alert, message, or account note. Detects and classifies hiring patterns, and blocks hiring claims that cannot be confirmed at the company's own source. Detection and classification only, never outreach. Not for outreach (see signal-outbound-plays) or champion job changes (see champion-job-change-tracking).
sources:
  - "Hiring radar (MIT, Dusan Vystrcil), pattern threshold, dedup ledger, 14-day window, zero-result failure check"
  - "Hiring signal verification (MIT, Peter Borkovich), verification at the company's own source, misattribution guard"
  - "Hiring signal prospecting (MIT, Thomas Maitre), hiring as a buying signal"
  - "Signal interpreter (MIT, Din Arbel), why-now discipline applied to hiring signals"
---

# Hiring signal tracking

Watches job postings for buying patterns, and verifies every hiring claim at the company's own source before it is used.

## Purpose

Hiring shows where budget and attention are going. A team being built now is a tooling decision being made this quarter. But research tools often attribute another company's job postings to the target, so a hiring claim is not usable until it is confirmed. Both halves belong in one skill.

## Principles

- **Verify before use.** A hiring claim counts only when confirmed from the target company's own source. Web research summaries are not enough.
- **A pattern is a cluster, not a single post.** One posting is weak. Three or more fresh roles in the same team is a real pattern.
- **Recency matters.** Only the last 14 days' postings are news. Older hiring is context.
- **Dead postings die early.** Evergreen, reposted, and agency listings are removed before they reach an alert.
- **Silence is not the same as no hiring.** Zero results across all watched accounts on several consecutive runs means the source has failed until proven otherwise.

## Inputs

- Watchlist of target accounts with canonical domains (tier-A accounts scanned daily, others weekly).
- Tracked queries: role titles, technologies named in job descriptions, and competitor product names.
- The GTM patterns to watch, defined in advance.
- Your own company's domain, to exclude your own postings.

## Procedure

### 1. Pull postings from two scans, kept separate

- **Watchlist scan:** postings by watched accounts, filtered by company.
- **Mention scan:** postings at any company matching a tracked query. A job description that mentions a watched company is not that company's hiring. Drop your own postings.

Use only sources you have tested. Use the platform's native integration where one exists. For other boards, use one tested scraper per board, and check its output before relying on it.

### 2. Keep only patterns that matter to the GTM motion

| Pattern | What it indicates |
|---|---|
| Hiring spree: three or more fresh roles in the same team | Tooling decisions are being made now |
| Buyer-persona hire: a first or head-of role for the persona you sell to | A new owner with a 90-day agenda |
| Build-versus-buy: a job description describes building what you sell | Funded, not yet staffed, still open |
| Executive hire in the buying committee | The first quarter in role shapes what stays |
| Competitor tool required in a job description | Displacement intelligence |
| Your product required in a job description | A customer signal for the account owner |

Single postings, category-only keyword matches, evergreen postings, and reposts are dropped. A pattern is real only when the posted dates support it.

### 3. Resolve and gate

- For postings placed by recruiting agencies, identify the real employer or drop the posting.
- For mention-scan hits, apply the ICP gate. A non-ICP company is logged, not alerted.

### 4. Deduplicate

- Check the account record for the last hiring signal and its pattern. The same pattern within 30 days does not re-alert. New postings attach to it as evidence.
- For an account with an active deal, do not alert as new. Flag it as a warm signal for the deal owner.
- Record a ledger note for every account processed or skipped, with the reason.

### 5. Verify before any hiring claim is used as fact

A hiring claim can enter a score, an ICP or tier assessment, an alert, a message, or an account note only when it passes all of these:

1. It is confirmed at the target company's own careers page, or on a job listing whose company name **and** domain both match the target.
2. It was not taken only from a research summary. Research prose is unverified until confirmed at source.
3. The citations behind it do not point mainly to a different company's domain. If they do, discard every fact derived from that research, not only the hiring lines.

If a claim fails, drop it. Do not soften it ("they may be hiring"). A wrong hiring claim is worse than none, because the prospect knows their own company.

### 6. Read and log

- Read the job descriptions that survive. Note named tools, team-size hints, reporting line, and pain language.
- Log the signal to the account record: pattern, roles, posted dates, links, and the scan it came from.
- Send one alert per pattern, with dated links, the account, who likely owns the consequence, and one line on what it means. Any pattern older than 14 days from its posted dates is context only.

### 7. Digest

Each run ends with a summary: postings pulled, patterns classified, alerts sent, and items skipped with reasons. Zero postings across all watched accounts on three consecutive runs is a source failure until verified, never a market signal.

### 8. Review after several weeks

After three to six weeks, read the ledger and digests: signals per week, share acted on within the 14-day window, and share at accounts with no owner. Drop patterns and queries nobody acts on. If alerts exceed rep capacity, add a draft-for-review step. The radar itself never sends.

## Output

- Per run: a digest and a ledger, with each signal's pattern, roles, posted dates, verification status, and links.
- Per signal: an alert with the account, pattern, evidence, owner, and one line of meaning.
- Per claim: a verification record showing the source checked and the result, or the reason for rejection.

## Quality bar

- Every hiring claim that reaches a score or message has a source on the target's own domain, or a name-and-domain-matched listing.
- No alert covers a posting older than 14 days.
- No agency posting is attributed to the client company.
- No single posting is reported as a pattern.
- Mention-scan hits never appear as a watched account's own hiring.
- Quiet runs are reported as quiet only after the source has been checked.

## Boundaries

- Detection and classification only. This skill never drafts, queues, or sends outreach.
- Champion and contact moves belong to `champion-job-change-tracking`.
- General signal interpretation and timing belong to `signal-detection-and-timing`.

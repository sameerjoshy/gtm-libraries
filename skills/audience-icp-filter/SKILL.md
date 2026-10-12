---
name: audience-icp-filter
version: 1.0.0
status: draft-for-review
description: Use when a list of people already exists (event or webinar attendees, registrants, a CRM export, a prospecting export, a community list) and someone needs to know who on it fits the ICP before anyone is contacted. Produces every lead in one of four buckets (match, review, no match, excluded) with a reason for each, removes the client's own colleagues and competitors, and reconciles every count to the input. Not for building a list from scratch or for scoring accounts.
sources:
  - "Audience ICP filter (MIT, Erwann Lefevre), coverage gate before ICP questions, deterministic pass then semantic queue review, four buckets with reconciliation, exclusion doctrine across identity fields, seniority and function taxonomy, multilingual titles, case-sensitive patterns, adjudication with reasons"
  - "ICP (MIT, Ido Goldberg / Swan), the rule that no team member hand-sorts a list and that a large review bucket is a diagnosis, not a deliverable"
---

# Audience ICP filter

Sorts an existing list against the ICP so that nobody is contacted by mistake, the right people are kept, and every decision can be audited.

## Purpose

Turn a messy list into four labelled buckets, with a reason on every lead and counts that add back to the input. The output is safe to act on: colleagues and competitors are out, real buyers are in, and the small set of genuinely unclear leads is short enough for a person to decide in minutes.

## When to use

- An existing lead list must be sorted against the ICP into labelled buckets, with a reason for every lead.
- A team needs to exclude colleagues and competitors safely before outreach.

Route elsewhere when:
- The ICP is not yet defined. Use `icp-builder`.
- The list is being built from scratch. Use `prospect-list-building`.

## Principles

- **Measure before asking.** Check what the list actually contains before proposing ICP criteria. A geography filter on a list with empty location fields filters nothing. It just sends everyone to review and calls that a result.
- **Exclusion is not quality.** Exclusion answers "must we never contact this person". Out of ICP answers "is this person a good lead". They go to different buckets, because an auditor needs to tell "we chose not to" from "we must not".
- **Two passes, neither optional.** Pass 1 is deterministic and reproducible. Pass 2 reads meaning, but only for the queue that pass 1 produces. Nobody hand-sorts a list.
- **Nothing dropped on an inference without a second look.** A wrong drop is invisible by construction. Any lead removed because of a function or seniority read from free text goes to the queue first.
- **A large review bucket is a diagnosis.** It usually means the list was never enriched or the ICP is under-specified. Name the cause and fix it upstream.
- **Honest criteria over decorative ones.** Three criteria the data supports beat six it cannot.

## Inputs

1. The lead list: one row per person, with whatever fields the source provides. Required: a unique id, or a first and last name.
2. The client's own company name and email domain, plus known competitors and any other exclusions.
3. ICP answers (Step 3): seniority, functions, founder rule, geography and industry if the data supports them, and any outright exclusions.
4. Optional: enrichment budget and approval.

## Procedure

### Step 1: Coverage gate (always first)

Measure the fill rate of each field across the list:

| Field | Needed for | If below threshold |
|---|---|---|
| Job title | Seniority and function | Classification degrades; most leads land in review |
| Company name | Company-based exclusion | Exclusion is unreliable |
| Bio or headline | Catching people whose company and email are both empty | Own-team and competitor exclusion will leak |
| Work email | Domain-based exclusion | Job-changers slip through |
| Location | Geography criteria | Geography cannot be applied |
| Industry | Industry criteria | Industry cannot be applied |

The bio row is the one people skip. It is the only field that catches a colleague whose company is blank and whose email is missing. That is exactly the profile of a lead imported from a social export.

Record which criteria the data cannot support. Say so before the ICP conversation starts. Do not offer criteria that the coverage cannot back.

### Step 2: Enrichment (only with approval)

If the gate shows gaps, quote the cost of enriching the affected rows and wait for an explicit yes. Quote the number of rows actually missing a needed field, not the size of the whole list. On a mostly complete list those numbers differ widely, and quoting the total overstates the cost.

Enrichment aimed at finding email addresses serves deliverability, not filtering. If someone asks for it here, say so and let them decide.

If enrichment is declined, proceed. Name each criterion dropped and state that exclusion is now best-effort.

### Step 3: ICP questions (only for supported criteria)

| # | Question | Feeds |
|---|---|---|
| 1 | Which seniority levels qualify: founder or C-level, VP or head of, manager or lead, individual contributor? | Seniority |
| 2 | Which functions: sales, growth or marketing, RevOps or GTM, partnerships, product or tech? | Functions |
| 3 | Do founders qualify regardless of stated function? | Founder rule |
| 4 | Any geography or industry constraint? Ask only if coverage supports it. | Locations, industries |
| 5 | Who is excluded outright: own company, competitors, agencies? | Exclusions |

Question 3 matters more than it looks. Most founder titles state no function, such as "Co-Founder" or "Founder at Stealth". If founders do not qualify automatically, every one of them lands in review. On a real list of about 150 leads, this one answer moved about fifteen leads. Ask it explicitly and explain the trade-off.

If the answer is vague ("good leads", "decision makers"), ask once for specifics. A vague ICP produces a large review bucket, which is the problem this skill removes.

### Step 4: Build the spec

Write one spec object: the ICP criteria, the exclusions, and the leads. Include locations and industries only where coverage supports them.

Two spec traps:
- **Geography matches on substring.** Enrichment often writes regional labels such as "Greater Paris Metropolitan Region" that do not contain the country name. Before writing the spec, read the actual location values and list the metros and regions that appear.
- **Industry expands through synonyms.** Pass a canonical bucket such as `saas` or `fintech`, and expand it to the platform labels that mean the same thing. Real software companies are routinely labelled "Technology, Information and Internet" and would otherwise be dropped. For buckets outside the synonym map, list the variants, or let the queue surface the misses.

### Step 5: Pass 1, deterministic classification

Run the classification in code, not by reading the list. The code must:
- Assign seniority by first match, evaluated top-down, so that "Chief Executive Officer" resolves as founder or C-level rather than matching a lower tier.
- Collect every function that matches, because cross-functional titles such as "Head of Growth and Partnerships" carry several.
- Fall back to the bio only when the title has no seniority or no function signal. Flag every bio-inferred match.
- Apply exclusions across the whole identity surface: company name, work email, personal email, bio, and company URL. A hit on either the company or the email excludes, because job-changers have stale fields.
- Compare names with punctuation and spacing stripped, so that "@AcmeLabs" matches "Acme Labs". Apply the squashed comparison only to terms of about five characters or longer. Shorter terms stay word-bounded, or they collide with ordinary words.
- Treat junk company values as no company: "Nothing", "-", "N/A", "Freelance", "Self-employed".
- Flag agency, freelance, and consultant signals into the queue. Do not exclude them automatically, because a consultant can be a real buyer.
- Route noise titles (student, intern, open to work, retired, investor) to no match, not review.
- Refuse to output if the input is invalid or if the bucket counts do not reconcile. Never produce a best-effort result.

Pattern rules for any taxonomy:
- Write patterns in lowercase unless the capitals carry meaning. Short acronyms need case-sensitive patterns, because otherwise "IT" matches the English pronoun "it".
- Include the languages the list is actually in. A list from a European market is often half non-English. A title the taxonomy misses goes to review, which is the safe failure.

Seniority tiers, first match wins:
- Founder or C-level: founder, co-founder, CEO, CTO, CMO, CRO, COO, CFO, "Chief ... Officer", president, owner, managing director.
- VP or head: VP, SVP, EVP, head of, director, general manager, country manager.
- Manager or lead: manager, lead, supervisor, principal.
- Individual contributor: account executive, SDR, BDR, specialist, coordinator, analyst, engineer, intern, junior.

Ordering is load-bearing. A flat set of patterns would classify "VP of Engineering" and "Engineer" the same way.

Buckets:
- **match:** seniority and function both in ICP, constraints satisfied.
- **review:** the engine declined to guess. Title unclear, function missing, or location or industry data absent.
- **no match:** out of ICP, or a noise title.
- **excluded:** own team, competitor, or a listed exclusion.

Every lead lands in exactly one bucket with a reason, and the counts reconcile to the input.

### Step 6: Pass 2, semantic review of the queue

Pass 1 returns a queue of the leads worth reading. Read only those. On a clean, on-target list the queue is roughly fifteen to twenty-five leads.

Queue flags and what to check:

| Flag | Meaning | Check |
|---|---|---|
| Ambiguous | Entire review bucket | Resolve to match or no match where the record supports it |
| Bio-inferred match | Matched from the bio, not the title | Does the bio really indicate an in-ICP function? |
| Agency or freelance | Company or bio reads like a service provider | Keep if a real buyer; drop if a service provider |
| Dropped on geo or industry | Right seniority and function, failed location or industry | Rescue if the label is a variant of an in-ICP value |
| Bio-inferred drop | Left the ICP on a seniority or function read from the bio | Confirm the bio really means that before discarding |

False positives live in match as well as review, which is why the queue includes some risky matches.

What pattern matching cannot judge, and what to do:
- "Chief Happiness Officer" and "Chief Medical Officer" match C-level but are not buyers. Remove them in pass 2. Do not narrow the pattern to avoid these, because narrowing would lose real buyers.
- A competitor not on the exclusion list. Exclude it and say which one was added and why.
- Bare functional titles such as "CMO at Acme" are unambiguously C-level but carry no function token. Read them as their function: CMO as marketing, CRO as sales, CTO as product and tech.
- "Founder at Stealth Mode" is almost always in ICP. Resolve it.

Two specific rules:
- **Competitor names in bios are not employers.** People list the tools they use. Before excluding on a competitor signal, confirm it appears as the employer or in the email domain.
- **Consultants can be buyers.** Keep or drop agency and freelance matches by reading the record, not by pattern.

### Step 7: Adjudicate with reasons

Submit each override with a substantive reason. The adjudication step must reject an override on a lead that does not exist, an invalid bucket, a duplicate, or a reclassification with no reason. Re-run the reconciliation after adjudication.

Resolve as many queued leads as the record honestly supports. Leave only the genuinely ambiguous ones for a human decision. Do not hand back the full review bucket as the deliverable.

If the queue is large (sixty or more), diagnose before working it:
1. The list was never enriched. Check coverage.
2. The ICP is under-specified. Most often the founder question was not answered, so function-less founders sit in review.

Fix the cause in the spec and re-run pass 1. That takes seconds. Hand-reviewing sixty leads does not.

### Step 8: Report

Report the four bucket counts, which must sum to the input count. Then:
- Criteria dropped for lack of coverage, and whether exclusion is best-effort.
- Each exclusion added in pass 2, with its reason.
- Pass 2 changes in aggregate: how many moved and why. For example: "moved 3: two rescued on an industry-label variant, one competitor excluded."
- Remaining review leads for a human, with what decision each needs.
- Any spec traps found (such as a location label that needed listing).

## Output

1. **Summary:** bucket counts, which sum to the input total. Coverage gaps. Criteria dropped.
2. **Match list:** each lead with its reason.
3. **Excluded list:** each lead with the exclusion that fired.
4. **No match list:** each lead with its reason, grouped by cause.
5. **Review list:** only the leads still unresolved after pass 2, each with the decision needed.
6. **Audit trail:** the spec used, the pass 2 overrides with reasons, and the reconciliation check.

Keep lead data in the client's workspace. Do not commit lead data to the library.

## Quality bar

- Coverage was measured before any ICP criterion was applied.
- Every lead is in exactly one bucket, with a reason, and the totals equal the input count.
- The client's own company name and domain are in the exclusion list.
- Every bio-inferred or founder-rule decision is in the queue or explained.
- No lead was dropped on a function or seniority inference without passing the queue.
- Every pass 2 override has a reason.
- Competitor exclusions were confirmed as employer or email domain, not bio text.
- The review list is short enough to decide in minutes.

## Rules

- MUST measure field coverage before proposing ICP criteria, and drop criteria the data cannot support.
- MUST get explicit approval, with a quoted cost for the rows affected, before enrichment.
- MUST run the deterministic pass in code, not by hand.
- MUST apply exclusions across company, both emails, bio, and company URL.
- MUST seed exclusions with the client's own company and domain.
- MUST reconcile every count to the input. Refuse rather than output a result that does not reconcile.
- MUST queue any lead dropped on a free-text inference before discarding it.
- MUST give a reason for every bucket decision and every override.
- MUST keep "not a buyer" (no match) separate from "must not contact" (excluded).
- NEVER exclude someone on a competitor name found only in their bio.
- NEVER drop an ambiguous lead to make the output tidy. Route it to review.
- NEVER hand back the full review bucket as the deliverable.
- NEVER treat junk company values as employers.
- NEVER commit lead or personal data to the repo.

## Boundaries

- Filters an existing list. Does not build lists from scratch: use the list-building skill when it is added.
- Defines the ICP criteria. Does not write them: use `icp-builder`.
- Tiers accounts for attention: use `account-tier-scoring`.
- Does not find email addresses or enrich for deliverability. That is a separate tool and budget decision.
- Does not write outreach or sequences.
- The method requires a deterministic classification script with the same reconciliation and refusal behaviour. The reference implementation is not in this library. Build or install one per client before running Step 5.

---
name: audience-icp-filter
version: 1.2.0
description: "Use when a list of people already exists (event or webinar attendees, registrants, a CRM export, a prospecting export, a community list) and someone needs to know who on it fits the ICP before anyone is contacted. Produces every lead in one of four buckets (match, review, no match, excluded) with a reason for each, removes the client's own colleagues and competitors, and reconciles every count to the input. Not for building a list from scratch (see `prospect-list-building`) or for scoring accounts (see `account-tier-scoring`)."
---

# Audience ICP filter

## Purpose

Sort an existing list against the ICP so that nobody is contacted by mistake, the right people are kept, and every decision can be audited. Turn a messy list into four labeled buckets, with a reason on every lead and counts that add back to the input. The output is safe to act on: colleagues and competitors are out, real buyers are in, and the small set of genuinely unclear leads is short enough for a person to decide in minutes.

## When to use

- An existing lead list must be sorted against the ICP into labeled buckets, with a reason for every lead.
- A team needs to exclude colleagues and competitors safely before outreach.

Route elsewhere when:
- The ICP is not yet defined. Use `icp-builder`.
- The list is being built from scratch. Use `prospect-list-building`.
- Accounts need tiering for attention. Use `account-tier-scoring`.
- The question is the outreach message or sequence. Use `personalized-first-touch` or `outbound-cold-email`.

## Inputs

1. The lead list: one row per person, with whatever fields the source provides. Required: a unique id, or a first and last name.
2. The client's own company name and email domain, plus known competitors and any other exclusions.
3. ICP answers (Step 3): seniority, functions, founder rule, geography and industry if the data supports them, and any outright exclusions.
4. Optional: enrichment budget and approval.
5. A deterministic classification script with the reconciliation and refusal behavior in Step 5. The reference implementation is not in this library; build or install one per client before running Step 5.

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

The bio row is the one people skip: it is the only field that catches a colleague whose company is blank and whose email is missing, the profile of a social-export import. Record the criteria the data cannot support, and say so before the ICP conversation starts.

### Step 2: Enrichment (only with approval)

If the gate shows gaps, quote the cost of enriching the affected rows and wait for an explicit yes. Quote the rows actually missing a needed field, not the whole list, because the two differ widely on a mostly complete list. Enrichment for email addresses serves deliverability, not filtering; say so and let the user decide. If enrichment is declined, proceed, name each criterion dropped, and mark exclusion as best-effort.

### Step 3: ICP questions (only for supported criteria)

| # | Question | Feeds |
|---|---|---|
| 1 | Which seniority levels qualify: founder or C-level, VP or head of, manager or lead, individual contributor? | Seniority |
| 2 | Which functions: sales, growth or marketing, RevOps or GTM, partnerships, product or tech? | Functions |
| 3 | Do founders qualify regardless of stated function? | Founder rule |
| 4 | Any geography or industry constraint? Ask only if coverage supports it. | Locations, industries |
| 5 | Who is excluded outright: own company, competitors, agencies? | Exclusions |

Question 3 matters most. Most founder titles state no function, such as "Co-Founder" or "Founder at Stealth", so if founders do not qualify automatically, all of them land in review. On a list of about 150 leads, this one answer moved about fifteen. Ask it explicitly. A vague answer ("good leads", "decision makers") produces the large review bucket this skill removes, so ask once for specifics.

### Step 4: Build the spec

Write one spec object: the ICP criteria, the exclusions, and the leads, including locations and industries only where coverage supports them. Two traps:

- **Geography matches on substring.** Enrichment writes regional labels such as "Greater Paris Metropolitan Region" with no country name. List the metros and regions that actually appear before writing the spec.
- **Industry expands through synonyms.** Pass a canonical bucket such as `saas` or `fintech` and expand it to the labels that mean the same thing. Software companies are often labeled "Technology, Information and Internet" and would otherwise be dropped. For buckets outside the synonym map, list the variants or let the queue surface the misses.

### Step 5: Pass 1, deterministic classification

Run the classification in code, not by reading the list. The code must:

- Assign seniority by first match, top-down, so "Chief Executive Officer" resolves as founder or C-level, not a lower tier.
- Collect every matching function; cross-functional titles such as "Head of Growth and Partnerships" carry several.
- Fall back to the bio only when the title has no seniority or function signal, and flag every bio-inferred match.
- Apply exclusions across company name, work email, personal email, bio, and company URL; a hit on either company or email excludes, because job-changers have stale fields.
- Compare names with punctuation and spacing stripped, so "@AcmeLabs" matches "Acme Labs". Keep the squashed comparison to terms of five characters or longer; shorter terms stay word-bounded or collide with ordinary words.
- Treat junk company values as no company: "Nothing", "-", "N/A", "Freelance", "Self-employed".
- Queue agency, freelance, and consultant signals rather than excluding them; a consultant can be a real buyer.
- Send noise titles (student, intern, open to work, retired, investor) to no match, not review.
- Refuse to output if the input is invalid or the bucket counts do not reconcile. Never produce a best-effort result.

Pattern rules:

- Write patterns in lowercase unless capitals carry meaning. Short acronyms need case-sensitive patterns, or "IT" matches the English pronoun "it".
- Include the languages the list is actually in; a European list is often half non-English. A title the taxonomy misses goes to review, the safe failure.

Seniority tiers, first match wins:

- Founder or C-level: founder, co-founder, CEO, CTO, CMO, CRO, COO, CFO, "Chief ... Officer", president, owner, managing director.
- VP or head: VP, SVP, EVP, head of, director, general manager, country manager.
- Manager or lead: manager, lead, supervisor, principal.
- Individual contributor: account executive, SDR, BDR, specialist, coordinator, analyst, engineer, intern, junior.

Ordering is load-bearing: a flat pattern set would classify "VP of Engineering" and "Engineer" alike.

Buckets:

- **match:** seniority and function both in ICP, constraints satisfied.
- **review:** the engine declined to guess. Title unclear, function missing, or location or industry data absent.
- **no match:** out of ICP, or a noise title.
- **excluded:** own team, competitor, or a listed exclusion.

Every lead lands in exactly one bucket with a reason, and the counts reconcile to the input.

### Step 6: Pass 2, semantic review of the queue

Pass 1 returns a queue of the leads worth reading. Read only those. On a clean, on-target list the queue is roughly fifteen to twenty-five leads.

| Flag | Meaning | Check |
|---|---|---|
| Ambiguous | Entire review bucket | Resolve to match or no match where the record supports it |
| Bio-inferred match | Matched from the bio, not the title | Does the bio really indicate an in-ICP function? |
| Agency or freelance | Company or bio reads like a service provider | Keep if a real buyer; drop if a service provider |
| Dropped on geo or industry | Right seniority and function, failed location or industry | Rescue if the label is a variant of an in-ICP value |
| Bio-inferred drop | Left the ICP on a seniority or function read from the bio | Confirm the bio really means that before discarding |

False positives live in match as well as review, which is why the queue includes some risky matches. What pattern matching cannot judge:

- "Chief Happiness Officer" and "Chief Medical Officer" match C-level but are not buyers. Remove them in pass 2; do not narrow the pattern, which would lose real buyers.
- A competitor missing from the exclusion list. Exclude it and say which and why.
- Bare functional titles such as "CMO at Acme" are C-level with no function token. Read them as their function: CMO as marketing, CRO as sales, CTO as product and tech.
- "Founder at Stealth Mode" is almost always in ICP. Resolve it.

Confirm a competitor signal as the employer or email domain before excluding; bios list tools, not employers. Keep or drop agency and freelance matches by reading the record, not by pattern.

### Step 7: Adjudicate with reasons

Submit each override with a substantive reason. Reject an override on a lead that does not exist, an invalid bucket, a duplicate, or a reclassification with no reason, and re-run reconciliation after adjudication. Resolve as many queued leads as the record honestly supports; leave only the genuinely ambiguous ones for a human. Do not hand back the full review bucket as the deliverable.

If the queue is large (sixty or more), diagnose first: the list was never enriched (check coverage) or the ICP is under-specified (most often the founder question went unanswered, so function-less founders sit in review). Fix the cause in the spec and re-run pass 1. That takes seconds; hand-reviewing sixty leads does not.

### Step 8: Report

Report the four bucket counts, which must sum to the input count, then:

- Criteria dropped for lack of coverage, and whether exclusion is best-effort.
- Each exclusion added in pass 2, with its reason.
- Pass 2 changes in aggregate: how many moved and why, for example "moved 3: two rescued on an industry-label variant, one competitor excluded."
- Remaining review leads for a human, with the decision each needs.
- Any spec traps found, such as a location label that needed listing.

## Principles

- **Measure before asking.** Check what the list holds before proposing criteria; a geography filter on empty location fields filters nothing.
- **Exclusion is not quality.** Exclusion answers "must we never contact this person"; out of ICP answers "is this a good lead". Different buckets, because an auditor must tell "we chose not to" from "we must not".
- **Two passes, neither optional.** Pass 1 is deterministic; pass 2 reads meaning, but only for the queue pass 1 produces.
- **Nothing dropped on an inference without a second look.** A wrong drop is invisible, so any free-text function or seniority gate goes to the queue first.
- **A large review bucket is a diagnosis.** It usually means the list was never enriched or the ICP is under-specified. Name the cause and fix it upstream.
- **Honest criteria over decorative ones.** Three criteria the data supports beat six it cannot.

## Output

1. **Summary:** bucket counts, which sum to the input total, plus coverage gaps and criteria dropped.
2. **Match list:** each lead with its reason.
3. **Excluded list:** each lead with the exclusion that fired.
4. **No match list:** each lead with its reason, grouped by cause.
5. **Review list:** only the leads still unresolved after pass 2, each with the decision needed.
6. **Audit trail:** the spec used, the pass 2 overrides with reasons, and the reconciliation check.

Keep lead data in the client's workspace.

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

- MUST get explicit approval, with a quoted cost for the rows affected, before enrichment.
- MUST run the deterministic pass in code, not by hand.
- MUST reconcile every count to the input. Refuse rather than output a result that does not reconcile.
- MUST keep "not a buyer" (no match) separate from "must not contact" (excluded).
- NEVER treat this skill as an email finder or use it to enrich for deliverability; that is a separate tool and budget decision.
- NEVER write outreach or sequences from this skill.
- NEVER commit lead or personal data to the repo.

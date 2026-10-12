---
name: prospect-list-building
version: 1.0.0
status: draft-for-review
description: Use when building a prospect list of companies, contacts, or both, for outbound, ABM, or a signal-based motion. Sizes the audience before any full pull, writes the column plan and the ICP pass rule before running it, removes most rows with free checks before any paid enrichment, runs AI research one narrow question at a time, and only activates a list after the user approves its size and cost. Not for scoring existing accounts (see account-tier-scoring) or for verifying an existing list (see list-hygiene).
sources:
  - "Build list (MIT, Ido Goldberg / Swan), column ladder with cost tiers and run-when gates, lock the brief, size first, free elimination before enrichment, AI research as one question per column, pilot on ten rows, companies before people, email waterfall, activation with approval, anti-patterns"
  - "List architect (MIT, Alex Vacca / Frontal, contributor Ivan Falco), ICP scoring with a 100-point scale, sourcing and qualification sequence, Sales Navigator segmentation at the search result cap, decay and re-verification rules"
  - "List building tips and lead sources guide (MIT, Alex Vacca / Frontal): data-quality hierarchy, source selection by need, pre-campaign checklist, common mistakes. Efficiency timings, provider comparisons, and tool-specific templates are dropped as unverified or vendor-specific"
  - "Adapted for GTM-360: platform-specific tool names replaced with generic steps; tiering conflict between the two sources resolved by stating one default; provider coverage and decay figures labelled as heuristics to test"
---

# Prospect list building

## Purpose

A list is a table in which each column costs something and removes some rows. Build it so the cheap checks remove most of the rows before any paid step runs. Write the plan first, show it, and run it only after the user agrees to the size and the cost.

## When to use

- A new outbound list, ABM target list, or signal-triggered list is needed.
- A list must be rebuilt because its source or ICP changed.
- A user asks for "a list of companies like X" or "contacts at Y".

Route elsewhere when:

- The question is how to score accounts already on file. Use `account-tier-scoring`.
- The question is whether an existing list is clean. This is list hygiene, which is not yet merged into this library. Use the free elimination and dedupe steps above on the existing list in the meantime.
- The question is which accounts are worth a named ABM investment. Use `abm-strategy-planner`.

## Inputs

- The ICP segment, and the persona or personas to reach.
- Hard constraints (must have) and soft ones (nice to have), such as headcount band, geography, industry, and technology.
- The motion: cold outbound, ABM, signal-triggered, event follow-up, or competitor displacement.
- The target row count.
- The CRM, so that accounts already in an active sequence can be excluded.

If the brief contradicts the org's saved ICP, stop and ask. Do not silently build a list the ICP would reject. The user may be running a deliberate experiment, but that has to be stated.

If the brief is vague, such as "SaaS companies that might want this", ask for the sub-segment, the size band, and the signal. That is not yet a brief.

## Procedure

### Step 1: Lock the brief

Restate the brief in four parts before any tool call:

- **Who:** the ICP segment and the persona or personas.
- **What:** the hard and soft constraints.
- **Why:** the motion.
- **Size:** the target row count.

If the org has more than one ICP segment and the user has not chosen one, ask which.

### Step 2: Size the audience first

Before any full pull, run a sizing query with a single result and read the total count.

- Under 50 companies: report it. A thin niche usually needs broader filters or a different source, not more retries of the same query.
- Over 5,000 companies: the brief is too loose. Ask for a tighter filter before pulling anything.

Sizing first avoids discovering after twenty calls that the niche is empty.

### Step 3: Write the column plan and show it

Draft the table before sourcing. Each column has four properties:

1. **Input:** which earlier columns it reads.
2. **Cost tier:** free filter, free elimination, cheap enrichment, AI research, or paid contact data.
3. **Run-when condition:** the upstream Boolean that gates it. Almost always the ICP pass.
4. **Fallback:** what to write when the column cannot resolve.

Template. Drop the columns the motion does not need.

```
INPUT (free preview)
  domain, name, employee band, industry, geography, professional profile URL

FREE ELIMINATION (no cost, code or formula)
  dedupe by normalised domain
  hard re-filter on geography and size band
  exclude accounts already in an active sequence or open opportunity
  cheap name and domain sniff test: plausibly fits the brief?
  icp_pass = AND(all of the above)

CHEAP ENRICHMENT (only if icp_pass)
  precise headcount, city-level location, technology signals if the motion needs them
  icp_pass_strict = AND(icp_pass, enriched values confirm)

AI RESEARCH (only if icp_pass_strict)
  one column per narrow question, each returning yes, no, or unclear
  research_pass = AND(icp_pass_strict, required answers are yes)

TIER (no cost)
  A, B, C, or D from research_pass and signal strength
  drop D before any contact work

PEOPLE DISCOVERY (only if tier is A, B, or C)
  contacts matching the chosen personas, with a profile URL
  people_pass = persona match AND profile URL present

CONTACT ENRICHMENT (paid, only if tier is A or B and people_pass)
  verified email through a waterfall; phone only for A-tier where calls are part of the motion
```

Show the plan to the user and confirm the `icp_pass` definition before running anything. A short check now saves hours of misdirected enrichment.

### Step 4: Source companies before people

Build the company set first, then find people at those companies. Never start with a broad people search such as "VP Sales at SaaS companies". It produces people with no reliable company context.

Use the source enumerations exactly as the tool defines them. Check enum-like filter values such as industry, location, and size band against the tool's own options before a search. Guessed values return zero results or silent errors.

On sources: more than one source gives better coverage, but not in a linear way. One heuristic from the source puts one source at about 60% of the addressable market, two at about 85%, and three at about 92%. Treat these numbers as a hypothesis to test in your own market. The same provider with different filters is one source, not two.

Choose the source type by what the list needs most. Record the type in the plan, not the tool name, since tools change.

| Need | Primary source type | Backup |
|---|---|---|
| Volume | Broad contact database | Native search in the enrichment tool |
| Precision on role and seniority | Professional network search | Verified contact database |
| Lookalikes of best customers | Firmographic lookalike tool | Enrichment with tech-stack filters |
| Local or SMB | Local business directory | Broad database with a location filter |
| Niche vertical | Industry directory or association list | Broad database with keyword filters |

### Step 5: Run the free elimination pass

Before any paid step, in code or formulas:

1. **Dedupe** by normalised domain: strip the `www.` prefix and lowercase.
2. **Re-apply hard thresholds.** A preview band such as "11 to 50" does not prove "more than 20". Re-apply the threshold, or send the row to enrichment to confirm it.
3. **Check geography precision.** A state match is not a city match. If the brief asks for a city, flag state-level rows for enrichment instead of passing them.
4. **Cross-check the CRM.** Drop anything in an active sequence or a recent open opportunity. Duplicate touches damage deliverability.
5. **Run a sniff test.** One short pass over names and domains: does this row plausibly fit the brief? It removes obvious noise cheaply.

This step typically removes a large share of the pool, often 60 to 80% in the source's experience. That is the largest saving in the process. Skipping it and enriching the full pool is the most expensive mistake.

### Step 6: Run AI research one question at a time

Each AI research column answers one narrow question about one row. Do not combine "is this direct-to-consumer and in this city and sells this product" into one prompt. That is three columns.

Prompt pattern:

```
Visit {domain}.
Answer one question: {specific question}.
Look at: {specific pages, such as the homepage, about page, or product pages}.
Return one of: yes, no, unclear.
If the site is unreachable or you cannot tell, return unclear.
Do not guess, and do not infer from general language.
```

Rules:

- Run research only on rows that passed `icp_pass`. Never run it on the full pool.
- Pilot on ten rows first. If 80% or more come back unclear, the question is wrong. Rewrite it before scaling.
- Use the cheapest model that can answer. Save the stronger model for judgment calls such as ICP fit.
- Always write a fallback value, so an unreachable site does not break the column.

### Step 7: Tier and pick contacts

Tiering, using the library default, a 100-point ICP score: A at 90 to 100, B at 70 to 89, C at 50 to 69, and D under 50. Score each account on the fit criteria agreed for the client, then tier on the score. The pass-and-signal scheme below is the alternative, for use only if the client chooses it:

- **A:** passes the ICP and has an active signal, such as funding, hiring, intent, or news.
- **B:** passes the ICP, with no active signal.
- **C:** partial fit, worth nurturing.
- **D:** fails the ICP. Drop it.

Do not mix the point score with the pass-and-signal rule in the same list. Pick one per client (see DECISIONS.md).

Contacts per company, by motion:

- Cold outbound, single thread: one contact per company.
- ABM or multi-thread: three to five, spanning the buying committee. See `multi-threading-coach`.

### Step 8: Enrich emails on the slice that matters

Only for A and B-tier contacts. Use a waterfall: the cheapest provider first, then the next provider on a miss, then merge the results, then verify.

- Verify after merging, not during.
- Drop `invalid` results. Treat catch-all results as risky, and ship them only if the user accepts the deliverability cost.
- Drop role-based addresses such as `info@`, `support@`, `hello@`, `admin@`, and `contact@` before any activation.
- Use batches for more than about 20 rows.

Phone enrichment only for A-tier, and only if the motion includes calls.

### Step 9: Dedupe, show cost, then activate

- Dedupe companies by normalised domain.
- Dedupe people by verified email, falling back to the profile URL.
- Cross-check the CRM again, to remove contacts already in active sequences.
- Show the user the list size, the tier breakdown, the completeness of each column, and the estimated cost. Wait for explicit approval.
- After approval, save the list, tagged with the segment and the source.
- Route by tier: A to priority outreach, B to standard nurture, C to low-touch content.

The task is not complete until the list is saved or the user explicitly drops it. Do not end on "shall I go ahead?" with no list created.

## Data quality and the pre-campaign checklist

Rank each contact by the strongest data it has:

1. Verified email.
2. Direct phone number, where calls are part of the motion.
3. Recent activity signal.
4. ICP fit confirmed by research, not inferred from title.
5. Company enrichment complete.

Before any campaign launches, check:

- [ ] Bounce rate on the sent or sampled segment is under 2% (default).
- [ ] Email coverage is at least 70% of the list (default). Below that, the problem is the source, not the outreach.
- [ ] ICP criteria are verified on the rows that will be sent.
- [ ] Recent signals are tagged where the motion uses them.
- [ ] Duplicates are removed.
- [ ] Competitor customers are flagged and excluded.
- [ ] The do-not-contact list is checked.

Both thresholds are defaults to calibrate per client.

## Reference figures

These are working numbers from the sources. Verify each one for the client's market before relying on it.

- Sales Navigator returns at most about 2,500 results per search. Segment the search to get more.
- Email addresses decay at roughly 22 to 30% a year. Re-verify any list older than about 30 days before use.
- A bounce rate under 1% is the usual target for a campaign. Deliverability above 95% is the usual target for the sending domain.

## Output

For each list build:

- The brief, restated in the four parts.
- The sizing result.
- The column plan, as approved.
- The counts after each stage: pool, after free elimination, after enrichment, after research, after tiering, after contact discovery, after verification.
- The tier breakdown and the cost estimate.
- The saved list, or the reason it was not saved.

## Universal rules

1. No paid column runs without `icp_pass = true`.
2. Size before sourcing.
3. Companies before people.
4. Check enum values against the tool's options before any search.
5. Cheap filters run before any credit is spent.
6. One question per AI research column.
7. Pilot ten rows before scaling any new column or provider.
8. Show the column plan, the size, and the cost before activating.
9. Push back on briefs that contradict the saved ICP.

## Anti-patterns

- Running several searches with different filters and calling it multi-source.
- Guessing enum values and getting silent empty results.
- Treating a preview band as proof of a hard threshold.
- Passing a state-level match when the brief asked for a city.
- Enriching the full pool before free elimination.
- Putting several questions into one research prompt.
- Ending the task on a question with no list saved.
- Quietly building a list that contradicts the ICP.
- Relying on one source for all coverage.
- Over-filtering, which shrinks the market before anyone has seen it, or under-filtering, which sends outreach to poor fits.
- Skipping verification before sending, which damages deliverability.

## Quality bar

The user sees the plan and the ICP rule before any sourcing. Free elimination removes most of the pool before any credit is spent. Each paid column has a run-when condition. AI research answers one question per column and has been piloted. The final summary shows size, tiers, completeness, and cost, and the user approves before activation.

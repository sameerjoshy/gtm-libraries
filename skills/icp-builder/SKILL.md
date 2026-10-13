---
name: icp-builder
version: 1.2.0
description: "Use when building, validating, refining, or adding to an ideal customer profile (ICP), including segments, personas, and the gate-based qualification rule that decides which accounts are in. Use when the ICP is too broad, too vague, or was written before revenue arrived, or when a new segment needs defining. Derives the profile from closed-won revenue where data exists, and produces a matrix that two people can apply the same way. Account tiering and list filtering have their own skills. Not for scoring a list already on file (see `audience-icp-filter`) or tiering accounts (see `account-tier-scoring`)."
---

# ICP builder

## Purpose

Define who the client sells to, turn that definition into rules a list can be filtered against, and keep the rules current as deals close. Produce an ICP that is a decision rule, not a description. Every criterion is either a gate with a named data source or a labeled assumption. The output tells the team who to exclude as clearly as who to target, and it predicts the client's own past wins.

## When to use

- A client needs an ideal customer profile that works as a decision rule for qualifying accounts.
- The ICP needs refining against closed-won and closed-lost deals.
- A new segment needs defining.

Route elsewhere when:

- A list already exists and must be sorted against the ICP. Use `audience-icp-filter`.
- Accounts already in the CRM need tiers. Use `account-tier-scoring`.
- The question is a TAM count or revenue sizing. Use `tam-build-and-sizing`.
- The question is a signal or a single account's readiness. Use `signal-detection-and-timing`.
- The question is a signal type: champion job changes. Use `champion-job-change-tracking`.
- The question is a signal type: hiring patterns. Use `hiring-signal-tracking`.

## Inputs

Required, in priority order:
1. Closed-won deals with value and close date, last twelve months where possible. Source: CRM export or a named list from the user.
2. Closed-lost and no-decision deals, especially late losses and good-fit accounts that went nowhere.
3. Firmographics for each deal's company: size, industry, geography, stage, model. Check fill rates first.
4. Current ICP draft, segments, and personas if any (read from `context/icp.md`).
5. Sales and account team input: the five to seven must-have questions they need answered before a deal is qualified.

Optional: customer interview notes, win/loss reasons, call transcripts, competitor lists.

If fewer than ten closed deals are available, do not refine. Below that the signal is noise. Run discovery from the team interview and the named deals instead, and label the output as a hypothesis.

## Procedure

### Principles

- **Revenue first, deck second.** The profile is derived from what paid, then checked against near-misses and late losses. A profile written before the revenue arrived is a hypothesis until it has been tested against the ledger.
- **Default-deny.** An account is out until it passes every gate. A strong score on some dimensions never rescues a failed gate on another. A perfect-fit account with no budget or no reachable buyer is a no.
- **Disqualifiers before qualifiers.** Knowing who to drop is the harder and more valuable skill. Write the exclusions first.
- **Sort every criterion into one category:** fit (checkable from research or CRM without talking to the company), readiness (an observable event that suggests change), discovery (only a conversation can answer), or disqualifier. Discovery criteria never go into the fit threshold, because the team will either guess or skip them.
- **Unknown is not a pass and not a fail.** An unknown produces the next research question. It is never filled with an assumption.
- **Measure before asking.** Check what the CRM or list actually holds before proposing criteria the data cannot support.
- **Falsifiable.** Every criterion names its source. Every gate can be answered yes or no by someone who has never met the customer.
- **Persona is part of the ICP.** The people who sign, champion, and block shape the profile in the same pass. Personas are not a separate project.

### Step 1: Check the evidence and fill rates

- Confirm which field holds deal value. Many CRMs have an abandoned standard amount field and a real custom ARR or ACV field. Use the real one.
- Confirm how the team marks a deal won. Do not assume a stage exists. If none is found, select on a populated value field over the window and state that basis.
- Measure fill rate for size, industry, geography, and stage. If any field is missing on more than 20% of records, flag the gap and say the analysis will be partial on that dimension. Do not enrich everything to fill it.
- If a CRM is not connected, ask the user to name five to ten closed-won and closed-lost deals. Work from the named list and say so.

### Step 2: Derive the proven profile from revenue

- Rank deals by revenue, not count. Group by industry, size band, stage, and geography. Compare win rates across the segments, and separately compare revenue share.
- Count distinct companies inside each segment before treating it as a pattern. A segment made up of one renewing customer is concentration, not a market.
- If one account exceeds about a quarter of revenue, report it as a concentration risk and do not build a profile around it.
- Do the sums, shares, and rankings in code where the set is larger than about twenty deals. Reason over the output; do not total rows by reading them.
- Cluster into two to four named archetypes by intersecting the revenue-dominant segments, for example "mid-market fintech in FR and DE". Each archetype needs at least two distinct companies behind it. Beyond four, collapse the thin ones.
- Label every inferred attribute as inferred, for example a buyer role the CRM never recorded.

### Step 3: Sort the criteria

Using the won, late-lost, and no-decision evidence, sort each criterion into one of four categories:
- **Fit:** size, industry, model, geography, technology, functional structure. Checkable from research or CRM.
- **Readiness:** observable events that suggest the status quo is under pressure, such as leadership change, acquisition, migration, hiring pattern. Signals, not proof. Handled in depth by the `signal-detection-and-timing` and `hiring-signal-tracking` skills.
- **Discovery:** the real business problem, sponsorship, urgency, willingness to act. Conversation only.
- **Disqualifier:** a condition that ends the opportunity. Split into hard disqualifiers (seen in stalled deals and absent from wins) and watch flags (seen in some wins, so probe rather than kill).

Ask of each disqualifier: did any closed-won deal show the same flag? If no, it is hard. If yes, it is a watch flag.

### Step 4: Build the gates in order

Order gates cheapest first, so expensive steps run only on survivors:
1. Structural fit: size band, stage, model, geography.
2. Problem evidence: something observable shows the problem exists. Not "they could have it."
3. Exclusions: competitors, current customers, prior contact, companies that sell the same thing. Run early.
4. Reachability: can the team reach a named buyer role? An unreachable fit is worth zero.
5. Deal size: can they pay the floor? Place before enrichment spend.
6. Timing: is a signal active, or is this a nurture entry?

Each gate is a binary question with a stated source. Record the reason for every exclusion. The exclusion log matters as much as the include list, because it stops the same accounts re-entering next quarter.

### Step 5: Set the tiers or score (optional)

Tiers from the gates:
- **Tier 1:** passes all gates and has an active timing signal. Worth manual research and a custom asset.
- **Tier 2:** passes all gates, no timing signal. Worth a templated, segment-level motion.
- **Tier 3:** passes structural fit only. Nurture. Never the target of paid enrichment.

If a numeric fit score is wanted, add it after the gates, not instead of them. One published framework uses a 0 to 100 score with bands of 80 to 100, 50 to 79, and below 50. The weights are the client's choice, set from their own win data, and must be recorded with a reason. A score never overrides a failed gate.

Sizing check (optional): a motion needs enough customers to be worth a segment. One published framework uses rough customer-count bands by motion, from about 160 for no-touch down to about 20 for dedicated. Treat these as one author's defaults, not benchmarks. Use them only as a sanity check, and confirm against the client's own numbers.

### Step 6: Define personas inside the ICP

For each segment, name the roles that play each part in the buying decision:
- **Champion:** wants the change and works internally for it.
- **Economic buyer:** signs and holds the budget.
- **Evaluator or technical buyer:** tests fit and can block.
- **Blocker:** has a reason to stop it.

Use titles and responsibilities from won deals. Note where the actual signers in won deals differ from the saved personas. That persona drift is a refinement finding in its own right.

### Step 7: Retro-test the matrix

- Apply the gates to the last ten closed-won accounts. They should land in Tier 1 or 2. If they do not, the matrix is wrong.
- Apply the gates to a sample of late losses. A criterion shared by winners and late losers is table stakes, not a qualifier. Remove it from the differentiating set.
- Apply the matrix to the same twenty accounts with two people working independently. If they do not land in the same tiers, rewrite the unclear gate.

### Step 8: Refine or add a segment

Refine (existing ICP):
- Show what is currently defined, in one or two lines per segment, and ask what feels off.
- Pull recent closed deals and compare patterns to the current ICP.
- Propose three to five changes, each with one line of evidence: "tighten size band to 50 to 300 (currently 50 to 1,000). Eight of twelve wins sit in 50 to 300. Five of seven losses are above 500." Lead with the place where wins disagree with the stated ICP. Propose more than five and the ICP needs full rebuild, not refinement.
- Stop if the data says the ICP holds. "No meaningful drift" is a valid answer. Inventing changes to look productive is the most common failure.

Add a segment:
- Only when a cluster of wins fits no current segment and the motion is materially different. Define its gates, personas, and exclusions using Steps 3 to 6.

### Step 9: Confirm, then save

- Present each proposed change and ask the user which to apply. Do not save without approval.
- Record each approved change with the date and the evidence it rests on.
- Recommend running the matrix over the next batch of unscored accounts to test the refinement.
- Learning loop: after enough outcomes, check which gates added separation, which signals appeared in wins and in no-decisions, which disqualifiers appeared in wins, and which unknowns were most useful to resolve. Revise the criteria, not just the numbers.

## Output

1. **ICP summary:** two to four archetypes, each with objective criteria a search can use, typical deal size, count of won companies behind it, and the evidence source.
2. **Gates and matrix:** ordered gates, each with a source and a yes/no question. Tier rules. Exclusion list with reasons.
3. **Personas:** per segment, roles and what each does in the decision, with the inferred ones labeled.
4. **Revenue view:** the revenue-ranked table by segment, share of revenue, and any concentration flag. Source coverage stated.
5. **Validation:** retro-test result on the last ten wins, two-person consistency result.
6. **Open questions:** each unknown, the question that resolves it, and who should answer.
7. **Proposed changes** (refinement only): three to five, with evidence, pending approval.

Write the approved ICP to `context/icp.md` in the client's ICP format.

## Quality bar

- Every criterion is in exactly one category: fit, readiness, discovery, or disqualifier.
- Every gate names its data source. No gate relies on a subjective rating.
- Every rate carries its denominator. Every archetype names how many companies it rests on.
- No archetype is built on one account, or on firmographics the data did not carry.
- Every exclusion has a recorded reason.
- The retro-test on the last ten wins passes, or the failures are explained.
- Inferred attributes are labeled as inferred.
- No proposed change is saved without approval.
- No thresholds or benchmarks are presented as industry standards unless cited.

## Rules

- MUST derive the profile from closed-won revenue where data exists, and state the selection basis.
- MUST measure field fill rates before proposing criteria, and drop criteria the data cannot support.
- MUST run gates in order and never let a score override a failed gate.
- MUST record the reason for every exclusion.
- MUST keep discovery criteria out of the fit threshold.
- MUST propose three to five changes at most in a refinement pass, each with evidence.
- MUST get approval before saving any change to the ICP.
- MUST NOT rank or cluster by deal count alone.
- MUST NOT present a single dominant account as a repeatable profile.
- MUST NOT refine with fewer than ten closed deals. Say so and use discovery instead.
- NEVER treat an unknown as a pass or a fail.
- NEVER infer a business problem, budget, or sponsor from firmographics or title alone.
- NEVER claim causation from correlation in output.
- NEVER state a benchmark or threshold as an industry standard unless the source is cited.

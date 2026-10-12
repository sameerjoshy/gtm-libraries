---
name: account-tier-scoring
version: 1.0.0
status: draft-for-review
description: "Use to tier accounts for human attention (Bronze, Silver, Gold) by combining intent or engagement with deal potential, after a gate check against the ICP. Use when accounts are scored by feel, when high-scoring accounts turn out to be too small or lack a buyer, or when deciding when an account is ready to hand to sales. Produces a tier, a score breakdown with Met, Missed, or Uncertain per dimension, a confidence level, and a handover decision. Not for ABM dashboards or ICP definition."
sources:
  - "Account tier scoring (MIT, Amos Bar-Joseph), gates before judgment, employee-count verification, enterprise persona gate, never-demote rule, prior-relationship floor with genuine-evaluation check, separate ACV potential assessment, memory snapshot, verified tag writes"
  - "Score and route (MIT, Ido Goldberg / Swan), intent-by-deal-size tier matrix, visibility bias, two-pass credit gate before enrichment, lazy decay with no batch rescore, change delta"
  - "ICP score and route (MIT, Udi Cohen), Met, Missed, Uncertain per criterion, score breakdown shown, High, Medium, Low confidence, AE, SDR, nurture routing"
  - "ABM engagement scoring (MIT, Rutger Katz / Neon Triforce), signal base weights, recency decay, score bands, handover requires score and buying-group coverage, false-positive rule"
---

# Account tier scoring

Places each account in a tier that tells the team how much human attention it deserves now. Every tier is the result of gates first, then intent and potential, with the reasoning written down so anyone can check it.

## Purpose

Keep reps' time on accounts that are both able to buy and showing a reason to act. Stop small accounts reaching the queue on one loud signal, and stop large accounts being dismissed for a quiet month. Produce a tier, a breakdown, and a handover decision that two people would reach the same way.

## When to use

- Accounts need tiers that set how much rep attention each one deserves now.
- Handover decisions need a checkable reason, with the signals and caps shown.

Route elsewhere when:
- The ICP itself is being defined. Use `icp-builder`.
- One account needs a meeting brief. Use `account-research-brief`.

## Principles

- **Gates before scores.** An account that fails the ICP gate, the size floor, or an exclusion is not tiered. A high intent score never rescues a failed gate.
- **Two questions, kept separate.** How strong is the intent or engagement? How large could this deal be? A tier is their intersection. Score each on its own first.
- **First-party beats third-party, person beats company.** Weight a signal by how confident you are that a real person at the account did it on purpose.
- **Intent without buyer coverage is a false positive.** A high score with no reachable buyer role is not ready for handover.
- **Never demote on a weak new signal.** A new low-weight signal never lowers a tier. Time-based decay is applied only by the explicit rule in Step 6, and only when a real new signal triggers a run.
- **Bias toward visibility, within the caps.** When genuinely borderline between two tiers, round up. But round-up never overrides a cap, a gate, or a rule that caps a tier.
- **Show the work.** Every tier carries its signal stack, its caps, and its confidence. Nothing is stated without the evidence beside it.
- **Verify writes.** A tier is only reported as applied once the record is re-read and confirms it.

## Inputs

1. The ICP and its gates, from `context/icp.md` or the `icp-builder` skill output. Without it, stop and ask for it.
2. The account record: firmographics (employee count, funding, geography, industry), lifecycle stage, and owner.
3. The first-party signal stack for the account: web visits, pricing-page visits, replies, meetings, product usage, form fills, and the person behind each signal.
4. Third-party signals: funding, hiring, technology change, intent topics. Labelled as third-party.
5. Existing contacts and their titles, checked against the buyer persona list.
6. Prior history: closed-lost deals, trials, prior meetings. Checked against the CRM, not from memory.
7. The account's prior tier, score, and dated snapshot, if any.

## Procedure

### Step 1: Gate check (runs before any scoring)

Run each in order. Any hard stop ends the run for this account and records the reason.

**1a. Size and self-serve gate.** Use the lower of the enrichment-provider count and the company's own page count. Enrichment often returns bucketed ranges whose midpoints inflate small companies. If the count is missing, a range, or within about 3x the floor, verify it on the company's own page before proceeding. Set the floor from the ICP size band, not a universal number. Funding never overrides the size floor. Accounts below the floor route to self-serve or nurture and are not tiered.

**1b. Vendor, partner, and investor check.** Accounts tagged as vendor, partner, or investor are not scored as prospects. Route them to the partnerships owner with a short note. One exception: a signup or trial from a known partner is scored in full, with the partner status flagged.

**1c. Excluded markets and competitors.** If the account matches an exclusion from the ICP (blocked segment, competitor, current customer, a company that sells the same thing), stop and record the exclusion. Require two independent confirmations before excluding on an industry or geography signal.

**1d. ICP gate.** Apply the ICP gates from the `icp-builder` output. Record Yes, No, or Unknown for each. A No stops the run. An Unknown produces a research question, not a pass.

**1e. Credit gate (two passes).** Pass 1 uses only data already held: the record, memory, CRM, and the signal that triggered the run. No enrichment tools are called in Pass 1. If Pass 1 lands at Non-ICP, or at Bronze with no new strong signal, log and stop. Enrichment, contact research, and drafts happen only in Pass 2, and only for accounts that are ICP-likely with preliminary signals at Silver or above.

### Step 2: Score intent or engagement (Q1)

Use the signal weights below as the default set, and calibrate them to the client's own wins before relying on them. These numbers are one published framework's defaults, not benchmarks.

| Signal | Default base points | Decay |
|---|---|---|
| Direct inbound request (demo, contact sales) | 15 | Persistent |
| Meeting accepted or completed | 20 | Persistent |
| Reply to outreach | 10 | Persistent |
| Pricing or ROI page view | 10 | Monthly (x0.25 per month) |
| Email click | 2 | Weekly (x0.4 per week) |
| Whitepaper or case study download | 5 | Weekly |
| Webinar attendance | 5 | Weekly |
| Website visit | 1 | Weekly (x0.5 per week) |
| Ad click | 1 | Weekly |
| Ad impression | 0.2 | Weekly |
| Social post engagement | 2 | Weekly |
| Email open alone | 0 | Not counted |

Rules that apply on top of the points:
- **Persistent signals never decay** until the account is disqualified.
- **Person-level outweighs company-level.** A signal from an anonymous visitor counts for less than the same signal from a named person.
- **Third-party signals** (funding, hiring, technology change) are context. They raise the score only when stacked with first-party signals.
- **Social engagement alone caps at Silver** at any volume.
- **A single profile view by a non-buyer caps at Silver.** Stacked with another strong first-party signal, it can qualify for Gold only if the viewer holds a buyer persona.
- **Stacking rule:** two weaker signals can outweigh one stronger signal, but never when the weaker ones are all third-party.

Score bands (default, from one framework; set your own from pipeline outcomes):
- 0 to 25: watchlist, no active engagement.
- 26 to 50: early engagement. Monitor.
- 51 to 100: warm. Buying group incomplete. Consider a senior-level warm touch.
- 101 to 150: hot. Handover only if buyer coverage (Step 5) is met.
- Above 150: in-market. Multiple stakeholders engaged.

### Step 3: Assess potential (Q2)

Assess deal potential as high, medium, or low. Weigh the whole picture; no single factor is a hard gate. Defaults fit a mid-market B2B product, so recalibrate to the client's price points.

1. **Company size** against the ICP band.
2. **Buying-team size:** how many people would use or buy what the client sells. Fewer than three suggests a founder-led sale. Scaled teams suggest a larger deal.
3. **Team maturity:** does a leader for the function exist? The fuller the structure, the higher the potential.
4. **Funding:** validated budget signal. Treat as context, not a gate.
5. **Current hiring:** roles that point to the problem the client solves are the strongest signal. Leadership hires alone are context only, because new leaders often slow buying during ramp.

Output one tag: `high-potential`, `medium-potential`, or `low-potential`. When asked to show the assessment, show all five dimensions with the evidence for each and which pulled the tag up or down.

### Step 4: Combine into a tier

Use the Gold/Silver/Bronze matrix:

| | Large potential | Small potential |
|---|---|---|
| **Strong intent** | Gold | Silver |
| **Weak intent** | Silver | Bronze |

Then apply these overrides in order:
1. **Enterprise persona gate.** At large companies (set the threshold from the ICP), a signal from a non-buyer persona caps at Silver, including stacked anonymous visits. Gold requires either a named, verified senior buyer, or two or more distinct first-party signals from named people.
2. **Prior-relationship floor.** For a closed-lost account or a past trial, raise a Silver to Gold, but only when a genuine prior evaluation exists: a prior deal, a logged sales meeting or call, or a trial record. If the closed-lost status came from something other than an evaluation, score on current merits. The floor never applies to accounts below the size gate.
3. **Borderline rule.** When an account is genuinely between Silver and Gold, round up to Gold. This does not apply when every signal is third-party. Third-party-only accounts are Silver.
4. **Caps always win.** No rule above lifts past a cap set in Steps 1 or 2.

Bronze is the floor for an ICP-eligible account. Never leave an eligible account untiered.

### Step 5: Handover decision

A tier of Gold does not on its own send an account to sales. Hand over when all of these hold:
1. Score is in the hot band or above (Step 2), **or** a critical event has occurred: a demo request, an accepted meeting, a reply from a buyer.
2. Buyer coverage is at least 50%: at least two required buying roles are identified, **or** the economic buyer is confirmed.
3. The account passes its gates (Step 1) with no open Unknown that blocks the decision.

Required buying roles come from the ICP personas: economic buyer, champion or end user, technical or evaluator, and a risk or compliance role where relevant. A critical event can bypass the score threshold but never the coverage requirement. Without coverage, marketing or the SDR continues to map the buying group.

If the account has a Gold tier but fails the coverage requirement, mark it as "Gold, coverage pending" and name the missing role. Do not alert the seller as a handover.

### Step 6: Decay, change delta, and recycling

- Decay is lazy. It runs only when a real new signal triggers a scoring run. There is no scheduled batch rescore.
- When a run applies decay: a Gold scored more than 60 days ago with no new signal moves to Silver. A Silver scored more than 90 days ago with no new signal moves to Bronze. Bronze does not decay further. Record the decay in the memory note.
- A new weak signal never lowers a tier. Only the time-based decay rule above, or an explicit gate in Step 1, can lower it.
- Recycling: if an account's score falls below a set level for a set time, move it back to nurture and alert marketing. Set both numbers from the client's data; the defaults are a score under 40 for 30 days.
- Every run records the change delta: prior tier, new tier, and what changed.

### Step 7: Breakdown and confidence

Show the breakdown, not just the tier. For each dimension, state Met, Missed, or Uncertain, with the value found:

| Dimension | Value found | Status |
|---|---|---|
| ICP fit | | Met / Missed / Uncertain |
| Size | | Met / Missed / Uncertain |
| Buyer persona | | Met / Missed / Uncertain |
| Intent points | | Met / Missed / Uncertain |
| Potential | | Met / Missed / Uncertain |
| Buyer coverage | | Met / Missed / Uncertain |

Confidence:
- **High:** all gates Met, at least three dimensions Met, and a verified buyer contact.
- **Medium:** mixed signals, or one or more dimensions Uncertain.
- **Low:** insufficient data, or a core gate Missed.

Route the output:
- **Gold, handover met:** to the seller queue with the reasoning and a recommended next action per buyer role.
- **Gold, coverage pending:** to the research queue, naming the missing role.
- **Silver:** logged. Reviewed in a regular batch, not alerted.
- **Bronze:** logged only.
- **Gated out:** logged with the reason.

Where the team uses the AE, SDR, and nurture split, map Gold with handover to AE, Gold without coverage or Silver with a clear next step to SDR, and everything else to nurture.

### Step 8: Record the decision

Write one memory snapshot per run, prepended to the account's history without deleting prior entries:

```
[TIER: Gold] [Mode: intent] [date] [CONFIDENCE: Medium]
Gates: ICP Yes, size Yes, exclusions none
Signals (strongest first): [type, person or company, date]
Buyer coverage: 2 of 4 roles (economic buyer confirmed)
Potential: high, [one sentence on the strongest factor]
Caps or floors applied: [enterprise gate / prior-relationship floor / none]
Change delta: Silver to Gold, [what changed]
```

Write the CRM note in one line: tier, date, reasoning, top signals. Re-read the record to confirm the tier field has changed. If it hasn't, retry once. If it still fails, mark the run as "tier write failed, manual fix needed" and do not report the tier as applied.

## Output

For each account in the run:
1. Gate result (passed, or the reason it stopped).
2. Tier, confidence, and handover decision.
3. Breakdown table with Met, Missed, or Uncertain per dimension.
4. Signal stack, strongest first.
5. Caps and floors applied.
6. Change delta.
7. Next action, for the seller or the research queue.

For a batch: a summary count by tier and gate outcome, then the Gold accounts, then the open Unknowns.

## Quality bar

- Every tiered account passed the ICP gate and size gate, with the evidence recorded.
- Size counts were verified where the enrichment count was in the risk band.
- No account is Gold on third-party signals alone.
- No account is handed over on score alone. Buyer coverage is shown.
- Every cap or floor applied is named.
- No tier was lowered by a weak new signal.
- Decay was applied only where the rule triggers, and recorded.
- Every tier write was re-read and confirmed, or flagged as failed.
- Thresholds and weights are labelled as defaults or as client-calibrated.

## Rules

- MUST run the gate check (Step 1) before any scoring.
- MUST verify the employee count where the enrichment figure is unreliable or near the floor.
- MUST NOT let a high score override a failed gate or a cap.
- MUST NOT hand an account to sales on score alone. Buyer coverage is required.
- MUST NOT lower a tier on a weak new signal.
- MUST NOT run scheduled batch rescoring. Decay runs lazily.
- MUST show the breakdown and the confidence level with every tier.
- MUST record the change delta and the memory snapshot on every run.
- MUST NOT report a tier as applied until the write is re-read and confirmed.
- MUST NOT present the default weights or bands as industry benchmarks. Calibrate them to the client's wins or label them as defaults.
- NEVER promote an account on anonymous or third-party signals alone where an enterprise gate applies.
- NEVER enrich or draft outreach for Bronze or Non-ICP accounts.

## Boundaries

- Tiers individual accounts for attention. It does not define the ICP: use `icp-builder`.
- Does not build the ABM engagement dashboard or its composite score for client reports: use `abm-account-engagement-report`. That score ranks accounts for a report. This skill makes the decision about attention and handover.
- Does not detect or interpret a single signal in depth: use `signal-detection-and-timing`. Hiring and champion changes have their own skills.
- Does not write outreach or sequences.

---
name: closed-lost-revival
version: 1.0.0
status: draft-for-review
description: "Use for a quarterly revival sweep over pipeline the company already paid to create: closed-lost deals, proposals that went quiet, champions who changed jobs, and contacts who engaged and then went silent. Applies hard gates, requires dated evidence before any draft, names each loss pattern against a library, and ships one capped campaign per quarter for human approval. Revives only accounts that engaged and then disengaged. Not for cold contacts who never replied (those go to prospecting), and not for live threads still inside a cadence."
sources:
  - "Closed-lost revival (MIT, Rutger Katz / Neon Triforce), three revival lanes (closed-lost and proposal-gone-quiet, champion job changes, engaged-then-quiet threads), hard gates, evidence before drafting, opener posture, loss-pattern library, quarterly campaign compression with a cap of 5 to 15 accounts, current-offer rule, human approval contract, next-touch timings"
  - "Benchmark and rate figures in the source (win rates, post-proposal win rates, champion movement) are vendor or industry estimates, context only"
  - "Adapted for GTM-360: an anecdote about a single vendor's pipeline result removed as unverified; champion-move detection cross-referenced to champion-job-change-tracking; the human approval rule kept as a hard requirement"
---

# Closed-lost revival

## Purpose

A large share of opportunities end closed-lost. That pool already knows the company, and in most CRMs no one owns it. Revival means working an asset the company has already paid to create. It is not a heroic save.

The prime rule: revive the accounts that engaged and then went quiet. Never revive a contact who never replied. That contact is a stranger who has seen the logo.

## When to use

- Running the quarterly revival sweep.
- Closed-lost or proposal-stage deals have gone silent, and nobody has reopened them.
- Pipeline is being bought through new leads while a warm pool sits untouched.
- A known champion has changed jobs.

Route elsewhere when:

- The thread is still active, with less than 60 days of silence. That is a cadence problem, not revival.
- The contact never engaged. Use `outbound-cold-email` or `prospect-list-building`.
- The question is about winning back the reasons for loss. Use `win-loss-program`.
- The question is about detecting champion moves continuously. Use `champion-job-change-tracking`. This skill only uses verified moves inside a quarterly campaign.

## Inputs

- Closed-lost deals with close date, original objection, last contact date, and deal owner.
- Proposals sent, with the date and what was promised.
- Champions and their history: whether they realised value at the origin company, and whether they have moved.
- Engagement history for each contact, with the last substantive exchange.
- Do-not-contact flags, and any partner, advisor, or peer relationships to exclude.
- The current offer, meaning what the company is selling or sharing now.

## Procedure

### Step 1: Apply the hard gates per lane

Each lane has gates. A lead that fails a gate is skipped immediately.

**Lane A: closed-lost deals and proposals that went quiet.** This is the highest-value lane. Post-proposal win rates are cited at 31 to 50% in the source (industry research). A buyer who reached proposal was more likely to buy than not, so a silent death at that stage is expensive.

- Skip if the contact is marked do-not-contact.
- Skip peers, advisors, partners, and friendly industry contacts. They never ride a sales cadence.
- Skip cold-never-replied contacts.
- Skip losses to a basic mismatch, such as a wrong ideal customer profile or a product that cannot do the job. Revival cannot fix fit.

**Lane B: champion job changes.** About a fifth of past champions are cited as moving in a given year, from industry estimates. Each verified move is a warm route into an account the company has not worked.

- The champion must have realised value at the origin company, meaning the deal was won, or they were an active user who drove workflows. A contact on a lost deal is familiarity, not a champion. Skip.
- Skip if the origin company declined within the last 90 days. The champion is leaving a company that just said no.
- A new employer that is a competitor or on an exclusion list: log it, no outreach.
- A new employer below the minimum viable size: at most a personal note from the former relationship owner. Never a sales motion.
- A move into an advisory, fractional, or board role: treat as a partner conversation, not a deal.

**Lane C: engaged-then-quiet threads.**

- Last real exchange 60 or more days ago. Under 60 days is an active cadence.
- Real engagement happened: a substantive reply, an attended meeting, or a real conversation. One-way sends do not count.
- The contact is still at the same company. If they have moved, route them to Lane B. The account must still fit the ideal customer profile.

### Step 2: Gather evidence before drafting

**Lane A.**

- Closed-lost, six to eighteen months ago: this is the usual window, because objections resolve, budgets reset, and sponsors rotate. Record the original objection, the last contact date, and the owner.
- Proposal gone quiet, sixty to 120 days ago: no response, and the contact is still at the company. Record the exact date and what the proposal promised.

**Lane B.**

- Confirm the current employment live. Cached enrichment data lags exactly where job moves happen. Read the full profile, not the headline.
- The wrong-person guard is a hard rule: the destination profile's own work history must include the origin company. A name and company match alone is never enough.
- Record the month of the move. The usual outreach window is days 14 to 45 in the new role. In the first two weeks the person is absorbing the job. Later, the window for a fresh start has closed.

**Lane C.**

- Pull the last message, its date, and the last open question in the thread.
- Classify the silence. The class sets the opener:
  - Ghosted: interest, then nothing.
  - Objection pending: "let us think about it", then nothing.
  - Timing miss: "circle back after an event" that never happened.
  - Changed landscape: a reorganisation, a freeze, or a role change in the middle of the conversation.

### Step 3: Name the loss pattern

Before drafting for a Lane A account, match it to a loss pattern.

1. Match the account against existing loss categories. Common ones include: budget timing, champion departed mid-deal, chose a competitor on one capability, trial started at the wrong moment, sponsor lacked authority, and a price-to-value gap at the proposed scope.
2. If it matches, use the revival approach that worked for that category before.
3. If it matches nothing, create a new category, define its approach, and record this account as the first worked example.

Treating every loss as a unique investigation gives no leverage. A library means most losses fit a pattern that has already been worked out.

### Step 4: Draft the opener

Lane A:

- Open with the specific objection from the first cycle. Do not use generic win-back language. Example: "When we last spoke, you flagged [exact objection]. Since then, [concrete change]."
- Do not use "just checking in", "touching base", or reassurance hedges such as "no pressure" or "no agenda". Buyers know a seller is selling, and the hedge reads as weakness.
- Ask for a specific outcome, not permission. "Worth 15 minutes to see if the picture has changed?" is better than "Would you be open to reconnecting?" Note that the phrase "worth 15 minutes" is flagged in `outbound-cold-email` as a weak close. Use the specific ask there too, not that phrase.

Lane B:

- Refer to the earlier relationship in terms of what they did with the product, not what the company did for them.
- Do not diagnose in the first message, and do not use stock congratulations. Name the specific reason their move makes this relevant.

Lane C:

- Acknowledge the gap briefly. Do not apologise for it.
- Anchor on their last question: "You asked about [specific thing]. Here is what has changed since."

### Step 5: Compress into one campaign

Ship one campaign package per quarter, not a stream of ad hoc sends.

1. Apply the gates. Only the survivors go forward.
2. Remove duplicates across lanes. The same person appearing twice, such as a champion who moved from a closed-lost account, gets one thread.
3. Rank by signal strength and freshness. Champion moves first, then proposals gone quiet, then engaged-then-quiet, then older closed-lost. Apply a recency decay within each lane.
4. Cap at 5 to 15 accounts. If more than 20 survive, take the top 15. If fewer than 5 survive, send fewer. Never pad. Each account gets one credible re-open per cycle, so quality per touch is the whole economics of revival.
5. Give every account a one-line premise with a dated basis: "Closed-lost in November, objection was integration depth. They posted an integration engineer role last week." A premise that cannot cite a date does not ship.

Current-offer rule: the people reached here went quiet months or years ago, and what was offered then may be retired. Every draft should reflect what the company is offering now. If the old asset has been replaced, say so: "that assessment became something sharper." Do not re-pitch a retired version, and do not pretend the first cycle never happened. The dated trigger opens the message, and the current offer carries the ask.

Cadence: quarterly, by design. A monthly sweep drains the pool and catches movers too early. Quarterly spacing also lets budgets reset and objections age out. Do not speed it up because candidates are piling up.

### Step 6: Route for human approval

Revival touches people with history, and one clumsy message can end the only re-open the company gets.

- Every draft goes to a human review queue, with its lane, premise, evidence, and a next-touch date. Nothing sends automatically.
- Next-touch timings: closed-lost, 7 days. Champion moves, 10 days, since they are busy. Engaged-then-quiet, 14 days.
- One follow-up only. If there is no reply, the account moves to passive nurture until a new signal fires. Revival is one knock, not a new cadence.
- Log each shipped cohort and its outcomes. Reply and conversion rates by lane, quarter on quarter, show which lanes deserve more of the 15 places.

## Output

- The sweep summary: how many accounts were audited per lane, and how many failed each gate.
- The campaign package: up to 15 accounts, each with its lane, its loss pattern, its premise and evidence, its draft, and its next-touch date.
- The kill list, with the reason for each exclusion. The kill list should be longer than the send list. That ratio is a health check.
- The cohort log to be filled in after the outcomes come back.

## Quality bar

Every shipped account has a premise tied to a dated trigger. The package is capped, deduplicated across lanes, and ranked by freshness. Champion movers are verified against the destination profile's own work history, and contacted in the 14 to 45 day window, not the week the alert arrived. Openers name the original objection or the last open question. They contain no "just checking in" and no reassurance hedges, and they carry the current offer, not the retired one.

Watch for accounts that never engaged slipping into the list, premises with no date, and the same message going to a contact across more than one lane.

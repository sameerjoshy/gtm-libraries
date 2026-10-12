---
name: account-research-brief
version: 1.0.0
description: "Use before a first meeting, an ABM push, or a territory review, when a single named account needs a sourced brief for the seller. Covers firmographics, positioning, buying committee, live signals, and discovery questions, with every claim tagged as sourced or inferred. Single account only; for portfolio ICP work see icp-builder."
---

# Account research brief

Produces a one-account brief an AE can use in a meeting. Every claim is tagged as sourced or inferred, so the seller knows what they can say out loud.

## Purpose

Answer: why this account, why now, who to speak to, and what to ask. Anything that does not help the seller act is left out.

## When to use

- An account executive needs a one-account brief before a meeting or a decision.
- The question is why this account, why now, who to speak to, and what to ask.

Route elsewhere when:
- Many accounts need placing in tiers. Use `account-tier-scoring`.
- A contact list needs sorting against the ICP. Use `audience-icp-filter`.

## Inputs

- **Account identifier.** Use the company's domain or URL slug, not its display name. Display-name matching returns near-matches, and researching the wrong company is worse than researching nothing. If there is no confident match, stop and report the ambiguity.
- **Purpose (ask once).** One sentence on the decision the brief supports: QBR, competitive deal, cold outreach, inbound triage, first meeting. If the user declines, produce a general brief and say on the first line that it is not tailored.
- **Target titles and record count.** Confirm both before pulling any people data.
- **Optional:** existing CRM history, prior research reports. Check uploaded reports against live sources before using them. Third-party reports sometimes mix up companies with similar names or cite old news.

## Procedure

1. **Resolve** the identifier and confirm the entity.
2. **Firmographics:** size, industry, headquarters, founding year, funding stage, description.
3. **Composition:** how employees split by function and seniority. A company that is mostly engineering sells differently from one that is mostly sales.
4. **Positioning pillars:** three to six themes from the company's own description and tagline. Quote the source phrase. These are the words the buyer uses about themselves.
5. **Live signals (last 90 days):** leadership moves, funding, product launches, hiring by function, partnerships. Hiring by function is the most current evidence of where budget is going.
6. **Buying committee:** economic buyer, champion, technical buyer, user buyer, likely blocker, each with a named person where the data supports one. Where no name is found, describe the role and mark it as a gap.
7. **Triage** against the stated purpose. A layoff outranks a product release for a renewal review. A product launch outranks a routine hire for a competitive deal. Drop anything that does not connect to the purpose.
8. **SWOT,** with every point tagged `sourced` or `inferred`.
9. **Discovery questions:** strategic (three to five) and tactical (three to five). Each must be something only the buyer can answer.
10. **Next actions:** three to five, each naming a person, the channel, and the timing. Draft one short outreach message for the first action.
11. **Summary:** the strongest fit, the biggest risk, and the fastest route to a proof point.

## Depth and routing

Pick the depth from the ask. Most asks need a short read. Scale up only when the user signals depth, or when the stakes justify it, such as board prep or executive outreach.

- A quick fit check ("is this account a fit?"): one paragraph, with the answer first.
- A standard brief: the steps above at summary level.
- A full dossier for a senior meeting: all the steps in full.

Over-researching a question a sentence could answer is the most common failure.

Choose the facet that matches the ask:

| Ask | Focus |
|---|---|
| What does the company do | Firmographics and positioning |
| Who to speak to | Buying committee |
| What is happening now | Live signals, last 90 days |
| How they sell | Go-to-market motion and pricing posture |
| Digital footprint | Domain, traffic, search presence |
| Money and ownership | Funding, ownership, runway |
| Tools they run | Technology stack |
| Competitor mentions | Where the account talks about rivals |

Cheap before expensive: check the CRM and prior briefs first, then free public sources such as the company's own site and news, then paid enrichment only where a real gap remains.

Inferred figures (estimated revenue, motion type, runway) are marked "estimated" or "appears to be", and never stated as fact. Quotes appear only where they occur in a source. Never invent a quote, a priority, or a financial figure.

Write any durable fact the research surfaces (financial state, stack, motion) to the account record, so the next person inherits it.

## Output

A markdown file named `account-brief-<company>-<YYYY-MM-DD>.md`, with these sections in order:

1. Summary (purpose, situation, top three facts, highest-leverage actions)
2. Company snapshot (table)
3. Positioning pillars, quoted
4. Strategic priorities, each with its evidence
5. Buying committee map, with gaps marked
6. Live signals, sourced or inferred
7. Discovery questions
8. Next actions, with one draft message
9. Conclusion

A quick version (purpose, buying committee, discovery questions, next actions) is available on request.

## Privacy in shared briefs

Briefs are often forwarded. Show contact names as initials, emails as domain only, and phone numbers masked. The full detail stays in the CRM.

## Quality bar

- Every claim is tagged `sourced` or `inferred`.
- Every SWOT point has a tag.
- Gaps are stated in the brief, not left blank.
- No executive, funding round, or job opening appears unless a source supports it.
- Tenure under six months is flagged as a timing signal.
- Any date already in the past that should still be in the future is flagged for checking.

## Rules

- One account at a time. Portfolio ICP and scoring work go to `icp-builder` and `account-tier-scoring`.
- Not a content piece. Outreach is limited to one draft per brief.

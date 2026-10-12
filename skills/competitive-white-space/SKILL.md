---
name: competitive-white-space
version: 1.0.0
description: "Use for a competitive positioning review: which messages every competitor repeats (saturated), which nobody says (white space), and what positioning the company can own. Takes competitor URLs or names. Not a monitoring report (use competitive-intelligence) and not a single-company overview (use account-research-brief)."
---

# Competitive white space

Shows what the market says, what it does not say, and where the company can take a position no competitor holds.

## Purpose

Turn competitive research into positioning and targeting choices. Every finding must change what the company says or who it targets.

## When to use

- The team needs to find claims no competitor makes, and turn them into positioning and targeting choices.
- Competitor messaging looks alike and the team needs to know where it can stand apart.

Route elsewhere when:
- The question is a dated change at a competitor. Use `competitive-intelligence`.
- The question is the company's own one-account research. Use `account-research-brief`.

## Inputs

- **Competitor URLs** (best), or names (the skill finds the sites), or a company URL plus "find competitors". Three to five competitors. More dilutes the analysis; fewer than three limits the patterns.
- **Company context.** Ideally the output of `account-research-brief` or a company overview, so the white space can be tied to the company's own position.

## Procedure

1. **Identify** competitors if not supplied. Choose three to five with direct overlap with the target market.
2. **Research** each: homepage, about, product, pricing, case studies, and review-site presence.
3. **Evaluate** through a fixed lens: positioning versus execution, technology versus services, audience fit, depth of support, switching friction, and whether the competitor identifies buying signals or works blind.
4. **Messaging saturation map.** Group the claims every competitor makes. A claim made by three or more of the set is saturated. Saturated claims are not differentiators, even when they are true.
5. **White space.** Find claims that no competitor makes, or makes weakly, that the company can make credibly. For each, check whether the company has proof. A white-space claim without proof is a hypothesis and is labelled that way.
6. **Positioning direction.** Build from the white space, not from the company's current messaging.
7. **Pain points.** Tie each unique pain to a white-space gap.
8. **Targeting.** Rank ICP segments by where the white space is most valuable.
9. **Hooks by buying stage** (unaware, aware, engaged), each tied to a white-space claim.

## Output

A document titled "[Company] Competitive White Space", with these sections in order:

1. Competitor profiles (one short card each)
2. Comparison matrix
3. Messaging saturation map: what everyone says
4. White space: what nobody says, with proof status for each
5. Positioning direction
6. Pain points only this company can solve
7. Targeting priorities
8. Messaging hooks by buying stage
9. Key takeaways (five to eight bullets)

## Writing rules

These matter because the document is read by people outside marketing.

- Plain language on every line. If a smart non-marketer would need a second read, rewrite it.
- Avoid jargon such as "de-risk", "table stakes", "moat", "leverage" as a verb, "value proposition", "north star", and "at scale". Say what the thing means in plain words.
- Headings state the difference in plain terms. For example: "The same team stays on your project from start to finish", not "Delivery stability as a de-risker".
- No em dashes, no emoji, no code blocks in the output.
- Paraphrase competitors. Quote only briefly and sparingly.
- Do not invent data. Write "Unknown" where a fact is missing.

## Quality bar

- Each white-space claim has a proof status: proven, partly proven, or hypothesis.
- No saturated claim is presented as a differentiator.
- Every takeaway changes a message or a target.
- No jargon from the banned list appears.

## Boundaries

- Positioning and messaging only. For monitoring over time, use `competitive-intelligence`.
- Competitor claims are as stated on their sites. Verify any performance claim before using it in the company's messaging.

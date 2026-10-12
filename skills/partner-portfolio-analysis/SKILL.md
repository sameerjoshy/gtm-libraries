---
name: partner-portfolio-analysis
version: 1.0.0
description: "Use to prepare for a meeting with an investor, accelerator, or channel partner by analysing how that partner's portfolio companies use the product. Produces a partner-facing summary of product penetration, plan mix, usage, and open pipeline with no financial figures, plus a separate internal sheet that holds the account-level financial detail. External sharing happens only with explicit confirmation. Maintains a registry of the portfolio mapping so later analysis starts from it. Not for a single account's figures or for partnership strategy without a portfolio data pull."
---

# Partner portfolio analysis

## Purpose

A partner meeting goes better when the team knows how the partner's companies already use the product. The analysis has to be shareable with the partner, so it cannot show revenue. The team also needs the financial detail internally. This skill produces both, keeps them apart, and records the portfolio mapping so later work can reuse it.

## When to use

- Preparing for a meeting with an investor, accelerator, or channel partner whose portfolio is relevant.
- Building a readout of product footprint and adoption across a fund's companies.
- Feeding a portfolio mapping into later pipeline-overlap work.

Route elsewhere when:

- The question is one account's figures. Use `account-research-brief`.
- The question is partnership strategy. Use `partner-ecosystem-architect`.
- The question is open pipeline across the whole business. Use `pipeline-review`.

## Inputs

- The partner's portfolio list, from a page or a pasted list.
- Account data for each portfolio company, matched by email domain: paying status, plan, activity over the last 30 days, and feature adoption.
- Open opportunities for each company, by domain: name, stage, close date, owner. Amounts are read but kept internal.
- The registry of earlier portfolio runs, if one exists.

## Procedure

1. **Extract the portfolio.** Read the partner's list. Where the page does not parse cleanly, use a pasted list instead, and say that the list was pasted.
2. **Match each company to an account by domain.** Record the match, and list ambiguous or unmatched domains separately. Do not count an ambiguous match silently.
3. **Pull open pipeline by domain,** with stage and close date. Strip amounts from anything going into the partner-facing output.
4. **Write the partner-facing summary, with no financial figures:**
   - footprint across the portfolio;
   - paying against free use, and plan mix;
   - feature-level usage and adoption;
   - open opportunities by stage, with no amounts;
   - growth signals and any upsell angles, framed as questions for the team;
   - an appendix on match quality, with the ambiguous domains named.
5. **Write the internal sheet,** with account identifiers, domains, plan, paying status, usage, the financial detail, and a summary tab with the portfolio totals.
6. **Set sharing.** Default to internal only. Create an external link only after the person who requested the analysis confirms it.
7. **Update the registry** with the partner, the run date, the links to each output, and each company's domain and account identifiers, so the next run starts from it.

## Output

- A partner-facing summary with no dollar figures in any part of it.
- An internal sheet with the full account detail, marked internal.
- The list of ambiguous and unmatched domains.
- The updated registry entry.

## Quality bar

The partner-facing output has no financial figure anywhere, including charts, labels and appendices. The internal sheet is never shared by default. External sharing requires explicit confirmation. Ambiguous matches are disclosed. Watch for a dollar figure leaking into a chart label, a sheet link shared without confirmation, and a registry left out of date.

---
name: seo-topic-research
version: 1.2.0
description: "Use when a B2B or SaaS site needs an SEO content roadmap grounded in commercial reality, so that organic search brings pipeline rather than traffic from the wrong audience. Runs the research in order: extract content opportunities from the account picture, validate them against real search demand, qualify each keyword against the results, filter for commercial fit (pipeline potential, ICP match, honest product fit, client alignment, and whether a page is new, an update, or a cannibalization risk), shape each survivor into a content format, and prioritize into a build order. Uses `seo-serp-qualification` and `seo-topic-prioritization` for the last two steps. Not for account intake (see `seo-account-context`)."
---

# SEO topic research

## Purpose

An SEO plan built from keyword lists tends to chase search volume, and volume brings the wrong readers. This skill runs topic research in an order that keeps commercial reality in view at every step, so the roadmap brings in buyers the company can sell to.

## When to use

- A company needs an SEO content roadmap.
- An existing content plan is generating traffic but no pipeline.
- A team asks what it should publish to rank for commercially useful searches.

Route elsewhere when:

- The account picture is missing. Use `seo-account-context` first.
- The question is the format of one topic. Use `seo-content-format-selection`.
- The question is whether one keyword can be won. Use `seo-serp-qualification`.
- The question is the build order. Use `seo-topic-prioritization`.

## Inputs

- The confirmed account intelligence document from `seo-account-context`.
- Access to search demand data, through whatever tool the team uses.
- The company's existing pages and their performance.

## Procedure

Work through steps one to six in order. Each step uses the output of the one before.

### Step one: extract opportunities

Turn the account picture into content opportunity angles. These are business angles, not keywords. Sources of opportunity:
- competitor plays, where a rival is weak or commonly compared,
- objections customers raise, which content can answer,
- feature, use-case, and vertical pages the company sells into,
- pain-led topics in the buyer's own words.

Every angle must cite a named signal: a call, a communication, or a data point. An angle without a signal is a guess.

### Step two: validate demand

For each angle, find the search terms that show whether people look for it. Record volume and difficulty where the tool provides them. Group the validated terms under the angle they serve, and use the seed patterns that suit each opportunity type. The output is a candidate pool: keywords grouped by opportunity, ready for qualification. Demand validates an angle. It does not decide strategy.

### Step three: qualify against the results

Hand the candidate pool to `seo-serp-qualification`. Many candidates should be killed there. That is the step working.

### Step four: filter for commercial fit

Test each qualified keyword against five gates:

1. **Pipeline potential.** Could a reader who arrives here become a deal?
2. **ICP match.** Is the reader the ideal customer, or someone else?
3. **Honest product fit.** Does the company's product really answer the question? Do not promise what the product does not do.
4. **Client alignment.** Does the topic fit the priorities confirmed in the account document?
5. **Net-new, update, or cannibalization.** Is there an existing page that already covers this? If yes, updating it may beat a new page, and a new page could compete with it.

A keyword that fails the first two gates is a traffic play. Traffic for the wrong audience is a cost, not a win. Remove it.

### Step five: shape the format

Pass survivors to `seo-content-format-selection` to choose each page's format. The format decides the structure and the call to action.

### Step six: prioritize

Pass the shaped list to `seo-topic-prioritization` to set the build order, with quick wins first.

## Output

- The opportunity inventory, with the signal behind each angle.
- The validated candidate pool, grouped by opportunity.
- The qualified list, with killed topics and the reasons.
- The fit filter results for each survivor, including any update or cannibalization decisions.
- The format for each topic, and the build order.

## Quality bar

Every opportunity cites a signal. Demand validates angles without deciding strategy. Killed keywords are recorded with reasons. Each survivor passes the fit gates, and an update is preferred to a new page where one would cannibalize. Watch for a roadmap of high-volume keywords with no buyer behind them, angles with no signal, and a new page that competes with an existing one.

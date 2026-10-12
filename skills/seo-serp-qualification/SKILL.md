---
name: seo-serp-qualification
version: 1.0.0
description: "Use to check whether a keyword candidate can be won, by looking at what actually ranks for it, before any content is commissioned. Assesses intent clarity, the content format that the results reward, the competitive landscape, and whether the gaps are beatable, then gives each keyword a QUALIFY, CONDITIONAL, or KILL verdict with its reason. Many topics should die at this step. Not for prioritising the topics that pass (see seo-topic-prioritisation)."
---

# SEO SERP qualification

## Purpose

A keyword can look attractive on volume and still be impossible to win, because the results are dominated by sites that cannot be displaced, or because the query means something other than what the team wants. This skill reads the results for each candidate and decides whether the topic is worth building.

## When to use

- A keyword list needs a reality check before content is commissioned.
- A topic has been proposed and the team wants to know whether it can rank.
- A previously killed topic is being reconsidered, and the reason for the kill needs checking.

Route elsewhere when:

- The question is the order of topics that pass. Use `seo-topic-prioritisation`.
- The question is finding topics. Use `seo-topic-research`.

## Inputs

- The keyword candidates, with their volume and difficulty figures if available.
- The company's proposition and the page that would answer each query.
- The date of the check.

## The four checks

1. **Intent clarity.** Do the results agree on what the searcher wants: a definition, a comparison, a product page, a how-to? If the results mix intents, the query is unclear, and the page must choose one.
2. **Rewarded format.** What format do the top results use: a long guide, a tool, a list, a comparison, a video? A page in a different format will struggle unless the format change is a deliberate advantage.
3. **Competitive landscape.** Who ranks? If the top results are dominated by very large sites with no obvious weakness, a new page is unlikely to displace them soon.
4. **Beatable gaps.** Are there weak results: old pages, thin content, or pages that do not match the intent well? A gap that the company can fill with a better answer is what makes a topic worth pursuing.

## Verdicts

- **QUALIFY:** intent is clear, the format is achievable, and there are beatable gaps. Proceed.
- **CONDITIONAL:** worth pursuing only if one stated condition holds, such as a format the company can produce, or a supporting page that already exists. State the condition.
- **KILL:** intent is unclear, the format is out of reach, or the results cannot be beaten. State the reason, and do not reconsider without new evidence.

## Procedure

1. **Run the search** for each candidate and record the top results.
2. **Assess each of the four checks** and record the evidence, such as the format and the domain types seen.
3. **Give the verdict** with its reason.
4. **For each conditional verdict,** name the one condition that would change it.
5. **Record the date** of the check, since results change.
6. **Return the list** with qualified topics separated from the rest.

## Output

- Each candidate with its verdict, the four check results, and the reason.
- The conditions attached to each conditional verdict.
- The date of the check.

## Quality bar

Every verdict cites what the results show, not the keyword figures alone. Killed topics carry a reason. Conditionals name one condition. The check date is recorded. Watch for qualification on volume alone, a format mismatch passed as qualified, and conditionals with several vague conditions.

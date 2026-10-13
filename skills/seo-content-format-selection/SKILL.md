---
name: seo-content-format-selection
version: 1.2.0
description: "Use when choosing the right content format for each surviving SEO topic, such as a comparison or alternatives page, a product landing page, or a guide, and grouping related keywords into one page. Format drives the page's purpose, structure, call to action, and how it ranks, so the search results for each topic should decide it. Also flags site-architecture changes that a new page would need. Not for topic research (see `seo-topic-research`) or the build order (see `seo-topic-prioritization`)."
---

# SEO content format selection

## Purpose

Writing a blog post for every keyword is a common mistake. A comparison search wants a comparison page, a product search wants a product page, and a how-to search wants a guide. A page in the wrong format fails however well it is written. This skill assigns the format for each topic, groups related keywords so one page serves them, and flags any structural change the site needs.

## When to use

- Qualified topics are waiting for a format decision.
- A team asks whether a topic should be a landing page or a blog post.
- Several keywords look like they need separate pages, and the team wants to know whether one page would do.

Route elsewhere when:
- The question is finding topics. Use `seo-topic-research`.
- The question is the build order. Use `seo-topic-prioritization`.

## Inputs

- The qualified topics, with the search results recorded for each.
- The site's existing pages and navigation.
- The product description and its main call to action.

## Procedure

### Formats

- **Alternatives page:** for searches that name a competitor or ask for alternatives. Structure: a fair comparison, when each option suits, and a call to action for the company's product.
- **Comparison page:** for searches that set two or more options against each other.
- **Product or landing page:** for searches that name a solution or a category and signal buying intent. Structure: the problem, the solution, proof, and a demonstration call to action.
- **Guide:** for searches that ask how to do something or learn about a subject. Structure: a complete answer, with a clear route from the guide to the product where it fits.

### Steps

1. **Read the search results** for each topic. The results show which format the audience and the engine reward.
2. **Match the format** to the results. If most results are comparisons, a comparison page is the default. If the results are guides, a guide is the default, even if the company would prefer a product page.
3. **Group keywords** that share one intent. Keywords with the same intent and the same results are served by one page, not several.
4. **Split keywords** that look similar but need different formats. Do not force them onto one page.
5. **Set the call to action** for each page to match its purpose. A guide's call to action is a next step. A product page's call to action is a demonstration or trial.
6. **Flag architecture changes:** new pages that need a parent section, links from existing pages, or a change to navigation.
7. **Check for cannibalization** against existing pages with the same intent, and note any page that should be updated instead.

## Output

- The format for each topic, with the search results that support it.
- The keyword groups, each served by one page.
- The architecture flags, and any existing page to update.

## Quality bar

Each format matches what the search results reward. Keywords with the same intent share a page, and different intents do not. Each page's call to action fits its purpose. Watch for a blog post where the results want a comparison, one page stuffed with keywords that need different formats, and new pages duplicating an existing one.

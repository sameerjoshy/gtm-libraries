---
name: recent-discourse-sweep
version: 1.1.0
description: "Use when a decision depends on what the market said about a company, product, category, or person inside a dated window, such as before a first touch, a renewal call, or a positioning bet. Lists the venues first, reads each one and records whether it returned results, came back empty, or was never reached, dates every item, and produces a sourced synthesis with a coverage report. Not for a brand's own mentions and reputation (see brand-mention-monitor) or for one company's profile (see account-research-brief)."
---

# Recent discourse sweep

## Purpose

A decision made on what people said last year, or on one loud thread, is a bad decision. This skill reads the venues where a topic is discussed within a fixed window, and it reports what was not covered as clearly as what was. An empty result counts as a finding only when the venue was reached and read. Otherwise it is a gap in the search.

## When to use

- Before a first touch to an account, to see what it has said recently.
- Before a renewal call, to see what the customer or its market has said.
- Before a positioning or content bet that depends on whether a trend is real.
- When a finding is claimed, and the team wants to know whether the market really says it.

Route elsewhere when:

- The question is the company's own brand mentions. That is a monitoring question, not a sweep (see `brand-mention-monitor`).
- The question is a single company's profile. Use `account-research-brief`.

## Inputs

- The topic, in plain words.
- The window, in days (default thirty).
- Any disambiguation terms, such as the industry, a product name, or a founder's name.
- The decision the sweep supports.

## Procedure

1. **Fix the window and list the venues before searching.** Name the window in days. List every venue to be read, by category: community discussion, technical forums, video, job postings, filings and preprints, trade press, short-form social, and general web search. A venue not on the list cannot be reported as missing later.
2. **Keep the topic clean.** The topic is a routing key: plain words, no brackets, and no comparison unless one is wanted. Put disambiguation into the search terms, not into the topic.
3. **Read each venue one at a time** and record one of three states:
   - Read, with results.
   - Read, and empty.
   - Never reached.
   These are different facts. Collapsing them into "nothing found" is the failure this skill exists to prevent.
4. **Date every item.** Drop anything outside the window. An undated item is not evidence.
5. **Rank by engagement, then read against the ranking.** Engagement shows how loud a view was, not how common it is. Note the dissenting view that drew little response, because it is often the objection the decision will meet.
6. **Synthesise with sources.** State what is consistently said, what is disputed, and what has changed in the window. Every claim links to its item.
7. **Report coverage** alongside the synthesis: the venues read, the venues empty, and the venues never reached, with the reason for each gap.

## Output

- The synthesis, with a source link for each claim.
- The coverage report: each venue in one of the three states, with its window and count of items.
- The dissenting views, noted separately.
- What the sweep cannot support, given the gaps.

## Quality bar

The venue list is fixed before searching. Every venue has one of the three states. Every item is dated and inside the window. The coverage report appears with the synthesis, not after it. Watch for an empty result reported as "no discussion", undated items used as evidence, and a trend called real from one loud thread.

---
name: closed-won-replication-play
version: 1.0.0
status: draft-for-review
description: Use the day a deal closes won to turn the win into pipeline while the story is fresh. Extracts the win profile, finds a fixed number of lookalike companies that are not already in the CRM, identifies the same persona as the winning champion at each, and drafts one outreach message per company from the deal owner, using an anonymised win reference. Nothing is sent without human approval. Not for the general ICP or list build (see prospect-list-building).
sources:
  - "Closed-won replication play (MIT, Ariel Cohen): win profile extraction, lookalike search with exclusion of existing customers and pipeline, persona matching to the champion, anonymised win references, peer tone, soft call to action, batch review before anything sends"
  - "Removed: the CRM-specific automation steps and the task-queue routing, which are platform details rather than method"
  - "Adapted for GTM-360: the default of five lookalikes per win, the broaden-one-criterion-at-a-time rule, and the three to five sentence length are author defaults"
---

# Closed-won replication play

## Purpose

A closed-won deal is evidence of what the company sells well and to whom. Waiting a quarter to use that evidence wastes it, because the team's story about the win is still specific and the buyer profile is still clear. This skill turns each win into a short list of lookalike companies and a set of drafts a human reviews before anything goes out.

## When to use

- A deal has just closed won and the team wants to repeat the win.
- A customer has been won in a segment the team wants more of.

Route elsewhere when:

- The question is the full ICP. Use `icp-builder`.
- The question is a broad list build. Use `prospect-list-building`.
- The question is the existing customer base. Use `expansion-revenue-architect`.

## Inputs

- The closed-won deal: industry, size, geography, go-to-market model, and the use case that drove the purchase.
- The champion's role, which sets the persona to find at each lookalike.
- The deal owner, who is the sender.
- The existing customer list and open pipeline, to exclude.

Fields that are missing are inferred where a reasonable inference exists, and the inference is labelled. Missing fields do not block the run.

## Procedure

1. **Extract the win profile:** vertical, headcount band, geography, relevant tools, go-to-market model, and the pain that drove the purchase. Name the deal owner.
2. **Build a specific search profile.** "B2B SaaS, 50 to 200 employees, United States, sells through outbound, scaling its sales team" works. "Tech companies" does not.
3. **Find exactly five lookalikes** (default). Exclude existing customers, open opportunities, and companies already in the CRM. If the count cannot be reached, broaden one criterion at a time, geography first, then size. If it still cannot be reached, proceed with the number found and flag the shortfall.
4. **Confirm ICP fit** for each lookalike. Being similar on paper is not enough; check that the company looks like one the team would win.
5. **Find the persona that matches the champion** at each company. A winning VP of Sales champion means a VP of Sales at the lookalike, not a generic decision maker.
6. **Note one specific detail** about each company or contact to make the message relevant.
7. **Draft one message per company:**
   - Sender: the deal owner, in their voice.
   - Win reference always anonymised: "we recently helped a company in [profile] do [outcome]". Never name the customer.
   - Peer tone, not a pitch. One specific detail about the prospect.
   - Soft call to action: an offer to share more, not a request for a meeting.
   - Three to five sentences on LinkedIn. Slightly longer by email, but still short.
8. **Do not reveal the mechanism.** The message never says the company was found because of another customer.
9. **Queue for review.** Present the batch to the deal owner, with the profile, the five companies, the persona for each, and the draft. Nothing is sent until the owner approves each message.

## Output

- The win profile, with any inferred fields marked.
- Five lookalikes with the ICP-fit reason, the persona, and the detail used.
- One draft per company, with the channel.
- A note on any shortfall in the count, and why.

## Quality bar

The win reference is anonymised. Each lookalike is net-new and checked for fit. The persona matches the champion's role. No message reveals how the prospect was found. Nothing sends without approval. Watch for named customers in drafts, lookalikes that are existing accounts, and generic personas.

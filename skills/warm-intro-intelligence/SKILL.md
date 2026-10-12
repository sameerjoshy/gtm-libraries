---
name: warm-intro-intelligence
version: 1.0.0
status: draft-for-review
description: "Use when a rep wants warm introduction paths into a target company or a named contact. Identifies the strongest available paths through the company's own network (employees, customers, partners, investors, advisers, and past call notes), labels each path's confidence honestly, and returns the paths for the rep to decide on. Decision support only: never contacts anyone and never writes to the CRM. Not for drafting the ask to the connector (see multi-threading-coach for the routing logic)."
sources:
  - "Warm intro intelligence (MIT, Din Arbel): input resolution (named contact, persona, or company only), persona priority by ICP segment, up to three target contacts, bridge nodes across the company's own network, evidence-based confidence labels, rep decides every step"
  - "Removed: the platform-specific node registry, the customer-list and partner-object identifiers, and the internal roster build instructions. The method is restated as a generic network-mapping procedure"
  - "Adapted for GTM-360: the three-contact limit and the confidence bands are author defaults. Personal relationships are used only as the rep's own knowledge and are never recorded beyond the relevant deal"
---

# Warm intro intelligence

## Purpose

A warm introduction converts far better than a cold approach, but only if the path exists. Most teams do not know who in their own network knows the target. This skill maps the paths from the company's network to a target contact, rates each path honestly, and leaves every decision with the rep.

## When to use

- A rep asks who the company knows at a target account.
- A specific contact needs an introduction.
- A persona needs a route in at a company the team has not reached.

Route elsewhere when:

- The question is how to ask for the introduction. Use `multi-threading-coach`.
- The question is the list of accounts. Use `prospect-list-building`.

## Inputs

- The target: a named contact, a persona or role, or a company only.
- The company's own network sources, as the team keeps them: employee profiles and history, customer and partner records, investor and adviser lists, and past call notes where the team has consent to use them.
- The ICP segment and its persona priorities, when the input is a company only.

## Procedure

1. **Resolve the input.**
   - A named contact: go straight to step 4.
   - A persona or role: find matching contacts at the company (up to three), then go to step 4.
   - A company only: classify its ICP segment from the record, or infer one from public information and label it as inferred. Choose up to three personas for that segment, then find contacts.
2. **Limit to three target contacts.** If no contact exists for a persona, say so in the output. Do not skip it silently.
3. **Map bridges.** For each target, search the network sources for a person connected to the target: a former colleague, a shared employer, a shared investor, a customer relationship, or a partner contact. Record the type of bridge.
4. **Rate each path:**
   - Strong: a direct, recent, two-way relationship with evidence in the records.
   - Moderate: a past or indirect relationship, or a shared affiliation without contact history.
   - Weak: a shared attribute only, such as the same university or a former employer several years ago.
   Each rating cites its evidence. A path with no evidence is not listed.
5. **Order the paths** by strength, then by recency of the relationship.
6. **Stop.** Present the paths. Do not contact anyone, draft an outreach to a connector, or write to the CRM. The rep decides each step.

## Output

For each target contact:

- Name, title, and company, with the ICP persona it matches.
- Ranked paths: the bridge person, the type of connection, the rating, and the evidence.
- A note where no path exists.
- For a company-only input: the segment, marked confirmed or inferred.

## Quality bar

Every rating is backed by a cited record. No path is presented without evidence. Nothing is sent, drafted for a connector, or written to a system. Watch for paths based on shared attributes presented as relationships, personal details used beyond the deal, and more than three targets without a reason.

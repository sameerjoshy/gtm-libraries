---
name: acquired-brand-gtm-integration
version: 1.1.0
description: "Use immediately after acquiring a product or brand, before combining websites, customer records, pipelines, messaging, analytics, or campaigns. Sets the integration boundary from the deal thesis, maps the existing demand system, assigns a brand posture to each customer-facing surface, segments records by relationship and permission before any merge, protects live demand during consolidation, and sequences reversible changes. Not for the deal itself or the legal integration."
---

# Acquired-brand GTM integration

## Purpose

After an acquisition, pressure builds to merge everything at once. Websites are redirected, lists are combined, pipelines are reassigned, and the brand is retired. Each step can break demand that was already working, and some steps cannot be undone without losing customers or consent. This skill slows the integration to the point where the team knows what it has, what it must protect, and what can change safely.

## When to use

- The acquisition has just closed, and the GTM teams are being asked to combine things.
- A brand, product, or customer list has been acquired and its demand system is unknown.
- A consolidation of websites, CRM, or campaigns is proposed without a map.

Route elsewhere when:

- The question is the acquisition price or deal terms. That is outside this library.
- The question is the CRM build itself. Use `crm-migration-consolidation`.
- The question is the data consent position. Route to counsel, and use `revops-data-governance` for the record-level work.

## Inputs

- The acquisition thesis in one sentence: distribution, product expansion, market entry, customer access, talent, or brand equity.
- The domains, websites, forms, booking paths, pricing pages, email programs, partner listings, reviews, and paid campaigns of both businesses.
- The CRM, the marketing database, and the billing system, with their owners.
- Any contract or consent terms that govern how customer and contact data can be used.

## Procedure

1. **Set the boundary.** Name the thesis. Reject any integration activity that does not support it. Record the rejected items, so the reason is clear later.
2. **Inventory the demand system** before changing it: domains, search and direct traffic, forms, account and login paths, communications, pricing, records, attribution, partners, reviews, and campaigns.
3. **Record every asset:** current owner, system of record, audience, business value, the impact if it fails, the basis for holding its data, and the rollback path. "Unknown" is a valid status. "Assumed" is not.
4. **Assign a brand posture to each customer-facing surface:**
   - Retain: the acquired identity carries demand or trust that must be protected.
   - Endorse: keep the identity and state the parent relationship.
   - Absorb: migrate only once journeys, promises, and data rights are preserved at the destination.
   - Retire: remove only after traffic, customers, records, and obligations have verified destinations.
   Posture is set per surface. A product name may stay while billing, legal disclosures, and sales operations change separately.
5. **Segment people before systems.** Split records into: active customers, open opportunities with a named owner, contacts who have opted in to marketing, historical leads without current permission, and non-sales relationships such as suppliers and applicants. Deduplicate within each segment, and keep the source brand, permission status, contract entity, and last meaningful interaction on every record.
6. **Protect live demand.** Trace each high-intent path, including branded search, pricing, contact, sign-up, login, password reset, and demo booking, and confirm it works after each change. Change one path at a time.
7. **Sequence reversible changes.** Start with changes that can be rolled back within a day. Hold irreversible steps, such as retiring a domain or merging a customer record, until the earlier steps have run cleanly for a period the team agrees.
8. **Write the decision record:** what was decided, for which surface, on what evidence, who approved it, and what would reverse it.

## Output

- The integration boundary, with the thesis and the rejected activities.
- The asset register: owner, system, audience, value, failure impact, permission basis, and rollback for each asset.
- The posture for each customer-facing surface.
- The segmented people map, with the permission basis for each segment.
- The staged sequence, with each reversible step marked and each irreversible step gated.
- The decision record.

## Quality bar

Every asset has an owner and a rollback path, or an explicit "unknown". Every customer-facing surface has a posture. No contact is treated as marketable without a permission basis. Live high-intent paths are tested after each change. Watch for a rebrand before the inventory, merged lists with lost permission data, and irreversible steps taken on day one.

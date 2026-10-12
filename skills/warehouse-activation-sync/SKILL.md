---
name: warehouse-activation-sync
version: 1.0.0
status: draft-for-review
description: "Use to move a scored or segmented audience from the data warehouse into the CRM, ad platforms, or sequencing tools without corrupting them. Enforces the order of operations: resolve identity before any write, send only real changes, guard field types, apply suppression and consent before anything reaches a destination, batch to each destination's limits, dry-run with a deletion guard, then reconcile after a live push. Not for designing the data layer (see gtm-data-architecture) or for CRM data quality rules (see revops-data-governance)."
sources:
  - "Reverse ETL activation (MIT, Austin Hay): the procedure of identity resolution with a match-confidence floor, quarantine rather than guessed creates, a change-data-capture diff so only real deltas move, field-level mapping with type guards, suppression and consent gates applied after matching, batching and scheduling per destination, a dry run with a maximum-delete guard, and a reconciliation report after the live sync"
  - "Removed: the named warehouse products, the named CRM, ad platforms and sequencers, and the example model and table names. Destination examples are described by type"
  - "Adapted for GTM-360: every numeric default (match floor, batch size, delete guard, auto-approve limit, cadence) is an author default to calibrate. The rule that the warehouse owns computed traits and the CRM owns rep-owned fields is kept as a hard rule"
---

# Warehouse activation sync

## Purpose

The warehouse holds the scores, tiers and segments the GTM team relies on. Getting them into the tools where work happens is where data quietly damages those tools. A naive job writes half-matched rows, rewrites records that have not changed, exceeds API limits, and sends suppressed contacts into a sequence. This skill sets the order that prevents those failures.

## When to use

- A computed audience needs to reach the CRM, an ad audience, or a sequencer.
- A sync job already exists and the team suspects it overwrites or duplicates records.
- A new destination is being connected to the warehouse.

Route elsewhere when:

- The question is the overall data architecture. Use `gtm-data-architecture`.
- The question is CRM field rules and duplicates. Use `revops-data-governance`.
- The question is which enrichment source to buy. Use `data-enrichment`.

## Inputs

- **Source:** the exact model or table of the audience, and its grain: account, contact, or both.
- **Destinations:** each one's object model, batch limit and rate limit.
- **Sync key:** the stable identifier that links a warehouse row to a destination record, such as a domain, an email address, or a CRM record ID.
- **Field mapping:** which warehouse fields map to which destination fields, and which are read-only in the destination.
- **Suppression and consent lists:** do-not-contact, unsubscribes, and the rules for each region and channel.

If any of these is missing, stop and ask for it.

## Procedure

Run the steps in this order every time.

1. **Resolve identity before writing.** Match each warehouse row to a destination record on the sync key. Apply a match-confidence floor, default 0.90. Rows below it go to a review list and are never guessed into a new record. Where two warehouse rows match one destination record, collapse them by a stated rule, such as most recent or highest score. Never create duplicates.
2. **Compute the change diff.** Compare the resolved audience with the last synced state. Send only new rows, changed fields, and intended removals. Do not send unchanged rows. Unchanged rows waste API budget and clutter the audit trail.
3. **Guard the field types.** Convert dates to the destination's format, map values to allowed picklist options, check number and currency types, and enforce length limits. A row that fails the schema goes to an error list with its reason. Never force-write it.
4. **Apply suppression and consent.** Remove contacts on do-not-contact or unsubscribe lists, contacts failing the region's consent rules, and contacts a channel excludes. Do this after matching, so the log shows exactly who was held and why.
5. **Batch and schedule to each destination's limits.** Chunk writes to the batch size, back off on rate-limit responses, and set a cadence per destination. As defaults: the CRM near real time, ad audiences hourly, and sequences only through an explicit enrolment step.
6. **Dry run first.** Report planned adds, updates, suppressions and errors, with counts and samples. Set a maximum-delete guard, default 10% of the audience. If intended removals exceed it, stop and surface the run. Do not mass-delete after a bad upstream run. Require sign-off above the auto-approve limit, default 500 rows.
7. **Sync live, then reconcile.** Write the changes, record the outcome of each row, and produce a reconciliation: expected against written counts for each object, error rows with reasons, and suppressed rows. Save the new sync state so the next run's diff is correct.

## Ownership rules

- The warehouse is authoritative for computed traits, such as scores, tiers and segments.
- The CRM is authoritative for fields that reps own. A sync never overwrites a rep-owned field.
- A sequencer never enrols contacts automatically from a warehouse sync. A bad upstream filter would become a mass mis-send.

## Output

- The sync plan: the resolved audience, the field map, and each destination's schedule.
- The dry-run diff: adds, updates, suppressions and errors, with counts and samples.
- The reconciliation report, with the saved sync-state pointer.

## Quality bar

Identity is resolved before any write. Unchanged rows are not sent. Suppression runs after matching and is logged. The delete guard is set and tested. Enrolment is a separate, gated step. Watch for a low-quality match floor lowered to hit a volume target, a sync that overwrites rep-owned fields, and an audience pushed live with no dry run.

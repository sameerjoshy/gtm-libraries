---
name: crm-migration-consolidation
version: 1.0.0
description: "Use when two or more CRM instances must be merged, when a company moves to a new CRM, or when a post-merger team has to decide whether to consolidate or run two systems side by side. Covers the consolidate-or-coexist decision, system of record per object, data harmonisation, deduplication and identity resolution, historical data, the ID crosswalk that makes rollback possible, rebuilding automations, re-pointing integrations, cutover and rollback, KPI re-baselining, GDPR carry-over, and the ARR tie-out to finance. Platform-neutral. For Salesforce configuration see revops-salesforce; for the wider post-merger plan see revops-change-management."
---

# CRM migration and consolidation

## Purpose

Moving or merging CRM instances fails mostly for reasons that are not technical: nobody agreed what each object means, nobody owned the decision of which system wins, and the people who use the system were not brought along. The technical work is real, but it is the smaller part. This skill sets out the decisions to make first, then the data and process steps, then the cutover, and the checks that show the result can be trusted.

## When to use

- Two CRM instances are being merged, usually after an acquisition or a reorganisation.
- A company is moving from one CRM to another.
- A post-merger team must decide between consolidating and running two systems.
- Duplicate accounts and contacts are blocking reporting.
- A cutover date is being planned.

Route elsewhere when:

- The question is the Salesforce configuration itself. Use `revops-salesforce`.
- The question is the wider integration plan after an acquisition. Use `revops-change-management`.
- The question is ongoing data governance and master data. Use `revops-data-governance`.
- The question is the handoff design across the revenue process. Use `revenue-handoffs`.
- The question is the tool stack. Use `revops-tech-stack`.

## Inputs

- The inventory of both instances: objects, fields, pipelines, automations, users, and record counts.
- The revenue model for each business: single or multiple go-to-market motions, territories, and pricing.
- The current definitions of the key terms: lead, opportunity stages, ARR, and churn.
- The list of integrations that touch the CRM, and what each one reads and writes.
- Finance records for active ARR, by entity and currency.
- The legal basis, consent records, and data-processing agreements for each instance.
- The team structure, and who will own the migration end to end.

## Procedure

### Step 1: Decide to consolidate or coexist

Start with the business question, not the platform. Consolidation is costly and disruptive. Coexistence is cheaper to start and harder to run over time. The answer comes from the go-to-market model and the definitions of the key numbers.

**Consolidate when:**

- A single go-to-market motion, with one territory model, one pipeline, and one pricing approach, serves both businesses.
- Leadership needs one version of ARR, net retention, and board reporting across all revenue.
- Data flows one way reliably, and the automations can be rebuilt once.
- Both organisations report to one P&L with aligned incentives.

**Coexist when:**

- Each business runs its own sales motion, customers, and forecast, and wants to keep that independence.
- One system is clearly better for its use case, and switching costs more than it saves. For example, one business sells complex enterprise deals and the other sells high-volume small deals.
- The businesses integrate at finance and reporting only, not in daily workflow.
- The organisation accepts the cost of two systems, reconciliation work, and the risk that reporting lags reality.

Coexistence still needs an integration layer. Plan the identity layer (one view of each customer), the finance layer (one ARR figure), and the reporting layer (one KPI set with two sources).

Timelines for full consolidation are often quoted at 12 to 18 months for large organisations. Treat that as a range to test against the client's size and complexity, not a fixed plan.

### Step 2: Set the system of record for each object

Before any data moves, decide which system is the source of truth for each object. This decision drives field mapping, validation, survivorship, and reconciliation. Every object needs one owner and one system. Ambiguity during the merge is what creates data problems after cutover.

| Object | Questions to answer | Typical decision |
|---|---|---|
| Account | Which system has the authoritative hierarchy? Which owns the primary customer ID? Which ID do contracts reference? | Migrate the hierarchy into the target. Generate new IDs. Keep the old IDs in a legacy field for the crosswalk. |
| Contact | Where does the primary contact live? Which system defines the contact-to-account link? Who owns deduplication? | Deduplicate in the source first, then migrate into the target as the system of record. |
| Opportunity | Which system feeds revenue reporting? Which stages drive the forecast? Which system tracks multi-threaded deals? | One system per segment is acceptable if the segments are clearly defined, for example enterprise in one system and small deals in another, with a rule for the boundary. |
| Subscription and ARR | Which system holds active subscriptions? Where do renewals start? Where is churn recorded? | Usually the billing or contract system is the source for subscription status. The CRM reflects current state only. |
| Activity | Which system logs emails, calls, and notes? Which is authoritative? Which is archived? | Archive the old history read-only. Sync activity to the target from cutover onward. |

Write each decision down with its reason, and get it signed off by the revenue leader and finance.

### Step 3: Harmonise the data models

This is where most of the effort sits. Before migrating anything, agree the target model and map both sources into it.

- **Object model.** Some CRMs use a single contact-first model, and others split leads from contacts and accounts. Choose the target model, then map both sources into it.
- **Stage and picklist values.** Two instances often describe the same stage in different words, such as "Negotiation", "In negotiation", and "In contract". Agree the canonical list, then build the mapping table before any transformation.
- **Property types and formats.** One system may store phone numbers as free text, and another as a restricted format. Choose the target format, and transform the source data to match.
- **Dependent fields.** Fields that only appear when another field has a certain value need their logic designed once for the target.
- **Currency.** Decide whether all ARR is held in one reporting currency with conversion at a stated rate, or whether each deal keeps its original currency. Finance must be able to reconcile whichever is chosen.
- **Definitions.** A term such as "marketing qualified lead" must mean the same thing in both organisations, or the adoption problem comes back after cutover. See `lead-routing-design` and `marketing-operations` for the definitions.

Common mistakes:

- Planning to clean the data after cutover. Post-cutover clean-up is usually more expensive than the same work done before it. Clean the source first.
- Keeping every field because someone might use it. Consolidation is the moment to remove custom fields nobody reads. Audit each one, and retire the unused ones.
- Migrating raw data with its problems intact, such as email typos, phone numbers without country codes, and company names with stray spaces. Standardise the source data, not just the target schema.

### Step 4: Deduplicate and resolve identity

Duplicates are the most common cause of broken pipelines and reporting after a merge. Treat deduplication as its own workstream, with its own owner and its own timeline.

**Match keys.** Use deterministic keys first:

- Contacts: email address is the strongest key, since it persists across job changes better than a name. Phone is a secondary key.
- Accounts: web domain is the most reliable key. Legal name plus country is the secondary key.
- Deals: a deal has no reliable deterministic key. Match on name, creation date, and amount together, and expect manual review.

**Fuzzy matching.** Exact matching misses variants: "Acme Corp" and "Acme Inc.", or "Sarah Jones" and "S. Jones", and an old employee alias with a former domain. Add fuzzy matching for names, then review the borderline cases by hand. Do not set a match threshold without testing it on a sample and checking the false positives.

**Survivorship rules.** When two records match, decide which values win:

- Most recently modified, when the freshness of the value matters.
- Most complete, when the record with more populated fields is the better base.
- Authoritative source, when one system is known to hold verified data for that field.

Write the rules per field. Example: "On an email match, use the record from the target system as the base. Take the phone number from whichever source has one. Take the company from the target if populated, otherwise from the source."

**Account hierarchies.** Parent and subsidiary structures often differ between instances. Export both hierarchies, agree the canonical one with the business, and write a reconciliation document before cutover. Decide whether to keep both hierarchies as separate associations or collapse them into one.

**Keep deduplication running.** Contacts change jobs and details go stale over time. A one-off deduplication will not hold, so plan a recurring match run after cutover.

**Planning estimates.** Deduplication effort depends heavily on the data. Estimate it from a sample: run the match rules on one thousand records, measure the share that needs manual review, and scale from there. Do not use a published duplicate rate as the planning figure.

### Step 5: Choose the history strategy

Emails, calls, notes, and engagement history rarely migrate cleanly. Rate limits, schema differences, and attachments create gaps that are hard to see and hard to fix after cutover. Decide the approach for each history type:

- **Full migration.** Use when the full customer journey must be visible, and the volume is manageable. Expect rate limits on large imports, so throttle the import and have a retry plan. Check that any links to call recordings still work after the move.
- **Partial migration.** Migrate the recent period, such as the last 18 to 24 months, and archive the rest. This reduces effort and clutter, while keeping older history available for audit.
- **Archive read-only.** Keep the old system available for lookups, with syncs turned off and write access removed. Plan a short overlap period, since users will ask why an old deal is missing and need a way to find it.

Email threading usually depends on the mail sync. Reconnect mail sync in the target system from cutover, and do not expect the old threads to rebuild themselves.

### Step 6: Build the ID crosswalk

Before cutover, create a mapping of every migrated record's old ID to its new ID, for contacts, accounts, opportunities, and subscriptions. Keep it permanently.

The crosswalk enables three things: rollback, reconstruction of the audit trail, and repair of integrations that still send the old IDs. Without it, an incident after cutover becomes a manual search.

Test the associations end to end in a sandbox before cutover. Check that each contact links to its account, each deal to its contacts and account, and each subscription to its customer. A broken link breaks the pipeline and the reports built on it.

### Step 7: Rebuild the automations

Automations do not transfer between systems. Each one has to be documented, rebuilt, and tested in the target. This is often the largest hidden effort, and it is easy to underestimate.

- **Inventory.** Document every live automation in the source: purpose, trigger, actions, and frequency.
- **Prioritise.** Rebuild lead routing and scoring first, because they drive adoption. Rebuild nurture and renewal logic second.
- **Test.** Build and test in a sandbox with sample data. Run the old and new logic side by side for a period, and compare their outputs. If routing gives different owners, find out why before cutover.
- **Retire.** Turn off old automations only after the new ones have run stably, for one to two weeks.

Do not try to export workflows from one system and import them into another. Trigger logic and field references are platform-specific, and third-party integrations must be authenticated again.

### Step 8: Audit and re-point the integrations

Every system that touches the CRM must be listed and re-pointed to the target. Sales engagement tools, billing, enrichment, intent data, BI tools, finance connectors, email sync, chat bots, and in-house apps all count.

For each integration, record:

- Does it create records in the CRM? For example, an intent data feed may create leads.
- Does it update existing records?
- Does it read from the CRM?
- Which fields does it use?
- Where does it run after the merge: in both systems, in one, or in neither?

**High-risk patterns:**

- An integration that writes to both systems during transition creates duplicates. Pause it during cutover, and resume only after duplicates are checked.
- An integration that creates records automatically must be paused before cutover, or it creates them in both systems.
- A finance sync that writes subscription status must point to one system only. Writing to both creates accounting mismatches.

### Step 9: Plan the cutover sequence

1. **One week before.** Pause every integration that writes. Freeze the source for new data entry, and allow read-only access.
2. **Cutover day.** Migrate the master data: accounts, contacts, and opportunities. Run deduplication. Create the crosswalk. Reconcile record counts.
3. **First hour after.** Re-point the integrations one at a time. Test each one before moving to the next.
4. **Hours two to four.** Resume the writing integrations, and monitor for duplicates and mismatches.
5. **Days one and two (hypercare).** Watch for sync failures, missing data, and orphaned records. Keep the rollback plan ready.
6. **Weeks one and two.** Run daily reconciliation: record counts, key metrics, and a sample check of the data.

Plan for a cutover window of one to three days at minimum. A short window with an unresolved problem is worse than a longer one with the problem fixed.

### Step 10: Prepare the rollback plan

A rollback must be possible if the cutover goes badly, such as major data corruption, a failed integration, or a user revolt. The crosswalk makes it possible.

The rollback has three parts: point the integrations back to the source, re-enable the source automations, and tell users which system to use.

Set the target for a rollback to complete within a working day, and test it in the sandbox. If the rollback would take days, the cutover is effectively irreversible, and the risk has to be accepted explicitly by leadership before the cutover.

### Step 11: Bridge the reporting and re-baseline the KPIs

Consolidation changes the numbers. Deduplication lowers contact counts. Stage redefinitions change pipeline value and conversion. Backdated activity changes cycle times. If nobody expects this, the first reaction is alarm.

Before cutover:

1. Rebuild the critical dashboards in the target system, covering pipeline, forecast, win rate, and velocity. Test them on sandbox data.
2. Agree in writing how each metric will shift, and why. Example: "Contact count will fall because duplicates are removed. ARR should be unchanged, since both systems tracked the same deals."
3. Share the impact summary with sales leadership, finance, and the board before cutover.

After cutover, show the old and new dashboards side by side for a set period, with a note that the new numbers reflect deduplicated data. Freeze the metric definitions after the stabilisation period, and archive the old dashboards.

### Step 12: Carry the GDPR obligations across

Consolidation does not remove the obligations attached to the data. Check these before migrating personal data:

- **Opt-outs.** Every marketing opt-out in the source must be carried over as a suppression, and tested in the target. Export the opt-outs, import them, and check that no marketing goes to those contacts.
- **Lawful basis.** Each contact should have a recorded basis for processing, such as consent, contract, or legitimate interest. Carry the basis across. Where it is missing, flag the record for legal review before migrating it.
- **Evidence of consent.** Where consent is the basis, the organisation must be able to demonstrate it. Carry the consent source and date with the record. Consent that cannot be shown is a compliance gap.
- **Notice for enriched data.** Where contact data was enriched from a third party, the notice obligations under GDPR Article 14 may apply. Decide before cutover whether to notify the contacts, or to leave the enriched fields out of the migration. Confirm the timing with counsel.
- **Objections.** An objection to direct marketing must stop that processing immediately. Import each objection as a suppression, and check that the target respects it.
- **Transfers and retention.** Where data moves to a system in another jurisdiction, document the transfer mechanism. Set one retention period for the merged data, and record it. Confirm the data-processing agreements for both systems cover the merged flow.

These are points for counsel to confirm, not legal advice.

### Step 13: Tie out ARR to finance

Before cutover, reconcile active ARR in the source systems to the finance records:

1. Export all active ARR by entity and currency from each source.
2. Remove duplicates and sum.
3. Compare the total with the invoicing or general ledger figures.
4. Investigate each gap. Common causes are duplicated deals in both systems, deals signed but not yet invoiced, and subscriptions in finance that appear in neither CRM.

Resolve the gap before migrating. Repeat the tie-out within 48 hours after cutover. ARR is board-facing, so any mismatch needs to be explained at once.

For multi-entity organisations, also agree the entity mapping for each deal, and how intercompany deals are recorded.

### Step 14: Run adoption as a workstream

Users from two organisations arrive with two sets of habits. If the merged system adds friction, adoption falls and data quality follows.

| Phase | Timing | Actions | Owner |
|---|---|---|---|
| Awareness | Eight weeks before cutover | Explain why the change is happening, and what it means for each team | Leadership and RevOps |
| Design | Six weeks before | Involve reps in the workflow, the picklist mapping, and the dashboard layout | RevOps and sales champions |
| Training | Four weeks before | Role-based training for each job, with a sandbox to practise in | RevOps and sales enablement |
| Pilot | Two weeks before | Two or three teams work in the new system alongside the old, and issues are fixed | Pilot teams and RevOps |
| Cutover | Day zero | Everyone moves over. Source read-only, except for lookups | RevOps and IT |
| Hypercare | Weeks one and two | Daily check-ins with sales leaders. Broken workflows fixed the same day | RevOps and team leads |
| Reinforcement | Weeks three to eight | Short refreshers on specific features, recognition for good data habits | Sales enablement and leadership |
| Normalisation | Months two to three | The merged system is the only one in use. The source is archived or closed | RevOps |

Track these after cutover: login frequency, activity logging per rep, field completion, forecast-entry accuracy, and support tickets. If any measure stays low for two weeks or more, take action. Options include more training, redesigning the workflow, or considering a rollback.

Training works best when it covers each person's own workflow, not the whole system.

### Step 15: Sequence the work

Work through these in order. Each step depends on the one before.

1. Audit both instances: objects, fields, pipelines, automations, integrations, users, and data volumes.
2. Define the target: consolidate or coexist, system of record per object, object model, and KPI definitions.
3. Clean the source data: deduplicate and standardise both instances.
4. Map the fields: document every source field, agree the target name and type, and write each transformation rule.
5. Build the target in a sandbox: properties, pipelines, stages, automations, and integrations.
6. Test-migrate a representative sample, for example a few thousand accounts and contacts and a few hundred opportunities. Check counts, associations, and a sample of records. Iterate on the mapping until the sample is right.
7. Plan the cutover: the window, the freeze, the parallel run, and the rollback.
8. Run the cutover: migrate, deduplicate, create the crosswalk, reconcile, and re-point the integrations.
9. Run hypercare for two weeks.
10. Normalise and retire the source. Start the recurring data-quality cadence.

Planning range for the whole sequence: a few months for a small instance, and longer for a large or multi-entity one. Validate the range against the client's own audit.

## Output

- The consolidate-or-coexist decision, with its reason and sign-off.
- The system of record for each object, signed by the revenue leader and finance.
- The harmonised data model: stage mapping, field mapping, formats, currency rule, and definitions.
- The deduplication plan: match keys, fuzzy-match thresholds tested on a sample, survivorship rules, and the hierarchy reconciliation.
- The history strategy for each history type.
- The ID crosswalk and the association test results.
- The automation inventory, with the rebuild and parallel-run plan.
- The integration register, with the cutover sequence for each one.
- The rollback plan, with the time it takes to execute.
- The reporting bridge and the KPI re-baseline summary.
- The GDPR checklist, flagged for counsel where needed.
- The ARR tie-out, before and after cutover.
- The adoption plan and the post-cutover measures.

## Anti-patterns

| Anti-pattern | Symptom | Fix |
|---|---|---|
| Consolidating without a decision | Two systems keep running, and nobody owns either | Make the consolidate-or-coexist decision in writing, first |
| No owner per object | Duplicate records appear in two systems after cutover | One system of record per object |
| Migrating dirty data | Duplicates and bad formats show up in the new system | Clean the source before the move |
| Exporting workflows | Automations fail or behave differently in the target | Rebuild and test each automation |
| Integrations writing during cutover | Duplicates or mismatched records | Pause writing integrations, then re-point one by one |
| No crosswalk | Rollback impossible, and integration failures hard to trace | Keep the old-to-new ID mapping permanently |
| Unexplained metric shifts | Leadership alarmed by a lower pipeline or contact count | Pre-announce the expected shifts, with the reason |
| ARR not reconciled | A board-level number changes after cutover | Tie out to finance before and after |
| Unprepared users | Reps keep the old system open and enter data in both | Training, a pilot, and a read-only source with a clear end date |

## Quality bar

Each object has one owner and one system. The migration decision is written down, with its reason. Every record can be traced from old ID to new ID. Automations are rebuilt and tested, not exported. Integrations have a register entry and a cutover step. ARR ties to finance before and after cutover, and any metric shift is explained in advance. Watch for consolidation with no decision, two systems writing the same object, unreconciled ARR, and adoption assumed rather than measured.

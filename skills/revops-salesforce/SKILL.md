---
name: revops-salesforce
version: 1.1.0
description: "Use to design, audit, or fix a Salesforce org for revenue operations: the object model and record types, field governance, automation architecture (one entry point per object, Flow over legacy tools), the opportunity stage model with forecast categories and validation rules, forecasting setup, territory and assignment design, dashboards by audience, data quality with duplicate rules, integrations with a system of record for each object, and change control across sandboxes. Salesforce-specific. Not for the method of forecasting (see revops-forecasting), the CRM-neutral strategy (see revenue-metrics and revenue-operating-cadence), or migrating between CRMs (see crm-migration-consolidation)."
---

# Salesforce for revenue operations

## Purpose

A Salesforce org is only as useful as its object model, its automation, and the data entered into it. Most orgs fail in the same few places: a stage model no one agrees on, automation stacked on the same object by different people, validation that either does not exist or blocks everything, and dashboards that disagree with each other.

This skill covers how to design and audit the org so that the pipeline, forecast, and reporting can be trusted. It is specific to Salesforce. The method behind the forecast and the metrics sits in other skills, and this one tells you where each thing lives in the org.

## When to use

- A new Salesforce org is being designed for a revenue team.
- The org has grown by accretion, and nobody can say which automation is live.
- Forecast numbers differ between the CRM and the finance view.
- Reps skip stages or leave amounts blank, and validation has not been set up.
- Legacy automation is still running and needs migrating.
- A team is adding a second pipeline, a territory model, or team selling with splits.

Route elsewhere when:

- The question is the forecast method, accuracy, or variance. Use `revops-forecasting`.
- The question is the revenue metrics. Use `revenue-metrics`.
- The question is the meeting rhythm. Use `revenue-operating-cadence`.
- The question is the stage evidence standard. Use `deal-qualification-gates`.
- The question is moving data from another CRM, or consolidating two instances. Use `crm-migration-consolidation`.
- The question is lead routing rules. Use `lead-routing-design`, then implement it here.
- The question is the data governance policy. Use `revops-data-governance`.

## Inputs

- Org details: the edition, the number of users and licenses, and the sandboxes available.
- A list of objects in use, with custom fields, record types, and page layouts.
- Every active automation: flows, legacy Process Builders and Workflow Rules, Apex triggers, and scheduled jobs.
- Validation rules, duplicate and matching rules, and assignment rules.
- The stage model, forecast setup, and role hierarchy.
- Dashboards and reports in use, and who reads them.
- Integrations and the connected users, with what each one reads and writes.

## Procedure

### Step 1: Audit the org before changing it

Pull an inventory and answer these questions:

- How many active custom fields are on Account, Opportunity, and Lead? Above about 500 on one object is a warning sign, not a rule.
- How many flows, Apex triggers, and legacy automations write to each object? More than one entry point per object is a risk.
- Which fields are empty on more than 80% of live records? These are candidates for removal.
- Which validation rules are active, and do they block anything that matters?
- How many open opportunities have no owner, no close date, no next step, or no amount?

Record the findings. Do not rebuild anything until the audit is agreed, since fixing an unknown automation tends to break a live one.

### Step 2: Decide the object model

Four decisions shape the org.

**Lead-first or contact-and-account-first.** Salesforce separates leads from contacts and accounts. Conversion creates an account, a contact, and an opportunity. Choose one approach and apply it everywhere:

- Lead-first: all inbound and outbound starts as a lead. Use it when sales development qualifies large volumes before an account exists.
- Contact-and-account-first: records go straight to accounts and contacts. Use it when most pipeline comes from existing accounts or partners.

Mixing the two creates duplicates. This is the most consequential choice in the org.

**Record types on opportunities.** Use record types to separate motions, such as new business, renewal, and expansion. Each record type can have its own stage set and page layout. Do not create a record type for every product, since that multiplies the configuration.

**Custom objects.** Add a custom object only when a record needs its own lifecycle or several values per parent. Common cases are a subscription record, a handoff record for the sales-to-customer-success handover, a health score history, and a forecast snapshot. Do not use a custom object where a field would do.

**Relationships.** Use a lookup for loose links. Use a master-detail relationship only when the child should be deleted with its parent and should roll up to it. For many-to-many links, use a junction object. The buying group on an opportunity is held in the standard contact roles on the opportunity, which record each contact's role.

### Step 3: Govern the fields

- **Naming.** Use one convention for custom fields, such as category, name, and a suffix for custom fields. Example: a field that records the date a lead became marketing-qualified should follow the same pattern as every other milestone date, not mql_dt in one place and MQL_Date in another.
- **Required fields.** Require fields only where a later process depends on them. Each required field must have an owner who can answer for its quality.
- **Field history.** Turn on field history for the fields that drive forecast and reporting: stage, amount, close date, and forecast category. Without it, you cannot audit a forecast change.
- **Retirement.** Review unused fields each quarter, and remove or hide those that no report or flow reads.
- **Page layouts.** Design layouts by role, with the fields each role needs first. A layout with more than about 50 fields on one screen is usually a sign that nobody has decided what matters.

### Step 4: Consolidate the automation

This is where orgs most often break.

- **One entry point per object.** Choose one mechanism per object for record-triggered logic, either flows or Apex triggers, and document it. Two mechanisms firing on the same change produce unpredictable results.
- **Flows, not legacy tools.** Build new logic in flows. Migrate existing Process Builders and Workflow Rules to flows, then deactivate the legacy versions after the flows have run in parallel for long enough to compare outputs. Check Salesforce's current documentation for the support status of legacy tools in your edition. Do not rely on a date recorded here.
- **Consolidate flows.** Keep the number of record-triggered flows per object small, such as one before-save, one after-save, and one before-delete. Split logic by purpose inside a flow, not by creating a new flow for each rule.
- **Naming.** Use a consistent flow name pattern: object, trigger, purpose, and version. Example: `Opportunity_AfterSave_ClosedWon_Handoff_v2`.
- **Switches.** Put on-off toggles for each automation in custom metadata, so a flow can be disabled without a redeployment during an incident.
- **Apex or flow.** Use flows by default. Use Apex when a process handles very large data volumes, needs complex error handling, or must respond within a sub-second window. Keep the boundary written down.

### Step 5: Set up the opportunity pipeline

**Stages.** Use five to eight stages, each with an exit criterion that a rep can check against the record. Stage names should describe what the buyer has done, not what the rep plans to do. For example, "Economic buyer has confirmed budget" is an exit criterion. "Negotiating" is not. Link the stage exit criteria to the evidence standard in `deal-qualification-gates`.

**Forecast categories.** Map each stage to a forecast category, such as Pipeline, Best Case, Commit, Closed, and Omitted, as configured in the org. Write the rule for when a deal can move into Commit. The rule should depend on evidence, not the rep's feeling.

**Validation rules.** Layer validation from the field level, to the record level, to the flow level, and keep each rule short. Set up these checks:

- No stage skipping: a deal cannot jump from early stage to closed without passing the required stages.
- Amount is required before the proposal stage.
- Close date is required for any open opportunity.
- A loss reason is required when a deal is closed lost.
- A next step with a date is required for any open opportunity past discovery.

Test each rule in a sandbox with a rep profile, not an administrator profile, since administrators often bypass validation.

**Multiple pipelines.** Use record types when two motions genuinely differ, such as enterprise and mid-market. Do not create pipelines for regions unless the stages really differ.

**Opportunity splits.** Turn on splits only when more than one person is credited on the same deal, and define the split types. Splits affect forecast roll-ups, so decide the split rule before enabling them.

### Step 6: Configure forecasting

- **Forecast type.** Use opportunity amount for most teams. Add product or product family forecasting only if the team sells in a way that needs it.
- **Hierarchy.** Align the forecast hierarchy with the role hierarchy, so each manager's roll-up matches their team.
- **Manager adjustments.** Decide who can adjust a rep's forecast, and record each adjustment. An adjustment without a reason is a sign of forecast negotiation.
- **Period.** Monthly or quarterly, matched to how the finance team reports.
- **Snapshots.** Standard forecast history can be too coarse for accuracy work. If you need a weekly snapshot of each rep's forecast, build a snapshot object that records the category, amount, and date each week. Keep the snapshot as the record used to measure accuracy.

For the method of measuring accuracy and variance, use `revops-forecasting`.

### Step 7: Design territories and assignment

- **Territories.** If the edition supports enterprise territory management, use it for hierarchical territories and multi-assignment. If not, use assignment rules and flows that route on account attributes such as region, size, and industry.
- **Account hierarchy.** Set the parent and child structure before reps are assigned. A reassignment after a hierarchy change is painful.
- **Assignment rules for leads.** Implement the routing logic from `lead-routing-design` using assignment rules and queues. Document the rule order, and check it with test records.
- **Reassignment.** Record each reassignment and its reason, so that credit disputes can be settled from the record.

### Step 8: Build dashboards by audience

Build three dashboards, each owned and reviewed by a named person:

- **Executive (weekly, CRO and VP).** Pipeline by forecast category. Coverage against the remaining target, using the method in `revops-forecasting`. Win rate on a rolling three-month basis. Forecast against actual for the current and two prior periods. The top ten deals with stage and next step.
- **Manager (daily, front-line).** Team pipeline by rep and stage. Deals that advanced and deals that stalled this week. Stale deals with no activity in a set window. Speed-to-lead against the agreed service level. Forecast accuracy by rep.
- **RevOps operational (weekly).** Field completion for the fields that matter. Conversion between stages. Time in stage. Loss reasons. Pipeline created against target.

Use report folders with access rules, so that a rep sees only the records they are allowed to see. Put a date stamp and a definition on every dashboard. Dashboards with no owner and no definitions are the usual source of conflicting numbers.

### Step 9: Protect data quality

- **Duplicate and matching rules.** Set matching rules on accounts, contacts, and leads, and duplicate rules that warn or block. Test them against a sample of real records before enforcing them.
- **Enrichment.** Write enrichment results to fields with provenance, following `data-enrichment`. Do not let an enrichment job overwrite a value that a rep entered by hand without a rule.
- **Bulk changes.** Run bulk updates from a tested file, with a backup of the old values, and log the job.
- **Monitoring.** Track field completion and duplicate counts each month, and report them in the RevOps dashboard.

### Step 10: Set up integrations with one system of record per object

For each integration, write down:

- The object it reads and the object it writes.
- Which system is the system of record for each field it touches.
- Which user the integration runs as, and that user's permissions.
- How it handles failures, and who is alerted.

Common patterns:

| Integration | Direction | System of record |
|---|---|---|
| Marketing automation | Two-way for campaign and lifecycle data | Salesforce for revenue, marketing platform for engagement |
| Enrichment provider | Inbound to Salesforce | Enrichment provider for the enriched fields only |
| Sales engagement tool | Two-way for activities | Salesforce for activity history |
| Quoting or CPQ | Two-way | Salesforce for opportunity values, quoting system for pricing |
| Customer success platform | Two-way | Depends on the client's maturity. Decide and write it down |
| Slack or similar | Outbound notifications only | Salesforce |

Rule: no two systems write the same field. If they must, one is the owner, and the other reads only.

Check the API limits for the org before adding an integration that polls or writes in bulk.

### Step 11: Control change

- **Environments.** Build in a sandbox, test with the rep profile, and deploy to production only after the test passes.
- **Deployment.** Use a tracked deployment method, such as change sets or a source-controlled deployment tool, so every change is recorded.
- **Permissions.** Use permission sets for access, and keep profiles minimal. Changes to access are a common source of data leaks and broken reports.
- **Release notes.** Each release lists what changed, why, who approved it, and how to roll it back.

### Step 12: Treat AI features as pilots

Salesforce offers AI features for scoring, summaries, and next-step suggestions. Before relying on any of them:

- Check the license and edition, since many AI features are sold separately.
- Pilot on the client's own data, with the team's current forecast as the comparison, for a fixed period.
- Measure whether the feature improves the forecast or saves time, and compare the result with the team's own baseline.
- Keep a human decision on any customer-visible action. AI scoring that drives material decisions about accounts may need human review under data protection rules, including GDPR Article 22 in Europe. Confirm with counsel.

Vendor claims about AI accuracy or pipeline improvement are not evidence for this client.

## Output

- The object model decisions, with the reason for each: lead model, record types, custom objects, and relationships.
- The field governance rules, with owners.
- The automation inventory, the single entry point per object, and the plan for migrating legacy tools.
- The stage model with exit criteria, the forecast category mapping, and the validation rules.
- The forecasting configuration and the snapshot design.
- The territory and assignment design.
- The dashboard set, with owners and review cadence.
- The integration register, with the system of record for each object.
- The change process: environments, deployment, and permissions.

## Anti-patterns

| Anti-pattern | Symptom | Fix |
|---|---|---|
| Too many custom fields | Hundreds of fields on account or opportunity, most empty | Audit each quarter, and remove the unused ones |
| Inconsistent naming | The same concept under three field names | One naming convention, applied to new fields and renamed where practical |
| Two automation mechanisms on one object | Changes trigger logic twice, or in the wrong order | One entry point per object, documented |
| Legacy automation still live | Old rules fire alongside new flows | Migrate to flows, run in parallel, then deactivate |
| Validation missing or too broad | Stages skipped, or reps blocked from saving | Layered rules, tested as a rep profile |
| Manual territory assignment | Accounts assigned from a spreadsheet | Territory model, or assignment flows |
| No forecast snapshots | Forecast accuracy cannot be measured | Snapshot object, written weekly |
| Overloaded page layouts | Fifty-plus fields on one screen | Role-based layouts |
| Dashboards with no owner | Two dashboards show two different pipeline numbers | Named owner, definitions on the page, one source for each number |
| Integrations that both write one field | Values flip between two systems | One system of record per field |

## Quality bar

Each object has one entry point for automation, and each field has an owner. The stage model has exit criteria a rep can check against the record. Validation is tested as a rep, not as an administrator. Dashboards carry their definitions and owners, and each number has one source. Every integration has a register entry naming the system of record. Watch for legacy automation still running, forecast categories set by feel, and integrations that write to the same field from two places.

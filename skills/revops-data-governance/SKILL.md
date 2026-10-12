---
name: revops-data-governance
version: 1.2.0
description: "Use when CRM data is unreliable, reports do not match across teams, fields have no owners, duplicates or integration drift are causing routing or forecast errors, or a bulk cleanup is being considered. Covers the system of record and data dictionary, measurable health scoring, reviewable and approved cleanup, enrichment rules, field and definition governance, and controls that stop defects returning. Not a CRM configuration guide, and not a forecast (see `revops-forecasting`)."
---

# RevOps data governance

## Purpose

Makes CRM data trustworthy enough to report on, route from, and forecast with. Give the team one documented system of record for each data point, one set of definitions, a health score that can be reproduced, and a cleanup that can be reviewed, reversed, and verified. Prevention comes first, then detection, then correction.

## When to use

- CRM data is too untrustworthy to report on, route from or forecast with, and needs measuring, cleaning under review and preventing from recurring.
- Owners, definitions or systems of record for key data points are unclear.

Route elsewhere when:
- The question is the forecast method. Use `revops-forecasting`.
- The question is the team's wider operating model. Use `revops-strategy`.

## Inputs

1. The CRM objects in scope, their field definitions, owners, pipeline stages, and automation rules. Snapshot them with the extraction time and record counts.
2. Reports or decisions that are failing, and who is affected. Examples: routing errors, forecast mismatch, duplicate outreach.
3. Existing definitions for lead, opportunity, pipeline, customer, and ARR, if any.
4. Integrations and sync directions currently in use.
5. Enrichment vendors in use and their contract scope.
6. Named owners for each object and each rule. If none exist, that gap is the first finding.

## Procedure

### Principles

- **Define before measuring, measure before cleaning.** A cleanup without a baseline cannot show it worked.
- **Measure only what drives decisions.** Do not reward filling optional fields because they are easy to count.
- **Unknown is not passing.** An unevaluable rule is reported as unknown. It is never scored as a pass.
- **Never invent values.** Missing data stays missing or goes to a human. Uncertainty is exposed, not converted into a correction.
- **No changes without named approval.** Approve specific operations, not a summary. Merges, deletions, ownership decisions, and bulk changes always need explicit approval.
- **Stale operations stop.** If a value changed after planning, that operation stops rather than overwrites newer work.
- **Score rules are versioned.** A changed rule rebases the baseline. It is never shown as an improvement or a decline.
- **Prevention beats correction.** Find the entry point of each recurring defect and control it there.

### Step 1: Set the system of record and data model

For each data point, name one system that owns it and say who may change it. Others read it.

Typical examples, to be confirmed with the client:
- Account name: CRM is authoritative.
- Annual revenue: enrichment feeds the CRM; manual edits are not allowed.
- Sales stage: only the sales team changes it.
- Subscription dates: the finance system is authoritative; the CRM displays them.

Where two systems could both write a field and no owner is named, a conflict is certain. Define the owner first.

Document the data model against the customer journey: leads and contacts early, accounts and hierarchy at the organization level, opportunities and line items in the middle, subscriptions and health after the sale. Document any relationship that is missing, such as contact to account to opportunity to revenue, because missing links become reporting gaps.

Keep a data dictionary: each object, property, type, owner, source, required stages, and deprecated fields. If a field is not in the dictionary, it is not an approved field.

### Step 2: Define health as versioned rules

Turn "clean CRM" into explicit rules across identity (duplicates), ownership, completeness of fields that drive execution, pipeline integrity (stage conformance, overdue close dates, stuck deals), and integration drift. Each rule declares:
- population (eligible records)
- condition (what passes)
- severity and impact weight from 1 to 5
- evidence source
- exclusions
- owner

Scoring method:
- Rule pass rate = 1 minus failures divided by eligible records. Exclude unknowns from the denominator, report the unknown rate, and mark the rule low confidence if unknowns exceed 10%.
- Object score = impact-weighted mean of its rule pass rates, times 100.
- Composite score weights objects by business relevance, not record count. A starting model is accounts 30%, contacts 25%, opportunities 35%, activities 10%. These weights are a starting point, not a standard.
- Do not publish an object score with fewer than 30 eligible records without a small-sample warning.
- Critical-rule floors are set separately from the composite. Starting floors: suppression conflicts 100% pass, active ownership at least 99%, and zero tolerated unresolved duplicate accounts tied to open opportunities. A high composite never hides a failing critical rule.

Optional five-dimension view for leadership, labeled as practice-based targets: completeness of required fields (95% or more), accuracy from sampled audits (90% or more), consistency across linked records (99% or more), timeliness (85% or more), and uniqueness (99% or more). If any dimension is below 85%, fix completeness and consistency first.

Version the rule set, weights, populations, and thresholds together. When any changes, recalculate the prior snapshot under the new version if possible, and label the rebaseline.

### Step 3: Deduplicate before anything else

Dedupe before enrichment, because enrichment on duplicates multiplies the errors.
- Exact match, high confidence: same email, same phone, same account domain and size.
- Fuzzy match, review required: name variants such as "Acme Corp", "ACME CORPORATION", and "Acme". Never merge on names alone.
- Vendor-flagged duplicates: check, but do not merge automatically.

Merge rules:
- Contact merge: the surviving record is the most complete with the most recent activity. Keep all activities and relationships. Keep an audit trail of what was deleted, when, and by whom.
- Account merge: usually the older record survives. Move all contacts, opportunities, and subscriptions. Never merge a parent into a subsidiary. Hierarchy is parent for the legal entity and child for divisions or subsidiaries. On acquisitions, create a parent relationship rather than deleting.

Prevent duplicates at creation: check on email for contacts, and fuzzy name and country for accounts, showing matches before a new record is saved. Log any override.

### Step 4: Audit and build a change plan

Snapshot before proposing changes. Define each audit check as an explicit rule (population, condition, severity, evidence). Cover duplicates, ownership gaps, stale pipeline, critical-field completeness, stage conformance, and integration drift.

Count findings by object, rule, owner, source, and age. Separate isolated bad records from systematic failures caused by imports, forms, integrations, or team behavior. Systematic failures get a source control, not a record-by-record fix.

Represent every proposed change as one reviewable operation:
- record type and stable identifier
- field being changed
- current value and proposed value
- rule and evidence
- confidence, reversibility, and impact radius
- whether a human decision is required

Separate deterministic corrections from judgment calls. Missing owners, unclear duplicate survivors, disputed lifecycle stages, and inferred values always require a named human decision.

Prioritize in this order:
1. Changes that stop ongoing corruption.
2. Changes that restore routing or ownership.
3. Changes that correct live pipeline decisions.
4. Cosmetic completeness.

Keep the first batch small enough that a reviewer can inspect examples from every rule and reverse the batch without rebuilding the cleanup.

### Step 5: Review, apply, and verify

1. Present the baseline and the expected effect before asking for approval.
2. Sample at least five operations per rule, or every operation if the batch has fewer than five. Include edge cases, not only obvious successes.
3. Require approval by operation identifier. Approval of a summary does not cover records no one has seen.
4. Re-read each target record immediately before changing it. If the current value differs from the plan, stop that operation as stale. Do not overwrite.
5. Apply approved operations only. Log the before value, after value, approver, time, and outcome.
6. Re-run the same audit rules. Reconcile planned, applied, skipped, failed, and newly detected counts. The batch is not complete until the reconciliation balances.

A reviewer must be able to reject one operation without rejecting the batch.

### Step 6: Enrichment governance

Enrichment fills gaps and refreshes data. It does not override authoritative data without a rule.

Governance modes per field:
- **Auto-overwrite:** only for data that does not change (founding year, domain).
- **Fill empty only:** where manual entry is authoritative.
- **Suggest for review:** where the new value could conflict, such as company size or job title. This is the default.

Refresh cadence: at creation, at stage transitions for targeted enrichment, quarterly for active accounts, and on trigger events.

Vendor assessment before commit: request a sample enrichment of around 100 known accounts and audit accuracy against records you know to be true. Check coverage of the target market, integration quality, the vendor's data sources and privacy terms, and its transfer mechanisms. Record each assessment in the vendor risk register.

### Step 7: Field and definition governance

Naming prefixes by owner, for example `rev_` for revenue operations core, `mktg_` for marketing, `sales_` for sales, `cs_` for customer success, `int_` for integration fields, and `calc_` for calculated fields. Reject unclear or temporary names such as `tmp_`, `test_`, or `x_`.

Creation workflow: document the purpose, owner, data type, source, and where it is used. Check whether an existing field already covers it. Approve or reject within an agreed period. Add it to the dictionary only after approval.

Deprecation, from a practice-based timeline (adjust to team adoption and data volume):
1. Announce to affected teams, with the replacement field named, for about two weeks.
2. Migrate the data and sample-check it: 100 percent migrated and verified before the next step. Allow four weeks or more.
3. Hide the field from views, forms, and workflows, and keep it readable for reporting. Allow about two weeks. Extend to twelve months for high-risk fields such as revenue, dates, and identifiers.
4. Delete only after confirming no report, workflow, or integration refers to it, and after an archived export. Keep a retention period of about six months.

A field with no documented owner and no use case goes into this timeline. It is not deleted directly. Deletion always needs the approval in Step 5.

Stage definitions tie data to stages. Each stage requires specific fields before a record can advance. Example: a prospect needs account name, contact email, and lead source. A proposal needs deal size and an identified decision-maker. Stages cannot advance on data that is not there.

Shared definitions: marketing owns the lead definition, sales owns the opportunity definition, finance owns the ARR definition, and customer success owns the health score. The definitions are shared in a published document. The tools do not have to be the same.

### Step 8: Prevention controls

Trace each recurring defect to its entry point, and choose the lightest durable control:
- Validation at creation: email format, phone country format, dates that cannot be in the past (except close date), and stage moves that need approval.
- Required fields kept to the minimum needed for each object. Too many required fields reduce adoption.
- Picklists instead of free text for every categorical field.
- Default values that reduce manual entry, such as currency or country from the account.
- Integration monitoring: alert after three consecutive sync failures, check record counts weekly for drift, and alert on latency above two hours.
- Scheduled audits: weekly for operational databases, and a quarterly sample of closed opportunities, churned accounts, and enrichment data.

Assign one owner to each rule and record its review cadence. Do not call a cleanup complete because its backlog reached zero. It is complete when the source is controlled, the rule is monitored, and the next review has an owner.

### Step 9: Controls for automated writers (agents and bulk tools)

When an automated agent or bulk tool writes to the CRM:
- Log every action: what it read, what it decided, what it wrote, and when.
- Block writes to immutable fields such as account name, created date, and closed-won revenue.
- Validate every write to a mutable field against an allowed range before it is saved.
- Hold and escalate any unusual value, such as a single deal above a size threshold, for human review.
- Do not allow an agent to merge records. It may propose merge candidates only.
- Escalate decisions the agent is not confident about. Track the escalation rate. A rate above about 15 percent suggests a poor prompt or broken upstream data. These thresholds are practice-based starting points.
- Version prompts and rules as code, and test any change on a sample of about 100 records before it goes live.

### Step 10: Privacy and consent

Involve the client's legal or privacy counsel before enriching or contacting people across jurisdictions. This skill does not give legal advice.

Operational controls to build with counsel:
- Record the consent or legal basis for each contact per channel and region.
- Keep a do-not-contact flag with an immediate cessation workflow when someone objects. Log the action.
- Check each enrichment vendor's data sources and transfer mechanisms before use.
- Set a deletion-request intake process with a deadline set by counsel for each jurisdiction.

### Step 11: Operating model and cadence

Roles:
- Data owner (executive): accountable for accuracy of a domain, approves standards and field creation.
- Data steward (RevOps or sales ops): runs audits, dedupe, and approved corrections.
- Data consumers: follow the standards and are measured on data quality.
- Governance council: monthly quality scorecard and incident review; quarterly field and definition approvals; annual maturity review.

Cadence:
- Weekly: operational health for active databases, sync failures, and stale-deal checks.
- Monthly: leadership health review with object-level scores and the trend.
- Quarterly: field audit (fields not touched in three months), definition review, and a sample audit.
- After any migration, acquisition, new integration, or cleanup: a fresh snapshot, annotated.

Maturity levels, as a self-assessment:
1. Chaos: no standards, no owners, many duplicates. Fix takes three to six months of dedicated effort.
2. Reactive: some naming conventions and occasional cleanups. Owners ad hoc.
3. Proactive: council meets monthly, prevention enforced, quality scored automatically. This is the practical target within about twelve months.
4. Optimized: automated enforcement and real-time monitoring. Requires data engineering resource.

## Output

1. System-of-record table and data dictionary (or the gaps in it).
2. Health report: the composite score, object scores, rule failures and rates, eligible, excluded, and unknown counts, critical-rule status, rule version, and snapshot time.
3. Movement analysis since the last snapshot, separating corrected records, new defects, population changes, and definition changes.
4. Change plan: operations grouped by cause, with the human decisions listed separately, and the first batch sized for review.
5. Post-run reconciliation: planned, applied, skipped, failed, and newly detected.
6. Prevention backlog: each defect with its source, control, owner, and review date.
7. Open questions requiring a named decision.

## Quality bar

- Every data point has one named system of record.
- Every rule has an owner, a population, and a version.
- Unknowns are reported as unknown, never counted as passing.
- Object scores with fewer than 30 records carry a small-sample warning.
- Composite and critical-rule status are both reported.
- Every operation in the plan shows current value, proposed value, and evidence.
- No operation was applied without approval of its identifier.
- Every stale operation was stopped, not overwritten.
- The reconciliation balances.
- Every recurring defect has a prevention control with an owner.

## Rules

- MUST snapshot before any change and retain operation-level evidence.
- MUST name one system of record per data point before cleaning it.
- MUST version rules and rebaseline when rules, weights, or populations change.
- MUST report unknowns and excluded records next to the score.
- MUST NOT score unevaluated records as passing.
- MUST NOT let a composite score hide a failing critical rule.
- MUST dedupe before enrichment and never merge on name alone.
- MUST require explicit approval, by operation identifier, for merges, deletions, ownership changes, and bulk changes.
- MUST stop an operation when the target changed after planning, and re-read before every write.
- MUST NOT invent field values or convert uncertainty into a correction.
- MUST NOT delete a field directly. It goes through the deprecation timeline with approval.
- MUST NOT declare a cleanup complete until the post-run audit reconciles.
- MUST NOT send CRM data to any service the operator does not own or has not approved.
- MUST NOT give legal advice. Route privacy questions to counsel.
- NEVER present the practice-based targets, weights, or thresholds as industry standards.

### Scope boundaries

- Defines governance, scoring, and cleanup method. Does not configure a specific CRM's properties, workflows, or permissions. That needs a platform-specific skill.
- Does not inspect deals for risk in a live pipeline: use `pipeline-review`. This skill fixes the data that review depends on.
- Does not forecast or define the forecast categories. A forecasting skill is needed for that.
- Does not choose the tech stack or integration platform. That is a separate architecture decision.
- Does not provide legal advice on consent, transfer, or retention.
- Does not write outreach or sequences.

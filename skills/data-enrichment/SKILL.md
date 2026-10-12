---
name: data-enrichment
version: 1.0.0
status: draft-for-review
description: Use when inbound leads arrive without the fields needed to score, route, or segment them, or when a target list or CRM lacks firmographic or contact data. Maps the coverage gap field by field, chooses between a single provider and a waterfall across providers, sets re-enrichment cadences and quality gates, and sets the legal conditions for enrichment in Europe. Not for choosing a specific vendor on the strength of its marketing; that needs a pilot on the client's own data.
sources:
  - "Data enrichment (MIT, Rutger Katz / Neon Triforce), field priorities and use cases, waterfall strategy, real-time, batch, and event-driven patterns, provenance fields, freshness cadences, coverage metrics and quality alerts, failed-enrichment queue, cost controls, legitimate interest assessment, notification duties in Europe"
  - "Provider names, prices, database sizes, match rates, and accuracy guarantees in the source are vendor claims. They are removed. The pilot method replaces them"
  - "Corrected: the source states an Article 14 fine ceiling of EUR 10M or 2%. Article 14 falls under the higher tier in Article 83(5), so this skill says the higher tier likely applies and that counsel must confirm it"
  - "Adapted for GTM-360: LLM-based extraction described as an option with its own review gate, not a default source"
---

# Data enrichment

## Purpose

Enrichment adds third-party company and contact data to records that arrive incomplete. Without it, routing fails, scoring is guesswork, and reps spend their time on research instead of selling. This skill decides what to enrich, how to source it, how often to refresh it, and what the legal conditions are, before any contract is signed.

## When to use

- Inbound leads come in without company size, industry, or location.
- A target list lacks the data needed to score or tier it.
- The CRM cannot route or segment records correctly.
- A provider is about to be chosen, or replaced.

Route elsewhere when:

- The question is how to route leads once enriched. Use `lead-routing-design`.
- The question is how to build a list from scratch. Use `prospect-list-building`.
- The question is data quality in general. Use `revops-data-governance`.

## Inputs

- The record types to enrich: leads, contacts, accounts, and targets.
- The fields used for scoring, routing, and segmentation, as they are defined today.
- Current coverage per field, or a sample from which to measure it.
- The volume per month, and the budget.
- The regions and industries in scope, since coverage varies by region.
- The legal basis the company relies on, and whether a legitimate interest assessment exists.

## Procedure

### Step 1: Map the coverage gap, field by field

Before choosing a provider, measure what is missing. Take a sample of 100 to 500 current records and check each field used for decisions.

Priority of fields, as a starting point:

- **Priority 1, needed to route or score:** company size, industry, annual revenue, headquarters location, website domain, job title.
- **Priority 2, needed to personalise or qualify:** company description, technologies used, funding stage and date, seniority, department, direct phone.
- **Priority 3, nice to have:** social profiles.

Enrich only the fields the company actually uses. Enriching fields that are never read adds cost and legal exposure without benefit.

### Step 2: Choose a sourcing strategy

**Single provider.** One source, one contract, one data format. Simple, and often adequate for one region and one industry. Its coverage is limited, and it leaves gaps that a second source would fill.

**Waterfall.** Query a primary source. For records it does not match, or matches only partly, query a second source, then a third. Keep whatever each step returns, and record which source supplied each field.

The waterfall is almost always better than a single source on coverage, because no single provider covers every region, industry, and company size well. The size of the gain depends on the client's data, so measure it in a pilot rather than assume it.

Specialist sources, such as technology-stack data or job-posting data, are added only where the motion depends on them.

### Step 3: Run a pilot before committing

Vendor match rates and accuracy claims are not evidence for a client's own records. Before a contract, run a 30-day trial:

1. Take a sample of 100 to 500 records from the real pipeline, spread across the regions and segments in scope.
2. Run each candidate provider, and then the waterfall, on the same sample.
3. Measure, for each source: match rate, coverage of each priority field, accuracy against a checked subset, and cost per successful match.
4. Compare on cost per usable field, not on headline coverage.

Decide go or no-go on the pilot's numbers. A provider that performs well in one region can fail in another, so keep the regional breakdown.

### Step 4: Choose the architecture for each use

**Real-time on record creation.** For high-volume inbound, where routing depends on the data. Enrichment runs asynchronously after the record is saved, so the form submission is never delayed. Target completion within about 30 seconds, and then trigger scoring and routing.

**Scheduled batch.** For cleaning existing records and catching anything missed in real time. A nightly job selects records missing priority fields, from the last seven days, and processes them in batches within the provider's rate limits.

**Event-driven.** For deeper enrichment at key moments:

- A lead reaches the marketing-qualified stage: full enrichment.
- An opportunity is created: re-enrich the account, because the data may have changed.
- An account is marked as a target: full firmographic, technology, and organisation data.
- A contact joins an opportunity: check title, phone, and email are still current.
- The annual account review: full refresh.

**On demand.** For one-off research and account planning, through a browser tool or a bulk file upload.

### Step 5: Record the provenance of every enriched field

Every enriched record needs to show where its data came from. Store, at minimum:

- The provider that supplied each field, or the waterfall step.
- The date of enrichment.
- The status: matched, partial, no match, or error.
- The provider's confidence score, if one is given. Treat it as a relative indicator, since providers do not publish how it is calculated.
- For Europe, the category of source, such as a purchased database, public records, or inference.

Without provenance, a bad field cannot be traced or removed.

### Step 6: Set re-enrichment cadences

Enriched data decays. The source cites annual decay of about 22 to 30%, from vendor estimates. Measure the client's own rate by re-checking a sample.

Starting cadences, to adjust once the decay rate is known:

| Record | Re-enrich | Trigger |
|---|---|---|
| Active lead, not converted | Every 90 days | Scheduled batch |
| Active customer account | Every 180 days | Scheduled batch |
| Dormant account | Yearly | Scheduled batch |
| Opportunity contact | On stage change | Event |
| Target account | Monthly | Scheduled batch |

### Step 7: Measure coverage and quality each month

Track, by provider and in total:

- **Match rate:** the share of records enriched successfully.
- **Field coverage:** the share with each priority field filled.
- **Freshness:** the share enriched within its cadence window.
- **Cost per enrichment:** total provider cost divided by records enriched.
- **Return:** the pipeline from enriched records, compared with records not enriched.

Set alerts for:

- Records past their re-enrichment window.
- A match rate that falls below the agreed floor. The source uses 60% as an example.
- Priority field coverage that falls below the agreed floor. The source uses 80% as an example.
- Monthly cost above budget by more than a set margin. The source uses 20% as an example.

These thresholds are starting points. Set them from the pilot.

### Step 8: Handle failures

- Retry failed calls, such as rate-limited or timed-out ones, up to three times with increasing delays.
- Send no-match records to manual research, or to the next source in the waterfall.
- Accept partial matches, and flag the missing fields.
- If a provider is down, queue records and enrich them when it returns.

### Step 9: Control cost

- Enrich only records that pass basic checks: a valid business domain, not a competitor, and not a personal email address.
- Batch where the provider charges less for batches.
- Do not re-enrich a record that was enriched recently.
- Alert before the monthly credit limit is reached.

### Step 10: Use language models for research, with a review gate

Language models can extract information from company websites, such as a mission statement, a leadership page, a funding announcement, or a technology mention. This is useful where vendor data is thin or outdated, and for low-volume, high-context work such as account planning.

Controls:

- Each extracted field is stored with the source page and the date.
- A consistency check flags implausible values, such as a company size that does not fit its stage, or a title that does not fit the seniority recorded.
- Extracted data is a secondary source, and it does not overwrite a verified field from a provider.
- For high-volume enrichment, a provider waterfall is usually cheaper and more reliable.

### Step 11: Meet the legal conditions, especially in Europe

Confirm each point with counsel. This is not legal advice.

- **Legal basis.** Most business enrichment relies on legitimate interest, not consent. Before enriching at scale, write a short assessment covering three questions: why the processing is needed for a stated purpose, whether the purpose could be met without it, and what the effect is on the person. The source cites a 2024 court ruling on this test. Confirm its application with counsel.
- **Minimisation.** Enrich only the fields used for the stated purpose.
- **Erasure.** The company must be able to delete enriched data when a person asks.
- **Transparency.** The privacy notice must say that third-party data sources are used.
- **Providers.** Each provider needs a data processing agreement, and compliance with the relevant rules must be verified, not assumed.
- **Notification.** When a contact's data is collected from a third party, the person generally has to be informed. The source sets the timing at one month, or at first contact if earlier. Where informing each person would take disproportionate effort, the rules allow an exception, which counsel should confirm.
- **Penalties.** The source states a ceiling of 10 million euros or 2% of global turnover for this duty. Article 14 falls under the higher penalty tier in Article 83(5), which is 20 million euros or 4% of global turnover, whichever is higher. Confirm this with counsel before quoting any penalty figure.

Record each contact's notification date in the CRM, so that compliance can be shown in an audit.

## Output

- The coverage map: each priority field, its current coverage, and the gap.
- The sourcing decision: single or waterfall, with the pilot results behind it.
- The architecture for each use: real-time, batch, event, or on demand.
- The provenance fields, the cadences, and the alert thresholds.
- The legal checklist, with the points flagged for counsel.
- A go or no-go decision for each segment, based on whether the enriched data would be used.

## Quality bar

Every field enriched is one the business uses. Each provider has been tested on the client's own records, and the decision rests on the pilot. Every enriched value has provenance. Re-enrichment runs on schedule, and coverage is reported monthly. The legal basis is written down, and the notifications are logged. Watch for vendor match rates quoted as fact, enrichment of fields no one reads, data with no source, and penalty figures stated without checking.

# GTM Glossary

Status: PLACEHOLDER. Definitions are working drafts and must be confirmed with each client.

## Funnel stages

- **Reached:** an account present in the ad platform export. Counted once per account.
- **Engaged:** a reached account with 1 or more clicks in the period.
- **Lead:** a contact who submitted a form or was logged as a lead in the CRM. Threshold: PLACEHOLDER.
- **MQL (Marketing Qualified Lead):** a lead that meets the client's scoring threshold. Threshold: PLACEHOLDER.
- **SQL (Sales Qualified Lead):** an MQL accepted by sales after qualification. Acceptance rule: PLACEHOLDER.
- **Opportunity:** a CRM deal created from an SQL, with an amount and close date.
- **Closed Won / Closed Lost:** final deal outcomes in the CRM.

## Account terms

- **ICP (Ideal Customer Profile):** the set of firmographic and situational traits that predict fit. Defined in `context/icp.md`.
- **Multi-channel account:** an account present in two or more pipeline sources (for example LinkedIn and Google).
- **Named account:** an account on the client's target list.

## Performance metrics

- **CTR:** clicks divided by impressions, as a percentage.
- **CPC:** cost divided by clicks.
- **Engagement score:** a composite of clicks, impressions, and stage. Formula and weights are in the skill, not here. Changing them requires an eval run.
- **Influenced revenue:** revenue from accounts with exposure before the opportunity was created, within a defined window. Not the same as attributed revenue. See the attribution note below.

## Attribution note

Three separate concepts. Never add them together into one number.

- **Exposure:** an account received impressions.
- **Influence:** exposure occurred before pipeline was created, within a stated window.
- **Attribution:** a click or conversion can be traced to the pipeline event.

## Revenue terms

- **ARR:** annual recurring revenue.
- **NRR (Net Revenue Retention):** revenue retained from existing customers including expansion, divided by starting revenue.
- **GRR (Gross Revenue Retention):** revenue retained excluding expansion.
- **CAC payback:** months of gross margin needed to recover acquisition cost. Calculation method: PLACEHOLDER.

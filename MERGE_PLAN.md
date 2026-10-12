# Merge plan for the remaining source skills

Rule applied: a source skill becomes a new merged skill only when its task is not already covered by a merged skill. Source skills that repeat a task are folded into the existing skill's `sources:` block, not written again. Dispositions are a first pass and are checked when each skill is written.

## 1. Covered or folded (no new skill)

- **rutger-katz:** abm-engagement-scoring, closed-lost-revival, crm-migration-consolidation, cs-operations, data-enrichment, deal-desk-operations, deal-qualification-gates, deal-velocity-engineer, expansion-revenue-architect, gtm-compensation, gtm-data-architecture, gtm-planning, icp-builder, lead-routing, marketing-operations, onboarding-activation, operating-cadence-designer, partner-channel-operations, partner-ecosystem-architect, positioning-messaging-designer, pricing-monetisation-ops, procurement-navigation, qbr-ebr-builder, renewal-save-motion, revenue-operating-cadence, revops-change-management, revops-crisis, revops-data-governance, revops-diagnostic, revops-forecasting, revops-handoffs, revops-metrics, revops-org-chart, revops-revenue-planning, revops-salesforce, revops-strategy, revops-tech-stack, sales-methodology, sales-ramp-enablement, trial-poc-conversion, win-loss-program
- **alex-vacca:** list-architect, list-building-tips, lead-sources-guide (prospect-list-building); cold-email-4-sequence, cold-email-strategist, cold-email-templates-34, email-1-variations-7, email-metrics-benchmarks, email-writing-frameworks, josh-braun-copywriting, outreach-4-categories (outbound-cold-email); cold-call-scripts (cold-call-outreach); linkedin-campaign-complete, linkedin-limits-warmup, linkedin-success-factors (linkedin-outreach); bridgebound-firmographic-15, bridgebound-history-16, bridgebound-in-market-20, bridgebound-relationship-39, bridgebound-symptoms-11, buying-signals-6, clay-buying-signals-5, outbound-triggers-6, inbound-triggers-30, signal-sourcer (signal-detection-and-timing); clay-enrichment-9step, clay-expert (data-enrichment); frontal-messaging-templates, atl-btl-messaging (positioning-messaging-designer)
- **ido-goldberg:** battlecard, brief, icp, map-contacts, multi-thread-deals, research, score (already folded); build-list (prospect-list-building); handle-reply (reply-handling); pipeline-review (merged); reach-out (outbound-cold-email); community-radar, event-radar, post-radar, visitor-radar (signal-detection-and-timing)
- **Others covered:** gal-aga/multi-threading-coach, gal-aga/mutual-action-plan-builder, gal-tamir/buying-group (multi-threading-coach), gal-tamir/sequence-writer (outbound-cold-email), gal-tamir/territory-signal-digest (signal-detection-and-timing), brian-carroll/icp-fit-and-buying-readiness (icp-builder), chris-rodde/positioning-and-messaging, luke-shalom/category-of-one-positioning, shane-oconnor/positioning-and-story (positioning-messaging-designer), dusan-vystrcil/hiring-radar, peter-borkovich/hiring-signal-verification (hiring-signal-tracking), jorge-macias/track-contact-job-changes, sung-jo/track-champion-job-changes (champion-job-change-tracking), sabahudin-murtic/competitive-intelligence-radar (competitive-intelligence), katya-tarapovskaia/account-intelligence-analyst, yoni-tserruya/account-intelligence (account-research-brief), yoni-tserruya/competitor-intel (competitive-intelligence), yoni-tserruya/customer-health, omer-levy/customer-health-actions, jeremy-hurst/account-health-audit (cs-operations), jeremy-hurst/expansion-opportunity-analysis (expansion-revenue-architect), nikhil-mirza/deal-blocker-maneuvers (merged), justin-rowe/competitive-white-space (merged), justin-rowe/company-recon (account-research-brief), justin-rowe/abm-account-engagement-report (merged), amir-baldiga/account-research-brief (merged), tanyo-gochev/icp-matrix-builder, tanyo-gochev/tam-builder, yoni-tserruya/tam-from-verified-data, ryan-iyengar/build-and-fill-a-tam (tam-build-and-sizing), ryan-iyengar/abm-signal-watchlist, ryan-iyengar/trigger-based-outbound (signal-detection-and-timing), ryan-iyengar/governed-crm-cleanup, ryan-iyengar/resolve-before-create (revops-data-governance), scott-wueschinski/revenue-engine-maturity-diagnostic (revops-diagnostic), udi-cohen/icp-score-and-route (account-tier-scoring), udi-cohen/data-quality (data-enrichment), udi-cohen/pipeline-signal-review (pipeline-review), amos-bar-joseph/account-tier-scoring (merged), uri-knorovich/company-deep-dive (account-research-brief), uri-knorovich/launch-monitor (signal-detection-and-timing)
- **Folded into an existing skill:** dima-bilous/give-first-cold-email, peter-cools/outbound-strategy, peter-cools/signal-timing, peter-cools/website-to-signals, tim-yakubson/b2b-cold-email-copywriting, tanyo-gochev/cold-email-first-touch, tanyo-gochev/email-sequence, maja-voje/outreach-messaging, campaign-benchmarking (tanyo-gochev) → outbound-cold-email or marketing-operations; dyanesh-perumal/pre-call-script → cold-call-outreach; thomas-maitre/linkedin-comment-and-invite-writer, thomas-maitre/linkedin-limits-and-safety, tanyo-gochev/linkedin-inmail → linkedin-outreach; thomas-maitre/icp-to-linkedin-search → prospect-list-building; lucas-godtfredsen/auto-reply-is-not-a-reply → reply-handling; lucas-godtfredsen/never-guess-an-email, nylan-richard/bulk-contact-enrichment, nylan-richard/crm-enrichment-sync, nylan-richard/icp-contact-search-and-enrichment, udi-cohen/enrich-company, boaz-descalo/company-domain-resolver, omer-levy/enrich-contact → data-enrichment; ryan-iyengar/crm-health-scoring → revops-data-governance; ryan-iyengar/hygiene-gated-outbound → prospect-list-building; manny-medina/ai-pricing-model-picker, manny-medina/credit-packaging, shane-oconnor/dev-tool-pricing → pricing-monetisation-ops; manny-medina/roi-proof-generator → gal-aga/roi-business-case (merge-next, see section 2); rob-snyder/pull-call-review, kevin-kd-dorsey/call-scorecards, ryan-iyengar/evidence-based-call-scoring → call scoring (section 2); luke-shalom and maja-voje are covered above; victor-moen/b2b-affiliate-program-playbook → partner-channel-operations; sam-jacobs/profitable-efficient-growth, roman-palii/audit-the-base-not-the-rate → revenue-metrics; tanyo-gochev/campaign-benchmarking → revenue-metrics; ariel-cohen/customer-expansion-scoring → expansion-revenue-architect; ariel-cohen/champion-move-detection → champion-job-change-tracking
- **Skipped as duplicate or personal:** .system/submit-skill (platform tooling); ido-goldberg/audit-swan (platform audit), ido-goldberg/skillify (platform), ido-goldberg/clear-my-desk and ido-goldberg/inbox-zero (personal productivity); omer-levy/lusha-prospector (single vendor tool); amos-bar-joseph/kill-the-wall-of-text, amith-tk/humanize-content, gali-firon/anti-ai-slop-writing, gali-firon/human-mannerisms, vesselin-malev/content-de-slop-ai (writing style; fold one into a single writing-quality skill if wanted); gali-firon/visual-argument-review (design critique, out of scope); nadav-david/inbound-is-data (fold into signal-detection)

## 2. Merge next (distinct task, in scope for a revenue system)

Each of these is a new skill. Groups marked (one skill) are written together.

- Discovery and demo: gal-aga/discovery-to-demo-bridge, monica-dinu/b2b-demo-builder, gal-aga/roi-business-case (one skill with manny-medina/roi-proof-generator)
- Qualification audit: amit-rotstein/meddpicc-gap-audit
- Call scoring (one skill): amit-rotstein/call-kpi-scoring, kevin-kd-dorsey/call-scorecards, rob-snyder/pull-call-review, ryan-iyengar/evidence-based-call-scoring
- Post-call and post-meeting follow-through (one skill): boaz-descalo/call-followup-sweep, jeremy-hurst/post-meeting-execution, jeremy-hurst/outreach-execution, tanyo-gochev/stage-aware-follow-up
- Objections and funnel diagnosis: tanyo-gochev/objection-mining, tanyo-gochev/outbound-performance-diagnosis, peter-cools/competitor-connection-displacement (one skill with peter-cools/signal-anchored-message as its messaging section)
- Offer design: tanyo-gochev/cold-offer-architect, amir-baldiga/icp-lookalike-expansion and amir-baldiga/lookalike-candidate-sourcing (one skill: lookalike sourcing and offer fit), nylan-richard/people-lookalike-ranking
- Personalisation (one skill): alex-vacca/personalization-6-buckets, personalization-hooks, personalization-playbooks, ai-personalization-prompts, yoni-tserruya/outreach-personalization, amir-baldiga/personalized-outbound-ab-test
- Inbound and LinkedIn signal handling (one skill): ariel-cohen/handle-demo-request, handle-linkedin-connection-request-signal, handle-linkedin-profile-view-signal, linkedin-dm-signal-classifier, linkedin-engagement-handler
- Closed-won replication: ariel-cohen/closed-won-replication-play
- Warm introductions: din-arbel/warm-intro-intelligence, nadav-david/bridge-before-cold
- Deliverability (one skill): imad-badreddine/cold-email-inbox-warmup, cold-email-preflight, multi-sender-rotation, linkedin-7-day-warmup, joshua-waldman/email-deliverability, lucas-godtfredsen/inbox-warm-up-ramp
- Pipeline generation: ivan-falco/scale-b2b-qualified-pipeline, omer-levy/prospect-to-pipeline, omer-levy/prospect-to-outreach
- Account selection and demand: ivan-falco/account-selection-framework, ivan-falco/demand-lifecycle, eliezer-cohen/leaked-demand-recovery
- Messaging validation: ivan-falco/message-validation, ivan-falco/persona-mapping-framework (fold persona mapping into icp-builder if it repeats)
- Acquisition GTM integration: gerrit-kesten/acquired-brand-gtm-integration
- Founder-led sales: shane-oconnor/founder-led-sales
- Sales hiring (one skill): justin-blij/sales-hire-scorecard, sales-hire-offer-close, panel-debrief-alignment, jason-mesiarik/hiring-scorecard
- Board and leadership (one skill): jason-mesiarik/board-meeting-prep, investor-update, bench-strength-and-succession, leadership-development-diagnostic
- SDR operating rules (one skill): alex-vacca/sdr-master-prompts, alex-vacca/sdr-outbound-rules
- GTM plays (one skill): alex-vacca/gtm-plays-11, alex-vacca/gtm-philosophy
- Market finder: uri-knorovich/market-finder
- Partner and advocacy: osnat-lidor/ambassador-finder
- Move and transition diagnostic: sangram-vajre/move-gtm-diagnostic
- Account progression staging: steve-armenti/account-progression-staging
- Revenue engine and lifecycle (one skill): tanyo-gochev/saas-lifecycle, sam-jacobs/profitable-efficient-growth
- RFP response: gali-firon/rfp-response
- GTM command centre: gali-firon/gtm-command-center
- Marketing ecosystem diagnostic: justin-rowe/marketing-ecosystem-diagnostic
- Event and conference planning (one skill, scope confirmed in section 3): ariel-cohen/conference-personal-plan, conference-shared-calendar, conference-booking-links, jeremy-hurst/pre-conference-outreach, post-conference-outreach, conference-meeting-cards, boaz-descalo/event-account-plan, dave-engel/conference-recommendation
- Nadav David reply gate and recent discourse (one skill): nadav-david/reply-pull-gate, earned-autonomy, recent-discourse-sweep
- Brand mention monitoring: uri-knorovich/brand-mention-monitor

Estimated: about 45 to 50 new skills in this section, after the (one skill) groups are combined.

## 3. Scope decision needed (channel and content skills)

These are distinct tasks, but they are channel tactics rather than a revenue system. Not written until you confirm.

- **Paid ads (about 45):** ivan-falco's Meta, Google, and LinkedIn ads family (about 35 files), john-williams's Google Ads set (5), justin-rowe's LinkedIn ads set (7), brianne-thomas's LinkedIn ads (2), aditya-sriram's Google and Meta audits (2), emilia-korczynska's LinkedIn ABM ads (4), gaetano-romeo's LinkedIn audit (1), ivan-falco/1-to-1-abm-ads, abm-on-meta, abm-retargeting-framework
- **Creator and influencer marketing (about 14):** maxwell-nimmo (5), thomas-marcelle (9)
- **Search and AI visibility (about 25):** sam-dunning SEO set (8), gaetano-romeo SEO and organic audits (2), thebigasif SEO (1), yahav-fuchs AEO set (4), huxley-peckham AI visibility (3), elad-hefetz AI visibility (1), sam-dunning and gaetano-romeo overlap
- **Reddit and community (about 10):** yahav-fuchs reddit set (8), vesselin-malev reddit and quora (2)
- **Newsletter and content (about 20):** daniel-bustamante newsletter and email content set (about 14), ryan-estes beehiiv (1), vesselin-malev content and case studies (4), danni-chen launch and founder posts (2), pete-mientkiewicz lead magnet post (1), thomas-marcelle sponsored post (1), vesselin-malev founder persona ops (1)
- **Events (about 6):** sam-jacobs pavilion concierge, uri-knorovich launch monitor (if counted here), others covered in section 2

Recommendation: include ads, creator, search and AI visibility, and events only if the library should cover channel operations as well as revenue motions. Otherwise leave them out and list them as out of scope. Reddit and newsletter content fit better in a separate content library.

## 4. Counts (first pass)

- Covered or folded: about 190 source skills.
- Skipped: about 10.
- Merge next: about 50 new skills.
- Scope decision: about 130 channel and content skills.

## Progress note

Skills listed as merge next in sections 2 and 3 are being written in batches. Check `skills/` and `COVERAGE.md` for what is merged. Items written so far: call-scoring, meddpicc-gap-audit, discovery-to-demo-bridge, roi-business-case, demo-builder, objection-mining, outbound-performance-diagnosis, cold-offer-architect, call-followup-sweep, stage-aware-follow-up, competitor-connection-displacement, closed-won-replication-play, leaked-demand-recovery, warm-intro-intelligence, rfp-response, sales-hire-scorecard, board-meeting-prep, founder-led-sales, acquired-brand-gtm-integration, move-gtm-diagnostic, account-progression-staging, sdr-outbound-rules, signal-outbound-plays, cold-email-preflight, email-deliverability, market-finder, personalised-first-touch, brand-advocate-finder, profitable-efficient-growth, saas-lifecycle-programs, gtm-command-center, marketing-ecosystem-diagnostic, reply-pull-gate, earned-autonomy.

## Progress note: sales batch 4 (103 merged)

- Written: bridge-before-cold, recent-discourse-sweep, demand-lifecycle-model, post-meeting-follow-through, sales-hire-offer-close, investor-update.
- Folded, not written (overlap with merged skills): persona-mapping-framework (covered by prospect-list-building and multi-threading-coach), prospect-to-pipeline (covered by cold-offer-architect and stage-aware-follow-up), outreach-execution (covered by sdr-outbound-rules and cold-email-preflight).
- Still pending: gtm-philosophy (alex-vacca), inbound and LinkedIn signal handling (ariel-cohen), events and conference group (about 8 files), brand-mention-monitor (uri-knorovich), bench-strength-and-succession and leadership-development-diagnostic (jason-mesiarik), and the channel and content sets.

## Progress note: leadership and brand batch (107 merged)

- Written: gtm-operating-principles (from gtm-philosophy, renamed to avoid a clash with the existing GTM set), bench-strength-and-succession, leadership-development-diagnostic, brand-mention-monitor.
- Still pending: ariel-cohen inbound and LinkedIn signal handling (one skill, read before writing), and the events and conference group (about 8 files, one skill).
- Then: the channel and content sets (paid ads, creator, search and AI visibility, Reddit and community, newsletter and content).

## Progress note: signal and events batch (111 merged)

- Written: inbound-demo-request-triage (handle-demo-request), linkedin-signal-triage (profile-view, connection-request, DM classifier, post-engagement, and influencer-engager handlers, one skill), event-attendee-prep (event room intelligence), event-logistics-planning (booking links, personal plan, shared calendar, one skill).
- The events group was split into two skills, and the signal group into one, because the attendee dossier and the logistics workflow have different inputs and outputs.
- Still pending: the channel and content sets (paid ads, creator and influencer, search and AI visibility, Reddit and community, newsletter and content).

## Progress note: paid ads batch 1 (122 merged)

- Written from the platform-neutral Ivan Falco ads set: paid-channel-selection, paid-campaign-plan, paid-budget-by-stage, ad-persona-framework, ad-copy-voice-of-customer, paid-measurement-scorecard, paid-optimisation-signals, paid-scaling-quadrant, creative-fatigue-rotation, lead-form-quality, paid-offer-strategy.
- Still pending in paid ads: Meta-specific sets (ivan-falco meta-* family, advantage-plus, creating-campaigns-ads-audiences, meta-api-reference, meta-capi-and-events, meta-third-party-conversion-tracking), Google Ads sets (john-williams, ivan-falco google-ads), Google Ads and Meta audits (aditya-sriram), LinkedIn audit and targeting sets (justin-rowe, gaetano-romeo, ivan-falco linkedin-ads), and ivan-falco message-validation and ads-writing-style. Platform-specific sets are to be written in generic form, with the platform detail removed.

## Progress note: paid search and paid social batch (132 merged)

- Written, generic form: paid-search-budget-reallocation, paid-search-unit-economics, paid-search-quality-diagnosis, paid-account-change-safety (John Williams write-safety, extended to any paid account), conversion-feedback-to-ad-platforms, off-domain-conversion-tracking, paid-social-campaign-structure, paid-social-audience-strategy, paid-automation-controls, ad-creative-as-filter.
- Not written: the john-williams pmax asset-group skill (platform-specific structure; to be written as a generic multi-format automated campaign skill in the next batch), the Meta creative-set and remaining Meta sub-skills that repeat the above, the audit skills (aditya-sriram, gaetano-romeo, justin-rowe), and the ads-writing-style and message-validation sets.

## Progress note: creator and community batch (145 merged)

- Written: creator-programme-strategy, creator-deal-structure, creator-rate-band, creator-negotiation, creator-discovery-and-vetting, creator-sponsored-post-drafting, creator-programme-measurement (creator set); community-channel-research, community-post-preflight, community-comment-safety, community-account-warmup, community-account-health (community set, generic forum form); affiliate-programme-playbook (affiliate set, read in part).
- Folded, not written: the ambassador-finder (covered by brand-advocate-finder), the creator benchmark skill (covered by creator-rate-band), and the Reddit attribution and brand-mention triage (covered by brand-mention-monitor and attribution skills).
- Still pending: the newsletter and content set, the search and AI visibility set (including the answer-engine visibility tracking), the remaining paid ads audit and Performance Max skills, and the ads writing-style and message-validation sets.

## Progress note: newsletter, content and SEO batch (155 merged)

- Written: newsletter-positioning, newsletter-subscriber-onboarding, newsletter-issue-formats (includes the 52-idea and post-to-issue sources), email-subject-and-copy-review (includes the pain-is-the-pitch rewrite), campaign-benchmark-verdict, content-authenticity-review (anti-slop, humanise and de-slop sources, one skill), seo-topic-prioritisation, seo-serp-qualification, organic-decline-diagnosis (zero-click audit), answer-engine-citation-drill-down.
- Folded, not written: tanyo-gochev email-sequence into saas-lifecycle-programs (same job: behaviour-triggered lifecycle flows).
- Not yet written, referenced as plain text: seo-topic research (sam-dunning business context, research pipeline, topic shaping, keyword validation) and answer-engine visibility tracking (yahav aeo-visibility-tracking).
- Still pending: the remaining SEO research sources, the answer-engine visibility tracking skill, the ryan-estes newsletter report, the remaining paid ads sources (Performance Max generic form, audits, writing style, message validation).

## Progress note: SEO research and answer-engine batch (159 merged)

- Written: seo-account-context (business context ingestion), seo-topic-research (the seven-phase pipeline, with opportunity extraction, keyword validation, and business fit filter folded in), seo-content-format-selection (topic shaping), answer-engine-visibility-tracking (visibility tracking and the score audit).
- Folded: the sam-dunning business-fit-filter, opportunity-extraction, and keyword-validation skills into seo-topic-research; the yahav aeo-score-audit into answer-engine-visibility-tracking. The yahav advocate-voice-tuning source is not yet reviewed against brand-advocate-finder; it remains open.
- Still pending: the ryan-estes newsletter performance report, the Performance Max generic structure, the paid ads audit sets (aditya-sriram, gaetano-romeo, justin-rowe), the ads writing-style and message-validation sets, and any remaining author-level sets not yet classified.

## Progress note: paid audit, audience diagnostics, message validation and newsletter report batch (164 merged)

- Written: paid-account-audit (read-only audit, generic form of the aditya-sriram Google and Meta audits), paid-audience-reach-diagnostic (penetration and ninety-day frequency bands from justin-rowe; bands are defaults to calibrate), paid-audience-segment-diagnostic (six demographic dimensions from justin-rowe; minimum volume per segment is an author default), paid-message-validation (ivan-falco scoring, 0 to 3 on urgency, budget and fit; example figures not reproduced), newsletter-performance-report (ryan-estes; platform and API details removed, denominator rule stated).
- Folded: none new in this batch beyond the sources named above.
- Not yet written: paid-automated-campaign-structure (john-williams PMax asset-group source). Still open.
- Planned folds, NOT yet verified against the source text, so not claimed as done: gaetano-romeo linkedin-enterprise-ads-audit into linkedin-ads-audit; justin-rowe linkedin-conversion-tracking and linkedin-audience-targeting-worksheet into conversion-feedback-to-ad-platforms and paid-social-audience-strategy; ivan-falco ads-writing-style banned-word and sentence rules into content-authenticity-review. Each must be read against its target before the fold is recorded.
- Open reviews: yahav-fuchs advocate-voice-tuning against brand-advocate-finder; osnat-lidor ambassador-finder fold claim to verify; remaining unclassified author sets.
- Counts: 164 directories in skills/ (five new skills in this batch, not six). Ledger regenerated: 57 of 82 authors cited.
- Update: paid-automated-campaign-structure is now written (john-williams PMax asset-group source, generic form; two-week settling period is an author default). Count is 165. The "not yet written" line above is superseded by this update.
- Correction: the earlier line "five new skills in this batch, not six" is wrong. This batch is six skills (five in the first commit, paid-automated-campaign-structure in the second). Merged count 159 -> 165.

## Progress note: fold verification and library check (166 merged)

- Planned folds checked against source and target text. Verdicts:
  - gaetano-romeo linkedin-enterprise-ads-audit: folded into linkedin-ads-audit as an enterprise and ABM section. Thresholds are author defaults.
  - justin-rowe linkedin-conversion-tracking: partly folded into conversion-feedback-to-ad-platforms (lookback window, view versus click reporting, reconciling definitions). Platform setup steps not folded.
  - justin-rowe linkedin-audience-targeting-worksheet: partly folded into paid-social-audience-strategy (cold audience size, persona too small, situation buyers reached by message, expansion off). Official attribute lists and the worksheet format not folded.
  - ivan-falco ads-writing-style: partly folded into content-authenticity-review (read-aloud test, rewrite rules). Banned-vocabulary list not reproduced, consistent with the rule against restating pattern lists.
  - osnat-lidor ambassador-finder: folded into brand-advocate-finder (tiering, work-history check). The earlier fold claim is now verified.
  - yahav-fuchs advocate-voice-tuning: NOT a fold into brand-advocate-finder, because it is a voice-training task rather than advocate finding. Written as the new skill voice-calibration-from-samples.
- Stale references fixed in brand-advocate-finder, call-followup-sweep, demand-lifecycle-model, marketing-ecosystem-diagnostic, gtm-planning-org-design, recent-discourse-sweep and lead-routing-design.
- Still open: prospect-list-building states list hygiene is not merged (no skill exists for it). Remaining unclassified author sets (25 authors not cited in COVERAGE.md) are not yet reviewed.

## Progress note: unclassified author sets (169 merged)

- Written as new skills: warehouse-activation-sync (austin-hay reverse-etl-activation; gtm-data-architecture covers only the principle), signal-campaign-build (bojan-berisavljevic signal-to-campaign; signal-outbound-plays covers play choice only), partner-portfolio-analysis (brad-smith vc-portfolio-research).
- Folded into email-deliverability: lucas-godtfredsen inbox-warm-up-ramp (per-mailbox ramp, pause rules, primary-domain rule). Source's warm-up network claim is not treated as evidence.
- The plan's earlier "still pending" lines for the event, community and content sets are stale: those skills are written. Stale wording is superseded by this note and by the coverage ledger.
- Still open: the Meta and Google Ads family sets, the remaining AI visibility sources (huxley-peckham, elad-hefetz), thebigasif patent-backed SEO quick wins, danni-chen launch and founder posts, pete-mientkiewicz lead magnet post, manny-medina pricing and credit sets, nylan-richard candidate sourcing and lookalike ranking, and amos-bar-joseph kill-the-wall-of-text.

## Progress note: AI visibility remainder (171 merged)

- Folded into answer-engine-visibility-tracking: huxley-peckham ai-visibility-sampling (repeat asks, majority vote, presence tiers, grid, break-in-series rule) and elad-hefetz ai-visibility-prompt-research (brand held back to the final pass, provenance tags, isolated branded set). The named platform and assistants are not restated.
- Written as new skills: citation-source-outreach (huxley-peckham citation-gap-outreach) and local-answer-engine-visibility (huxley-peckham local-ai-visibility).
- Still open: thebigasif patent-backed-seo-quick-wins, danni-chen founder-post-triggers-24 and launch-window-mechanics, pete-mientkiewicz viral lead magnet post, manny-medina ai-pricing-model-picker, credit-packaging and roi-proof-generator, nylan-richard candidate-sourcing-and-ranking, people-lookalike-ranking and account-org-mapping, amos-bar-joseph kill-the-wall-of-text, and the Meta and Google Ads family sets.

## Progress note: remaining author sets, batch two (180 merged)

- New skills: lookalike-prospect-ranking (nylan-richard people-lookalike-ranking), candidate-sourcing-and-ranking (nylan-richard), account-org-map (nylan-richard account-org-mapping), exec-readable-summary (amos-bar-joseph kill-the-wall-of-text), usage-pricing-model-selection (manny-medina ai-pricing-model-picker), credit-based-packaging (manny-medina credit-packaging), founder-post-triggers (danni-chen founder-post-triggers-24), post-launch-window (danni-chen launch-window-mechanics), lead-magnet-post (pete-mientkiewicz viral lead magnet post).
- Folded: manny-medina roi-proof-generator into qbr-ebr-builder, Panel 1 value recap rules. Verified: the qbr skill already covers the value recap.
- Correction: an earlier entry said manny-medina pricing sources were folded into pricing-monetisation-ops. That was wrong. The target excludes pricing-model strategy by its own scope note, so the two pricing sources became new skills.
- Skipped: thebigasif patent-backed-seo-quick-wins. Its receipts are patent IDs and leaked API fields from an external evidence map that is not in the library and cannot be verified here. Per the rule against inventing or approximating receipts, the skill is not restated.
- Source figures not restated: market salary and outsourcing figures, vendor price points, post performance counts, and the patent evidence map.
- Still open: the Meta and Google Ads family sets (ivan-falco meta-* and google-ads, advantage-plus, meta-capi and related sets), and any uncited author sets not yet classified. COVERAGE.md's uncited list is the check for the second.

## Status correction: remaining work after batch two (180 merged)

- Ivan Falco's ads sources are mostly covered by paid skills that cite him by name (ad-copy-voice-of-customer, ad-persona-framework, creative-fatigue-rotation, lead-form-quality, paid-campaign-plan, paid-channel-selection, paid-measurement-scorecard, paid-offer-strategy, paid-optimisation-signals, paid-scaling-quadrant, paid-social-campaign-structure, paid-social-audience-strategy and others). Those coverage claims are from the citations, not a line-by-line read.
- Not yet verified line by line: the Meta reference set (meta-ads-operating-system, meta-setup-and-tracking, meta-reporting, meta-onboarding, meta-api-reference, meta-b2b-overview, meta-optimization-playbook, meta-creative-strategy, meta-offer-strategy, meta-audience-strategy, meta-campaign-structure) and the LinkedIn ABM sets (linkedin-abm-1to1-few-many, linkedin-ads-abm-guide, linkedin-ads-audience-guide, ads-outbound-signaling-guide). Each needs a read against its target before it is recorded as covered.
- Authors with no citation in COVERAGE.md are classified in the notes above (folded, covered, or skipped), with one deliberate skip: thebigasif.

## Progress note: Meta reference set checked (182 merged)

- Read line by line: meta-optimization-playbook and meta-ads-operating-system were written as paid-social-optimisation-playbook (diagnosis paths, kill, optimise and scale rule, learning phase, swap rule, 80/20). meta-setup-and-tracking was written as paid-social-launch-checklist.
- Covered by existing skills, checked by reading their sources and descriptions: meta-audience-strategy (paid-social-audience-strategy), meta-offer-strategy (paid-offer-strategy), meta-campaign-structure (paid-social-campaign-structure), meta-creative-strategy (ad-creative-as-filter and creative-fatigue-rotation).
- Skipped, with reason: meta-api-reference (API schema reference, platform documentation, not a GTM method), meta-onboarding (credential setup flow for platform tooling), meta-reporting (scripts and output standards; reporting is covered by paid-measurement-scorecard), meta-b2b-overview (platform benchmarks that could not be verified; channel choice is covered by paid-channel-selection), meta-ads (routing skill for the source's own tooling).
- Prospect-list-building: the "not yet merged" claim is corrected to point at revops-data-governance, which covers CRM cleanup and deduplication.

## Progress note: LinkedIn ABM sources checked (184 merged)

- linkedin-abm-1to1-few-many: written as abm-campaign-level-choice (levels, company versus contact lists, splitting mixed lists, per-account reach, frequency cap). Platform list minimums not restated; they must be checked against current platform rules.
- ads-outbound-signaling-guide: written as ad-engagement-outbound-triggers (intent-named campaigns, stage thresholds, personalisation by topic, sequence, feedback loop, lift against cold baseline). Named tools and the API limitation not restated.
- linkedin-ads-abm-guide: partly covered by abm-strategy-planner (budget formula). Ad formats, specs, benchmark tables and the tech stack are skipped as platform reference and unverified figures.
- linkedin-ads-audience-guide: partly covered by paid-social-audience-strategy (sizing, exclusions, lookalikes). Platform targeting attribute guidance (job function against title, seniority and company size bands) is skipped as platform reference and is not restated.

## Review pass over the whole library (184 merged)

- Overlap: descriptions compared pairwise by shared terms. The highest pair scores 0.26, so no two skills share a description closely enough to count as duplicates. The closest pairs (monthly report and audit, demand lifecycle and budget by stage, cold email and LinkedIn outreach, the two community comment skills) cover distinct tasks, and each already routes to the other.
- Routing: fifteen descriptions did not name a route elsewhere. Each now does.
- Structure: post-launch-window was missing its Output and Quality bar sections, and now has them. About forty older skills use different section names from the template (for example, no "When to use" heading). They were left as written, since their structure is intentional, and reformatting them blind would risk their content.
- Checks: no em dashes, no unresolved skill references (the three remaining backticked terms in account-tier-scoring are tier labels), and no description over the length limit.
- Not reviewed in depth: the body quality of each older skill beyond structure and overlap. That needs a per-skill read and is the remaining review work.

- Step 2 body review (184 merged): renamed "Steps" to "Procedure" in 20 skills and "Quality checks" to "Quality bar" where the target heading was absent. No content was added or removed. Still without a standard section (needs authored content, so not invented here): "When to use" in about 25 skills, "Inputs" in about 20, and "Procedure" in a few whose procedure uses other headings. Listed for a human decision. Self-QA: no em dashes, names match directories, no duplicate names, descriptions under 1024 characters with no angle brackets. Tier labels (high-potential and similar) in account-tier-scoring are values, not references.
- Step 2 completion: added "When to use" to every skill that lacked it (about 33 skills) and "Inputs" to every skill that lacked it (about 28), each drawn only from the skill's own body (purpose, principles, steps and measures) with route-elsewhere pointers to existing skills. No facts, figures or sources were added. Skills still without a "Procedure" heading (14) are phase-structured by design (for example "Periodic briefing", "Pass one", "Part one", "Method 1"); a single procedure heading would mislabel them, so they are left for a human decision.
- Full QA pass (188 merged):
  - Frontmatter: 46 skills had an unquoted description containing a colon followed by a space, which is invalid YAML. All 188 descriptions are now quoted (same text). Every file now parses and has the required fields.
  - Vendor names: incidental platform names in bodies generalised (cold-call-outreach, outbound-cold-email, marketing-operations, positioning-messaging-designer, champion-job-change-tracking, abm-account-engagement-report, crm-migration-consolidation). Routing references and citation lines are kept. The LinkedIn-named skills (linkedin-*, and abm-strategy-planner, whose subject is a LinkedIn programme) keep the platform name because it is their subject. This is a policy call for review.
  - Spelling: prose "program", "center" and "judgment" changed to British forms. Directory names are unchanged.
  - Routes: three skills pointed to "the platform skill" without naming one (lead-routing-design, revenue-handoffs, gtm-planning-org-design). Now name revops-salesforce or revops-tech-stack.
  - Duplication: no body duplication (highest 6-word overlap about 1.5 percent). Closest topic pair, closed-lost-revival and leaked-demand-recovery: the closed-lost item was removed from leaked-demand-recovery's description, so the boundary is clear.
  - Ledger: author matching ignored hyphens, so Amos Bar-Joseph showed as not cited. Matching now ignores punctuation. Authors still uncited are all listed in COVERAGE.md with a disposition.
  - Source completeness: 19 uncited source skills dispositioned. Four merged as new skills (category-of-one-positioning, commercial-base-audit, event-selection-scoring, seo-page-quick-wins), written from the method only, with no unverified names or figures. Eight skipped as connector-bound with their methods covered by merged skills. Seven open, for a decision: positioning-and-messaging, give-first-cold-email, pre-call-script, outreach-messaging, b2b-cold-email-copywriting, pull-call-review, and revenue-engine-maturity-diagnostic.
  - Still open from the earlier step: 14 phase-structured skills without a Procedure heading, by design.

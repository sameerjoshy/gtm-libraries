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

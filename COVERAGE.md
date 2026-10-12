# Coverage ledger

Tracks every source skill from the two downloaded libraries, so that nothing is dropped silently. Generated from the source tree and the `sources:` lines in `skills/*/SKILL.md`. Regenerate it after each merge batch.

## Totals

- Source skills in the first library (`gtm-skills`): 404 SKILL.md files across the author folders below.
- Source agent roles in the second library (`openclaw-skills`): 5. All five are merged into `agents/`.
- Merged skills in `skills/`: 192.

## Status meanings

- **Cited:** at least one merged skill names this author in its `sources:` block. The author's method is partly in the library. It does not mean every one of their skills is merged.
- **Not cited:** no merged skill names this author yet. Their skills are not in the library.

Per-author counts are a starting point, not a quality judgement. Merging is done by theme, and the theme decides which skills matter.

## Per-author ledger

| Author (folder) | Source skills | Status |
|---|---|---|
| ivan-falco | 44 | Cited |
| rutger-katz | 43 | Cited |
| alex-vacca | 37 | Cited |
| ido-goldberg | 19 | Cited |
| daniel-bustamante | 15 | Cited |
| ariel-cohen | 13 | Cited |
| yahav-fuchs | 12 | Cited |
| tanyo-gochev | 11 | Cited |
| justin-rowe | 10 | Cited |
| thomas-marcelle | 9 | Cited |
| ryan-iyengar | 8 | Cited |
| sam-dunning | 8 | Cited |
| gali-firon | 7 | Cited |
| jeremy-hurst | 7 | Cited |
| nylan-richard | 6 | Cited |
| vesselin-malev | 6 | Cited |
| erwann-lefevre | 5 | Cited |
| jason-mesiarik | 5 | Cited |
| john-williams | 5 | Cited |
| maxwell-nimmo | 5 | Cited |
| nadav-david | 5 | Cited |
| omer-levy | 5 | Not cited (see dispositions below) |
| peter-cools | 5 | Cited |
| thomas-maitre | 5 | Cited |
| yoni-tserruya | 5 | Cited |
| alon-goldenberg | 4 | Cited |
| amir-baldiga | 4 | Cited |
| emilia-korczynska | 4 | Cited |
| gal-aga | 4 | Cited |
| imad-badreddine | 4 | Cited |
| udi-cohen | 4 | Cited |
| uri-knorovich | 4 | Cited |
| boaz-descalo | 3 | Cited |
| gaetano-romeo | 3 | Cited |
| gal-tamir | 3 | Not cited (see dispositions below) |
| huxley-peckham | 3 | Cited |
| justin-blij | 3 | Cited |
| lucas-godtfredsen | 3 | Cited |
| manny-medina | 3 | Cited |
| shane-oconnor | 3 | Cited |
| aditya-sriram | 2 | Cited |
| amit-rotstein | 2 | Cited |
| amos-bar-joseph | 2 | Cited |
| brianne-thomas | 2 | Cited |
| danni-chen | 2 | Cited |
| din-arbel | 2 | Cited |
| gerrit-kesten | 2 | Cited |
| kevin-kd-dorsey | 2 | Cited |
| sam-jacobs | 2 | Cited |
| .system | 1 | Not applicable (source tooling, not GTM) |
| amith-tk | 1 | Cited |
| austin-hay | 1 | Cited |
| bojan-berisavljevic | 1 | Cited |
| brad-smith | 1 | Cited |
| brian-carroll | 1 | Cited |
| chris-rodde | 1 | Cited |
| dave-engel | 1 | Cited |
| dima-bilous | 1 | Cited |
| dusan-vystrcil | 1 | Cited |
| dyanesh-perumal | 1 | Cited |
| elad-hefetz | 1 | Cited |
| eliezer-cohen | 1 | Cited |
| jorge-macias | 1 | Cited |
| joshua-waldman | 1 | Cited |
| katya-tarapovskaia | 1 | Cited |
| luke-shalom | 1 | Cited |
| maja-voje | 1 | Cited |
| monica-dinu | 1 | Cited |
| nikhil-mirza | 1 | Cited |
| osnat-lidor | 1 | Cited |
| pete-mientkiewicz | 1 | Cited |
| peter-borkovich | 1 | Cited |
| rob-snyder | 1 | Cited |
| roman-palii | 1 | Cited |
| ryan-estes | 1 | Cited |
| sabahudin-murtic | 1 | Cited |
| sangram-vajre | 1 | Cited |
| scott-wueschinski | 1 | Cited |
| steve-armenti | 1 | Cited |
| sung-jo | 1 | Cited |
| thebigasif | 1 | Cited |
| tim-yakubson | 1 | Cited |
| victor-moen | 1 | Cited |

## Matching limit

Authors are matched by folder name with all punctuation and spaces removed, case-insensitively, against the `sources:` text. This handles hyphenated surnames and initials. A name written in a form the match cannot see still shows as "Not cited", so check the sources text before acting on a "Not cited" row.

## Uncited sources: dispositions

Every source skill that no merged skill names directly has a recorded disposition below. Each is one of: merged (a new skill cites it), folded (its method was added to an existing skill, which cites it), covered (the method is already in a merged skill, which is named), skipped (a connector-bound or platform-specific skill whose method is covered elsewhere), or open (a human decision is needed). No source is open at this point.

| Author | Source skill | Disposition | Where |
|---|---|---|---|
| luke-shalom | category-of-one-positioning | Merged | category-of-one-positioning |
| roman-palii | audit-the-base-not-the-rate | Merged | commercial-base-audit |
| dave-engel | conference-recommendation | Merged | event-selection-scoring |
| thebigasif | patent-backed-seo-quick-wins | Merged | seo-page-quick-wins |
| rob-snyder | pull-call-review | Merged | call-pull-diagnosis |
| chris-rodde | positioning-and-messaging | Folded | positioning-messaging-designer (evidence and narrative checks) |
| dima-bilous | give-first-cold-email | Folded | outbound-cold-email (give-first rule) |
| maja-voje | outreach-messaging | Folded | outbound-cold-email (R.E.P.L.Y. structure) |
| tim-yakubson | b2b-cold-email-copywriting | Folded | outbound-cold-email (diagnose in order) |
| dyanesh-perumal | pre-call-script | Folded | cold-call-outreach (one named prospect) |
| scott-wueschinski | revenue-engine-maturity-diagnostic | Folded | revops-diagnostic (weakest-dimension rule); the five-level scale is not added |
| gal-tamir | territory-signal-digest | Skipped (connector-bound) | Method covered by signal-detection-and-timing |
| gal-tamir | sequence-writer | Skipped (connector-bound) | Method covered by signal-outbound-plays and outbound-cold-email |
| gal-tamir | buying-group | Skipped (connector-bound) | Method covered by multi-threading-coach and account-org-map |
| omer-levy | prospect-to-pipeline | Skipped (connector-bound) | Method covered by prospect-list-building and signal-outbound-plays |
| omer-levy | prospect-to-outreach | Skipped (connector-bound) | Method covered by prospect-list-building and outbound-cold-email |
| omer-levy | enrich-contact | Skipped (connector-bound) | Covered by data-enrichment |
| omer-levy | lusha-prospector | Skipped (connector-bound) | Covered by data-enrichment |
| omer-levy | customer-health-actions | Skipped (connector-bound) | Readiness classes covered by cs-operations |

## Partly cited author: Ivan Falco, skill by skill

Ivan Falco is cited by many merged skills, but not every one of his 44 source skills is named. Each unnamed one has a disposition here.

| Source skill | Disposition | Where |
|---|---|---|
| abm-retargeting-framework | Merged | abm-retargeting-segments |
| account-selection-framework | Merged | account-selection-funnel |
| linkedin-ads-audience-guide | Merged | linkedin-audience-targeting |
| scale-b2b-qualified-pipeline | Covered | paid-social-audience-strategy, paid-social-campaign-structure, conversion-feedback-to-ad-platforms, ad-creative-as-filter |
| persona-mapping-framework | Covered | account-org-map (budget owner, champion, blocker roles) |
| 1-to-1-abm-ads | Covered | abm-campaign-level-choice (1:1 level) |
| linkedin-ads-abm-guide | Covered | abm-strategy-planner (budget arithmetic) and abm-campaign-level-choice (campaign structure) |
| linkedin-ads | Covered | linkedin-audience-targeting and linkedin-ads-audit |
| abm-on-meta | Skipped (platform) | Method covered by abm-campaign-level-choice and paid-social-campaign-structure |
| advantage-plus | Skipped (platform) | Platform feature; method covered by paid-social-campaign-structure |
| creating-campaigns-ads-audiences | Skipped (platform) | Platform set-up; method covered by paid-social-campaign-structure |
| google-ads | Skipped (platform) | Platform guide; the search audit method is in paid-account-audit |
| meta-ads | Skipped (platform) | Platform guide; method covered by the merged paid-social skills |
| meta-api-reference | Skipped (platform) | API reference, not a GTM method |
| meta-b2b-overview | Skipped (platform) | Overview; method covered by the merged paid-social skills |
| meta-onboarding | Skipped (platform) | Platform set-up; method covered by paid-social-launch-checklist |
| meta-reporting | Skipped (platform) | Platform reports; method covered by paid-measurement-scorecard |

## Other partly cited author: list hygiene

| Source skill | Disposition | Where |
|---|---|---|
| alex-vacca: list-architect (hygiene and verification) | Covered | prospect-list-building (sourcing and qualification); revops-data-governance (duplicates and cleanup). The detailed hygiene content sits in reference files that are not used |

## Matching limit

Authors are matched by folder name with all punctuation and spaces removed, case-insensitively, against the `sources:` text. This handles hyphenated surnames and initials. A name written in a form the match cannot see still shows as "Not cited", so check the sources text before acting on a "Not cited" row.

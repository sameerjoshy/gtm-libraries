# Coverage ledger

Tracks every source skill from the two downloaded libraries, so that nothing is dropped silently. Generated from the source tree and the `sources:` lines in `skills/*/SKILL.md`. Regenerate it after each merge batch.

## Totals

- Source skills in the first library (`gtm-skills`): 404 SKILL.md files across the author folders below.
- Source agent roles in the second library (`openclaw-skills`): 5. All five are merged into `agents/`.
- Merged skills in `skills/`: 188.

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
| chris-rodde | 1 | Not cited (see dispositions below) |
| dave-engel | 1 | Cited |
| dima-bilous | 1 | Not cited (see dispositions below) |
| dusan-vystrcil | 1 | Cited |
| dyanesh-perumal | 1 | Not cited (see dispositions below) |
| elad-hefetz | 1 | Cited |
| eliezer-cohen | 1 | Cited |
| jorge-macias | 1 | Cited |
| joshua-waldman | 1 | Cited |
| katya-tarapovskaia | 1 | Cited |
| luke-shalom | 1 | Cited |
| maja-voje | 1 | Not cited (see dispositions below) |
| monica-dinu | 1 | Cited |
| nikhil-mirza | 1 | Cited |
| osnat-lidor | 1 | Cited |
| pete-mientkiewicz | 1 | Cited |
| peter-borkovich | 1 | Cited |
| rob-snyder | 1 | Not cited (see dispositions below) |
| roman-palii | 1 | Cited |
| ryan-estes | 1 | Cited |
| sabahudin-murtic | 1 | Cited |
| sangram-vajre | 1 | Cited |
| scott-wueschinski | 1 | Not cited (see dispositions below) |
| steve-armenti | 1 | Cited |
| sung-jo | 1 | Cited |
| thebigasif | 1 | Cited |
| tim-yakubson | 1 | Not cited (see dispositions below) |
| victor-moen | 1 | Cited |

## Matching limit

Authors are matched by folder name with all punctuation and spaces removed, case-insensitively, against the `sources:` text. This handles hyphenated surnames and initials. A name written in a form the match cannot see still shows as "Not cited", so check the sources text before acting on a "Not cited" row.

## Uncited sources: dispositions

Every author still marked "Not cited" has a recorded disposition below. Each source skill is one of: merged (a new skill cites it), skipped (it depends on a contact-data connector the library does not use, and its method is covered by a merged skill), or open (a human decision is needed).

| Author | Source skill | Disposition | Where |
|---|---|---|---|
| luke-shalom | category-of-one-positioning | Merged | category-of-one-positioning |
| roman-palii | audit-the-base-not-the-rate | Merged | commercial-base-audit |
| dave-engel | conference-recommendation | Merged | event-selection-scoring |
| thebigasif | patent-backed-seo-quick-wins | Merged | seo-page-quick-wins |
| gal-tamir | territory-signal-digest | Skipped (connector-bound) | Method covered by signal-detection-and-timing |
| gal-tamir | sequence-writer | Skipped (connector-bound) | Method covered by signal-outbound-plays and outbound-cold-email |
| gal-tamir | buying-group | Skipped (connector-bound) | Method covered by multi-threading-coach and account-org-map |
| omer-levy | prospect-to-pipeline | Skipped (connector-bound) | Method covered by prospect-list-building and signal-outbound-plays |
| omer-levy | prospect-to-outreach | Skipped (connector-bound) | Method covered by prospect-list-building and outbound-cold-email |
| omer-levy | enrich-contact | Skipped (connector-bound) | Covered by data-enrichment |
| omer-levy | lusha-prospector | Skipped (connector-bound) | Covered by data-enrichment |
| omer-levy | customer-health-actions | Skipped (connector-bound) | Readiness classes covered by cs-operations |
| chris-rodde | positioning-and-messaging | Open | Overlaps positioning-messaging-designer. Its evidence-first stage is not in the library |
| dima-bilous | give-first-cold-email | Open | Overlaps outbound-cold-email. Its give-first offer types are not in the library |
| dyanesh-perumal | pre-call-script | Open | Overlaps cold-call-outreach. One-prospect call preparation is not in the library |
| maja-voje | outreach-messaging | Open | Overlaps outbound-cold-email. Its R.E.P.L.Y. framework is not in the library |
| tim-yakubson | b2b-cold-email-copywriting | Open | Overlaps outbound-cold-email and cold-email-preflight. Its list, offer and copy weighting needs a check |
| rob-snyder | pull-call-review | Open | Overlaps call-scoring. The PULL framework definition sits in a reference file that is not used |
| scott-wueschinski | revenue-engine-maturity-diagnostic | Open | Overlaps marketing-ecosystem-diagnostic. The revenue-engine scope is not covered |


# Coverage ledger

Tracks every source skill from the two downloaded libraries, so that nothing is dropped silently. Generated from the source tree and the `sources:` lines in `skills/*/SKILL.md`. Regenerate it after each merge batch.

## Totals

- Source skills in the first library (`gtm-skills`): 404 SKILL.md files across the author folders below.
- Source agent roles in the second library (`openclaw-skills`): 5. All five are merged into `agents/`.
- Merged skills in `skills/`: 24.

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
| daniel-bustamante | 15 | Not cited |
| ariel-cohen | 13 | Not cited |
| yahav-fuchs | 12 | Not cited |
| tanyo-gochev | 11 | Cited |
| justin-rowe | 10 | Cited |
| thomas-marcelle | 9 | Not cited |
| sam-dunning | 8 | Not cited |
| ryan-iyengar | 8 | Cited |
| jeremy-hurst | 7 | Not cited |
| gali-firon | 7 | Not cited |
| vesselin-malev | 6 | Not cited |
| nylan-richard | 6 | Not cited |
| yoni-tserruya | 5 | Cited |
| thomas-maitre | 5 | Cited |
| peter-cools | 5 | Cited |
| omer-levy | 5 | Not cited |
| nadav-david | 5 | Not cited |
| maxwell-nimmo | 5 | Not cited |
| john-williams | 5 | Not cited |
| jason-mesiarik | 5 | Not cited |
| erwann-lefevre | 5 | Cited |
| uri-knorovich | 4 | Not cited |
| udi-cohen | 4 | Cited |
| imad-badreddine | 4 | Not cited |
| gal-aga | 4 | Cited |
| emilia-korczynska | 4 | Cited |
| amir-baldiga | 4 | Cited |
| alon-goldenberg | 4 | Cited |
| shane-oconnor | 3 | Not cited |
| manny-medina | 3 | Not cited |
| lucas-godtfredsen | 3 | Not cited |
| justin-blij | 3 | Not cited |
| huxley-peckham | 3 | Not cited |
| gal-tamir | 3 | Not cited |
| gaetano-romeo | 3 | Not cited |
| boaz-descalo | 3 | Not cited |
| sam-jacobs | 2 | Not cited |
| kevin-kd-dorsey | 2 | Not cited |
| gerrit-kesten | 2 | Not cited |
| din-arbel | 2 | Cited |
| danni-chen | 2 | Not cited |
| brianne-thomas | 2 | Cited |
| amos-bar-joseph | 2 | Not cited |
| amit-rotstein | 2 | Not cited |
| aditya-sriram | 2 | Cited |
| victor-moen | 1 | Not cited |
| tim-yakubson | 1 | Not cited |
| thebigasif | 1 | Not cited |
| sung-jo | 1 | Cited |
| steve-armenti | 1 | Not cited |
| scott-wueschinski | 1 | Not cited |
| sangram-vajre | 1 | Not cited |
| sabahudin-murtic | 1 | Cited |
| ryan-estes | 1 | Not cited |
| roman-palii | 1 | Not cited |
| rob-snyder | 1 | Not cited |
| peter-borkovich | 1 | Cited |
| pete-mientkiewicz | 1 | Not cited |
| osnat-lidor | 1 | Not cited |
| nikhil-mirza | 1 | Cited |
| monica-dinu | 1 | Not cited |
| maja-voje | 1 | Not cited |
| luke-shalom | 1 | Not cited |
| katya-tarapovskaia | 1 | Cited |
| joshua-waldman | 1 | Not cited |
| jorge-macias | 1 | Cited |
| eliezer-cohen | 1 | Not cited |
| elad-hefetz | 1 | Not cited |
| dyanesh-perumal | 1 | Not cited |
| dusan-vystrcil | 1 | Cited |
| dima-bilous | 1 | Not cited |
| dave-engel | 1 | Not cited |
| chris-rodde | 1 | Not cited |
| brian-carroll | 1 | Cited |
| brad-smith | 1 | Not cited |
| bojan-berisavljevic | 1 | Not cited |
| austin-hay | 1 | Not cited |
| amith-tk | 1 | Not cited |
| .system | 1 | Not applicable (source tooling, not GTM) |

## Matching limit

Authors are matched by folder name with hyphens replaced by spaces, case-insensitively, against the `sources:` text. Some authors are written differently in the sources (for example, a folder with a middle initial). Those show as "Not cited" when they are in fact cited. Check the sources text before acting on a "Not cited" row.

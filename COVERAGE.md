# Coverage ledger

Tracks every source skill from the two downloaded libraries, so that nothing is dropped silently. Generated from the source tree and the `sources:` lines in `skills/*/SKILL.md`. Regenerate it after each merge batch.

## Totals

- Source skills in the first library (`gtm-skills`): 404 SKILL.md files across the author folders below.
- Source agent roles in the second library (`openclaw-skills`): 5. All five are merged into `agents/`.
- Merged skills in `skills/`: 171.

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
| nylan-richard | 6 | Not cited |
| vesselin-malev | 6 | Cited |
| erwann-lefevre | 5 | Cited |
| jason-mesiarik | 5 | Cited |
| john-williams | 5 | Cited |
| maxwell-nimmo | 5 | Cited |
| nadav-david | 5 | Cited |
| omer-levy | 5 | Not cited |
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
| gal-tamir | 3 | Not cited |
| huxley-peckham | 3 | Cited |
| justin-blij | 3 | Cited |
| lucas-godtfredsen | 3 | Cited |
| manny-medina | 3 | Not cited |
| shane-oconnor | 3 | Not cited |
| aditya-sriram | 2 | Cited |
| amit-rotstein | 2 | Cited |
| amos-bar-joseph | 2 | Not cited |
| brianne-thomas | 2 | Cited |
| danni-chen | 2 | Not cited |
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
| chris-rodde | 1 | Not cited |
| dave-engel | 1 | Not cited |
| dima-bilous | 1 | Not cited |
| dusan-vystrcil | 1 | Cited |
| dyanesh-perumal | 1 | Not cited |
| elad-hefetz | 1 | Cited |
| eliezer-cohen | 1 | Cited |
| jorge-macias | 1 | Cited |
| joshua-waldman | 1 | Cited |
| katya-tarapovskaia | 1 | Cited |
| luke-shalom | 1 | Not cited |
| maja-voje | 1 | Not cited |
| monica-dinu | 1 | Cited |
| nikhil-mirza | 1 | Cited |
| osnat-lidor | 1 | Cited |
| pete-mientkiewicz | 1 | Not cited |
| peter-borkovich | 1 | Cited |
| rob-snyder | 1 | Not cited |
| roman-palii | 1 | Not cited |
| ryan-estes | 1 | Cited |
| sabahudin-murtic | 1 | Cited |
| sangram-vajre | 1 | Cited |
| scott-wueschinski | 1 | Not cited |
| steve-armenti | 1 | Cited |
| sung-jo | 1 | Cited |
| thebigasif | 1 | Not cited |
| tim-yakubson | 1 | Not cited |
| victor-moen | 1 | Cited |

## Matching limit

Authors are matched by folder name with hyphens replaced by spaces, case-insensitively, against the `sources:` text. Some authors are written differently in the sources (for example, a folder with a middle initial). Those show as "Not cited" when they are in fact cited. Check the sources text before acting on a "Not cited" row.

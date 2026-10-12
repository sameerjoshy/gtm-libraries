# GTM Libraries

Private starting point for GTM-360 operating libraries. Designed to be copied per client.

## Libraries

| Folder | Purpose | Owner | Status |
|---|---|---|---|
| `definitions/` | Agreed meanings of metrics and stages | GTM-360 | Draft |
| `context/` | Company, ICP, and client facts that skills read | GTM-360 | Draft |
| `skills/` | Executable GTM skills (SKILL.md + assets), 89 merged | GTM-360 | Draft for review |
| `agents/` | GTM agent role definitions (Scout, Writer, Rep, Closer, Mission Control) with approval gates | GTM-360 | Draft for review |
| `evals/` | Test cases with expected outputs | GTM-360 | Placeholder (not yet populated) |
| `runs/` | Log of eval runs by date, skill version, context version | GTM-360 | Empty |

## Rules

- Private repository only. Nothing in this repo should contain real customer names, contacts, or revenue.
- Client copies live in their own private repositories, forked from this template.
- Every threshold or weight change gets its own commit, with the reason in the commit message.
- Every skill is tagged with a version before it is used on client work.
- Placeholder content is marked `PLACEHOLDER` and must be replaced before use.

## Replicating for a client

1. Copy this repo to a new private repository for the client.
2. Replace `context/` with the client's facts. Update `context/last-updated` in each file.
3. Keep `definitions/` unless the client uses different definitions, and record any changes.
4. Pick the skills needed and tag the versions.
5. Populate `evals/` before running any skill on client data.

Team-wide defaults (deal scoring, list tiering, CRM): see [DECISIONS.md](DECISIONS.md).

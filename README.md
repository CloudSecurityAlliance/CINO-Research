# CINO Research

Research from the Cloud Security Alliance's Chief Innovation Office (CINO). This is the evidence,
decision records, and scored predictions behind CINO columns, reports, and plugins.

Every topic here follows the same ladder, as far as it has climbed:

| Layer | What it's for |
|---|---|
| **Idea** | the question worth investigating |
| **Column or report** | the argument, so people can *read it* |
| **Research (this repo)** | the evidence, so people can *check it* |
| **Plugin** | the practice, so people can *do it* ([csa-plugins-official](https://github.com/CloudSecurityAlliance/csa-plugins-official)) |

Not every topic reaches every layer. A topic only gets a plugin when it prescribes something an AI
can actually do.

## Topics

| Topic | Type | Status | Column | Plugin | Next check |
|---|---|---|---|---|---|
| [why-is-telemetry](why-is-telemetry/) | column-research | active | Circle News 91 (Sep 2026) | planned | 2026-11-15 |

Each topic's `README.md` starts with YAML front matter holding the same fields, so this table can be
checked against them.

## How to read a topic

- **`README.md`**: what the topic is, where it stands, and which files to start with.
- **`KnowledgeBOM.md`**: the Knowledge Bill of Materials. It lists every claim the work relies on,
  its source, and whether it has been verified.
- **`CognitiveBOM.md`**: the Cognitive Bill of Materials. It records how the thinking went: the
  decisions made, the alternatives rejected, what was superseded, and what we expected to happen.
- **`experiment-log.md`**, where present: **append-only** predictions with check-by dates, scored
  when they come due. Wrong predictions are kept. The git history shows each prediction was written
  before its outcome.

## Licence

Content is licensed under [CC BY 4.0](LICENSE). Share and adapt it, with attribution to the Cloud
Security Alliance.

"Cloud Security Alliance", "CSA" and the CSA logo are trademarks of the Cloud Security Alliance, and
no licence here grants rights to them.

## Feedback

Open an issue, with the topic name in brackets at the start of the title, e.g.
`[why-is-telemetry] ...`. Corrections to claims are especially welcome. They are logged in the
topic's KnowledgeBOM, not silently fixed.

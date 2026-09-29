---
title: Why Is Telemetry
type: column-research
status: active
started: 2026-09-24
last_reviewed: 2026-09-28
column: Circle News, September 2026 (Kurt Seifried, CSA); final text in review
plugin: planned (csa-plugins-official)
next_check: 2026-11-15
source: exported from CSA's internal writing workspace (Circle News research packet); experiment-log.md and TEMPLATE.md are originals here
---

# Why Is Telemetry

**The argument in one paragraph.** Traditional telemetry records *what* happened. As AI does more
consequential work, organizations also need to record *why*: the intent, the evidence relied on,
the assumptions, and the alternatives rejected. Above all, they need to record **what they expected
to happen, written down before they know the result**. Then they score it against what actually
happened. Once why becomes telemetry, judgment becomes data. People have tried to capture reasoning
for more than fifty years, and it mostly failed on cost. AI changes that cost, but capturing the
reasoning isn't enough. The expected outcome is what makes it something you can learn from.

## Start here

| If you want | Read |
|---|---|
| **To try it** | [`TEMPLATE.md`](TEMPLATE.md): a decision record with expected-outcome fields |
| **To see us do it, including where we're wrong** | [`experiment-log.md`](experiment-log.md) |
| The evidence, claim by claim | [`KnowledgeBOM.md`](KnowledgeBOM.md) |
| How the thinking changed, with decisions and rejected paths | [`CognitiveBOM.md`](CognitiveBOM.md) |
| The source sweep: what held up, what was corrected, who else is working on this | [`11-source-sweep.md`](11-source-sweep.md), with raw evidence in [`sources/`](sources/) |
| The first-person case (CSA's MCP server work) | [`14-mcp-case-material.md`](14-mcp-case-material.md) |

## What's here, and what isn't

This folder holds what you need to **use** the idea and to **check** it:
- the template;
- the experiment log;
- the two BOMs;
- the source sweep and its raw evidence;
- the first-person case material.

The column's working papers (research sequence, design notes, drafts, and the numbered files the
BOMs sometimes refer to, such as `04` or `10`) live in CSA's internal writing workspace and are
not published here. Where the BOMs cite a numbered file that isn't in this folder, that is why.

## What the column cites, and where it's backed

| Column claim | Source | KnowledgeBOM |
|---|---|---|
| A firm's information structures are the modern factory layout, and they never wear out | Paul David, 1990, p. 360 | B2 |
| Workslop: 40% of 1,150 US desk workers received it in the past month; nearly two hours per instance (self-reported) | HBR, Sep 2025 | C3, C4 |
| Capturing rationale costs the recorder now and benefits someone else later | Grudin, 1996 | H1 |
| Context files handed to coding agents didn't generally improve task success, and cost 20%+ more | arXiv 2602.11988 | I7 |
| A recorded prediction checked against real email: the white text got through, as predicted, but for a different reason than the one written down | [csa-zendesk experiment](https://github.com/CloudSecurityAlliance/csa-zendesk/tree/main/experiments/2026-09-24-h1-h2-reachability) | [`14`](14-mcp-case-material.md) §3 |
| Training a model against a monitor that reads its reasoning drives the monitor's recall to near zero | Baker et al. (OpenAI), 2025 | J4 |
| The Army's after-action review; forecasting tournaments | TC 25-20; Mellers et al. 2014 | H4, A4 |
| No standard, framework or tool found that records an AI agent's own expected outcome | negative search, 2026-09-24 | I8 |
| Four control moves in one day's work on one server | session logs, traced 2026-09-28 | G2 |

Corrections are logged in the KnowledgeBOM, not silently fixed.

## Corrections

We log corrections here instead of quietly editing them away. The column argues that written
reasons are claims to be tested, and these are ours being tested. Most were caught by our own
source checks or by an adversarial review from a second AI before publication.

| Date | What was wrong | How it was found | What changed |
|---|---|---|---|
| 2026-09-24 | Workslop was quoted as 41%. The survey's own figure is 40% (41% appears only in a summary blurb) | Source sweep | Corrected in the KnowledgeBOM (C4) |
| 2026-09-24 | Paul David's "before" state was described as central electric drive. It was *group drive* | Source sweep | Corrected (B2) |
| 2026-09-24 | A cited paper was listed as arXiv. It is a Preprints.org preprint, not peer reviewed | Source sweep | Corrected (E3) |
| 2026-09-28 | "Paid for that lesson four separate times" had grown in the retelling, from one branch in one day to "the fleet" | Tracing the claim through the session logs | The column now says one day's work on one server (G2) |
| 2026-09-28 | A study that scored the *text* of reasoning was cited in a way that contradicted the column's own rule about grading reasoning | The author's read | Cut from the column (H5) |
| 2026-09-29 | **An export on 2026-09-28 included internal support-ticket figures from our corpus study** (ticket counts, element counts, flag rates), against this repo's own public-safety rule. It contained no credentials and no personal data | Adversarial review by a second AI | Removed from [`14-mcp-case-material.md`](14-mcp-case-material.md) on 2026-09-29. **They remain in this repo's git history.** We chose not to rewrite that history, because the history is what shows when our predictions were made. |

## Status

- **The column** is written and in final review.
- **The public repo and experiment log** started on 2026-09-28. The template now separates the
  **hoped** outcome from the **expected** one.
- **The plugin** (decision records with expected outcomes, plus a scoring command) is planned.
- **The first scoring date** is 2026-11-15.

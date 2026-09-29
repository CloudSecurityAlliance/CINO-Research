# CLAUDE.md

Guidance for AI sessions (and humans) working in this repository.

## What this repo is

The **public shelf** for research from CSA's Chief Innovation Office. The working drafts live in
CSA's private workspaces, and finished, public-safe research is published here. Everything in this
repo is public, so treat every file, commit message, issue, and PR description as published
material.

## Layout

One folder per research topic at the repo root, nothing else. There are no category folders and no
meta folder.

- **Folder names are stable and permanent.** Columns, plugins, and Labs pages link to them, so never
  rename or move a topic folder.
- **Folder names are lowercase with hyphens and carry no date.** Topics are kept up to date, and
  the date lives in the front matter. The one exception is a deliberately dated snapshot, which can
  carry its year.
- **Category, status, and ladder stage are metadata, not folders.** A topic changes status over
  time; its path never changes.

## Topic README front matter

Every topic `README.md` starts with YAML front matter:

```yaml
---
title: Human-readable title
type: column-research      # column-research | engineering | sense-making | tracker | post-mortem (add types only when a topic needs one)
status: active             # seed | active | published | living | archived
started: YYYY-MM-DD
last_reviewed: YYYY-MM-DD
column: where the argument is published, or "none"
plugin: plugin path in csa-plugins-official, "planned", or "none"
next_check: YYYY-MM-DD     # next experiment-log due date, if any
source: where the working original lives (describe it; do not link private repos)
---
```

When a topic's front matter changes, update the root `README.md` topics table to match.

## What a topic contains

These are goals, not a template. Include what the topic needs.

- `README.md`: front matter, what the topic is, its current state, and where to start.
- `KnowledgeBOM.md` (required): the claims relied on, their sources, and their verification status.
- `CognitiveBOM.md` (required when decisions are made): decisions, rejected alternatives,
  supersessions, and each decision's **expected outcome with a check-by date**.
- `experiment-log.md` (when the topic makes predictions): append-only. See the rules below.
- `sources/`: evidence files.
- Anything else the topic needs (templates, findings, datasets), named for what it is.

## Open work

[`TODO.md`](TODO.md) at the repo root indexes all open work, one line per item, alongside GitHub
Issues. Keep it current when a topic's work starts, advances or finishes.

## Rules

1. **Pull requests only.** Never commit directly to `main`.
2. **Public safety.** Before anything lands, check it contains none of the following:
   - facts about a specific customer or tenant (vendor facts are fine; facts about one
     organization's data or configuration are not);
   - internal system designs, internal incident details, or internal figures;
   - links to private repositories, personal data, or credentials of any kind.

   The `public-safety` CI check catches the structural patterns. It cannot catch meaning, so read
   before you publish.
3. **One original per artifact.**
   - Most files are *exported* from a private working copy, and the topic README names it (in
     words).
   - Experiment logs and templates published only here are *born here*, and this copy is the
     original.
   - Never edit the same artifact in two places.
4. **Experiment logs are append-only.**
   - Never edit a prediction after it is recorded.
   - Record outcomes as new entries.
   - Keep wrong predictions, and score them. The commit history is the proof, so don't rewrite it.
5. **Corrections are logged, not silent.** When a claim turns out wrong, change its KnowledgeBOM
   status and note what changed and when.
6. **Naming:** use KnowledgeBOM and CognitiveBOM. Don't use KBOM or CBOM, which collide with the
   Kubernetes and Cryptographic Bills of Materials.

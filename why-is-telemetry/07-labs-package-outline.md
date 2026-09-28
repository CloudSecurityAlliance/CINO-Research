# CSA Labs Page: /why-is-telemetry

> **Deferred 2026-09-28 (Kurt; CognitiveBOM C19).** The column ships alone. Build v0.1 at the first scoring date (2026-11-15), with real results in the experiment log. Proposed format: one page plus a small public git repo as the source, so commit history proves each prediction was recorded before its outcome.

**Rewritten 2026-09-28.** It replaces the pre-sweep package outline. The earlier plan (maturity
model, design-dimensions framework, full experiment-pattern catalogue) is **parked, not dropped**.
See "Later" below, and `08`.

**What the page is:** a living companion to the column, not a longer column. It holds four things
the column can't:
- the full evidence;
- the template the column's close asks readers to use;
- the public KnowledgeBOM and CognitiveBOM;
- an experiment log where the page scores its own predictions.

**Model:**
- **Stable slug** `labs.cloudsecurityalliance.org/why-is-telemetry`, with no date in it.
- **Version and last-reviewed date** at the top, plus a changelog.
- **TLP:CLEAR, CC BY 4.0.**
- **Built from this packet**, which is the one source of truth. The page is a rendering of it,
  never edited separately.
- **Build process** (as for the Slaughter package): the WordPress content-authoring MCP, with files
  in the Media Library.

## Page structure

### 0. Header block

- Version (v0.1 at launch), last reviewed, next scoring date.
- TLP:CLEAR, license, and a short link.
- One line: "The column is the argument; this page is the evidence, the kit, and the scorecard."

### 1. The argument in one screen (~200 words)

Thesis, the one new idea (write down the expected outcome and score it), and a link to the column.

### 2. Long-form write-up (~3,000-3,500 words)

This is the column's argument with its evidence left in. It can run longer than the column in
three places: the lineage, the landscape, and the design rules.

| # | Section | Carries | Main sources (KnowledgeBOM IDs) |
|---|---|---|---|
| L1 | **What vs. why** | Telemetry records what. Agents make why operational. Argyris's thermostat, *"Why am I set at 68 degrees?"*, is single-loop vs double-loop learning. | A1-A3; sweep 2 §5.1 |
| L2 | **The productivity pattern** | David, including the p. 360 information-structures line. The J-curve. The ILO's "aggregation paradox" (task gains of 10-70%, no macro gain yet). DORA 2024. Full workslop figures with caveats. METR's perception gap, clearly dated early 2025. Counter-evidence stated fairly: customer support +14%, BCG consultants +12%/40%. | B1-B6, C1-C7 |
| L3 | **55 years of trying** | IBIS → QOC/gIBIS → Compendium → ADRs → PEP/RFC/KEP templates → decision journals. Grudin's four reasons it failed. Levitt & March. NASA's lessons-learned system (43% of project managers contributed). What *did* work, and why: the Army AAR, Tetlock's tournaments, kernel reviewers enforcing "describe your problem". | H1-H4, H7, H8, H11 |
| L4 | **What AI changes, and what it doesn't** | Capture cost; the beneficiary gap (`MINE`); capture in the execution path; rationale can be scored. It does not change politics, blame (2-5% of failures blameworthy vs 70-90% treated as blameworthy), or reconstruction bias. | H5, H6, H9, H11 |
| L5 | **The current wave and its gap** | Landscape, described generically rather than as a VC thesis: decision traces, spec-driven development, agent checkpoints, reasoning-provenance schemas. The gap: none records an expected outcome. Links to the gap table (section 5). | I1-I8 |
| L6 | **The core: the expected outcome is the join key** | Why a prediction is what turns a record into data. Falsifiability. The three-question gate for what deserves a record. | A4, A5, I8 |
| L7 | **Rationale is not truth: evidence and ten design rules** | The evidence: Nisbett & Wilson, choice blindness, Chen 2025, Baker 2025, Fischhoff, Lerner & Tetlock, registered reports. The rules: capture before, structured claims, score after, never grade the rationale, pre-decision process accountability, keep it cheap, sample and mine, treat it as sensitive data, CoT as a signal but not the record. | A6, D4, J1-J6 |
| L8 | **Worked cases** | The MCP pair: library-first ("paid for four times") and H1/H2, with a link to the public experiment and the precise 82.6% wording. Kurt's five-field decision standard, and why the loop-closing field lived in the format nobody used. | `14` |
| L9 | **Limits** | Politics and blame; gaming; sensitive data in reason fields; intent files alone don't help (the ETH result); agents are poor at forecasting (Qian 2026); aggregate scoring hides the populations where judgment fails, so disaggregate. | I7, J4-J6 |
| L10 | **Going first** | What CSA is doing, in public, on this page. Leads into sections 3 and 4. | none |

### 3. Try-it kit (the resource the column's close points to)

1. **Decision-record template** (Markdown, downloadable). Kurt's five fields (decision, why,
   rejected alternatives, revisit trigger, connections) and optional assumptions, **plus**:
   - expected outcome;
   - confidence;
   - check-by date;
   - actual outcome (filled in later);
   - what we learned.
2. **The three-question gate:** hard to reverse, surprising without context, a real trade-off.
3. **Agent instruction:** a short prompt block that makes an AI emit the record as structured
   output *before* the result is known, with an explicit "do not rewrite after the outcome" rule.
   Starts as a prompt. It becomes an installable skill only if people ask (decision pending).
4. **Scoring procedure:** what to do on the check-by date (compare, record, feed back), and the
   rule never to grade the rationale text itself.

### 4. Experiment log (living: the page scores itself)

A table of dated predictions with check-by dates, filled in as they come due.

**Seed entries:**
- The CognitiveBOM expected outcomes: C15 (lineage framing reads as a contribution), C16 (readers
  see a series arc), C17 (the MCP pair loses nothing).
- A page-level prediction: someone outside CSA uses the template within 90 days.
- A standards prediction: whether OpenTelemetry proposals #72 or #239 merge by a date.

**Rule:** entries are never edited after the fact. A wrong prediction is scored and kept.

### 5. Standards and landscape gap table (living)

Rows:
- OpenTelemetry GenAI conventions
- OWASP Agentic Top 10
- CSA AICM
- EU AI Act (Art. 12, 13, 86)
- NIST AI RMF
- ISO/IEC 42001
- observability tools
- the decision-trace and spec-driven wave

Columns: records *what*? records *why*? records an *expected outcome*? last checked.

Re-checked on each scoring day. This is where "kept up to date" is most visible.

### 6. Downloads and provenance

- `KnowledgeBOM` and `CognitiveBOM` (Markdown; embedded JSON when practical).
- The source sweep summary (`11`) and `sources/`.
- The MCP case material (`14`).
- Everything TLP:CLEAR, with each claim marked as verified or unverified.

### 7. Changelog

Version, date, what changed, and which experiment-log entries were scored.

## Keeping it current

- **Scoring day, quarterly.** Check-by dates fall due, and the gap table is re-checked. The refresh
  is driven by predictions coming due, not by someone remembering.
- **Event triggers:**
  - an OpenTelemetry decision-point or judgment proposal merges;
  - AICM adds a per-decision control;
  - EU AI Act high-risk obligations take effect;
  - a new entrant claims the expected-outcome ground.

  If worth it, record these as `WAITING-FOR` entries, as in the Slaughter package.
- **Owner:** Kurt. The page has one owner, and updates go through this packet.

## Resources: v0.1 vs. later

**v0.1 (launch with the column, or within a week of it):**
- sections 0, 1, 3 and 4;
- a first cut of section 2 (it may be short at launch: L3, L6, L7 and L8 first);
- section 6.

**Later, when there is a reason:**
- the full long form;
- the gap table (section 5) filled in completely;
- a PDF through the document pipeline;
- serving the page and files from the CSA MCP server;
- the installable skill;
- a proposed AICM control for per-decision expected outcomes, posted for comment (Kurt's call);
- the parked framework material from `08`: maturity model, design dimensions, experiment-pattern
  catalogue.

## Open decisions (Kurt)

1. Whether v0.1 launches with the column.
2. The kit's agent piece: a prompt only, or an installable skill.
3. The AICM control proposal: on the page, later, or internal.
4. Which packet files ship. Default: the BOMs, `11`, `14` and `sources/` ship. `01`-`10` and `12`
   stay working files.

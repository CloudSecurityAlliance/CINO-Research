# CognitiveBOM - Working Cognitive Bill of Materials

This is the working cognitive bill of materials for *Why Is Telemetry*. It records how the thinking changed, what was selected, what was superseded, and what remains open.

Naming decided 2026-09-24 (Kurt): **KnowledgeBOM** and **CognitiveBOM**. Both acronyms collide: the bare "CBOM" is the Cryptographic Bill of Materials (CycloneDX / ECMA-424), and the bare "KBOM" is the Kubernetes Bill of Materials (KSOC, 2023).

## Disposition vocabulary

| Disposition | Meaning |
|---|---|
| `completed` | Reasoning step or decision currently stands |
| `superseded` | Useful earlier position replaced by a better one |
| `rejected` | Explicitly out for this article |
| `open` | Still unresolved |
| `parked` | Valuable but belongs in Labs or future work |

## C1 - Initial frame: AI organizations and RSI

**Origin:** user question  
**Disposition:** `superseded`

Initial frame: explore whether people are writing about companies or organizations run almost entirely by AI, with a small human group governing boundaries and values.

What changed:

The article did not become a piece about autonomous companies. That topic produced the deeper mechanism: if organizations become AI-native, the hard problem is not only doing work with agents. It is preserving enough state for the organization to improve the work, the workflow, the evaluator, and the governance.

## C2 - Bottlenecks narrowed toward judgment

**Origin:** joint  
**Disposition:** `completed`

The early bottleneck list included culture, capability, judgment, causal attribution, long-horizon reliability, coordination, improvement-loop integrity, provenance, authority, governance bandwidth, grounding, and economics.

What survived into the column:

- judgment;
- why/rationale;
- expected versus actual outcomes;
- workflow improvement.

What moved to Labs:

- full bottleneck taxonomy;
- governance bandwidth;
- self-adaptive-system prior art;
- long-horizon reliability.

## C3 - Standardization reframed

**Origin:** Kurt  
**Disposition:** `completed`

Earlier implicit bias: optimize toward one best workflow.

Kurt challenged this by asking why we assume one workflow must win. AI can make variants, consume variants, and compare variants in ways human organizations rarely could.

New frame:

> Standardization is partly an adaptation to scarce human cognition. AI may make managed pluralism practical.

Article role:

Mostly background. The column uses only the narrower implication that AI enables repeat, branch, replay, and comparison.

Labs role:

Major design dimension.

## C4 - Solution space and unacceptable boundaries

**Origin:** Kurt  
**Disposition:** `completed`

Important shift:

The work is not only to define what is good. It is also to define what is unacceptable, and why.

Why it matters:

Explicit red lines permit more variation inside the acceptable envelope. They also make evaluation records more useful because a later review can see which boundary was active at the time.

Article role:

Probably one sentence if included.

Labs role:

Core section in the design-dimensions report.

## C5 - Exploration dividend

**Origin:** joint  
**Disposition:** `parked`

Earlier framing: extra AI attempts cost more tokens and should be justified by better current output.

Improved framing:

Extra attempts can produce artifact value now and learning value later.

Working term:

> Exploration dividend.

Article role:

Possibly one sentence in the "cheap cognition changes what is practical" beat.

Labs role:

Economics / compute allocation model.

## C6 - Negative knowledge elevated

**Origin:** Kurt  
**Disposition:** `completed`

Kurt emphasized that rejected ideas, failures, near misses, and false starts must be recorded.

Reasoning:

If organizations only record wins, they relitigate old decisions and never see patterns in the negative space.

Candidate line:

> Repeated rejection is itself telemetry.

Article role:

Potential supporting beat, but may be cut for space.

Labs role:

Major CognitiveBOM feature.

## C7 - Causality split across KnowledgeBOM and CognitiveBOM

**Origin:** joint  
**Disposition:** `completed`

Question:

Does causality belong in the knowledge bill of materials, the cognitive bill of materials, or both?

Current answer:

- KnowledgeBOM stores causal claims about the world, versioned and evidence-linked.
- CognitiveBOM records which causal claims this work relied on and how they shaped decisions.

Why it matters:

Recursive improvement needs to know not only what changed, but which causal assumptions drove the change.

## C8 - Workflow files changed the process objective

**Origin:** uploaded README / CLAUDE review  
**Disposition:** `completed`

Reading the workflow files clarified that this column should have two objectives:

1. produce the best possible Circle News column;
2. use the column process itself as a controlled recursive-improvement experiment.

This fits existing conventions:

- research sequence;
- decisions made;
- decisions against;
- protected lines;
- cutting-room material;
- delivery record.

## C9 - Title locked

**Origin:** user memory of the line  
**Disposition:** `completed`

The line recovered:

> Why is telemetry.

Why it won:

- short;
- memorable;
- slightly puzzling;
- observability-native;
- scales to the larger organizational argument.

Superseded title ideas:

- "Why do we only do knowledge work once?"
- "What happens when work becomes cheap enough to repeat?"
- "The End of the One Best Way"

## C10 - Article/Labs split

**Origin:** joint  
**Disposition:** `completed`

Decision:

Circle News carries the argument. Labs carries the machinery.

Reason:

The underlying material is much larger than a newsletter column. Trying to carry the framework, sources, pattern catalog, maturity model, and BOMs in the article would weaken the column.

## C11 - Workslop sharpened the problem

**Origin:** Kurt thought experiment, source search in conversation  
**Disposition:** `completed`

Earlier problem statement:

Organizations need to record why.

Sharper problem statement:

AI can make one person faster while moving the missing thinking downstream.

Protected line:

> AI can make an individual more productive while making the organization less productive.

Why it matters:

This gives the article a concrete failure mode and avoids sounding like documentation advocacy.

## C12 - General-purpose technology frame added

**Origin:** Kurt  
**Disposition:** `completed`

Kurt suggested the electricity/computers analogy. It became the article's historical frame.

Decision:

Use electricity and computers. Keep power tools as cutting-room material unless the column needs a personal illustration.

Why:

Electricity and computers are the strongest historically supported cases. Power tools are vivid but would slow the column.

## C13 - Counterargument identified

**Origin:** assistant synthesis  
**Disposition:** `completed`

Obvious objection:

Recorded rationale is not truth. Humans and models rationalize, explanations can be wrong, and stated intent can be gamed.

Response:

Capture structured claims, link them to evidence and outcomes, and test them over time.

This must appear in the column for credibility.

## C14 - Current open items

**Origin:** latest synthesis  
**Disposition:** `open`

Open:

- exact opening hook;
- exact source list for inline citations;
- whether KnowledgeBOM/CognitiveBOM are named in the column;
- whether the software architecture example appears in the column;
- how explicitly to say "recursive self-improvement" in the close.

## C15 - Source sweep moves the thesis's weight

**Origin:** source sweep, 2026-09-24 (`11-source-sweep.md`)
**Disposition:** `completed` (Kurt, 2026-09-24)

What the sweep found:

- The "capture why" half of the thesis is crowded. Foundation Capital's "context graphs" (Dec 2025) says "the 'why' becomes first-class data". Spec-driven development, Entire Checkpoints, the Oracle AER schema and CSA's Agentic Trust Framework all capture agent rationale.
- The "record the expected outcome, then score it against what happened" half appears open for AI agents. Among human practices, only the Army AAR and Tetlock's tournaments close that loop, and they are among the best-evidenced.
- The old design-rationale literature failed on economics (Grudin 1996; Levitt & March 1988). AI moves those economics, which gives the column its "why now".

Options (not decided):

- (a) Keep the protected pivot line, acknowledge Foundation Capital in one sentence, and make the expected outcome the distinctive middle.
- (b) Sharpen the pivot itself around the prediction.

**Decision (Kurt, 2026-09-24):** do not cite Foundation Capital. Tell the idea's lineage
instead. "Why is telemetry" has roots about 55 years back (design rationale, IBIS 1970). It
failed because of humans. It has resurfaced with AI. Now we are ready to use it. The
generic "it has resurfaced with AI" covers context graphs, spec-driven development and agent
checkpoints without naming a VC thesis.

Precision note for drafting: the evidence says it failed because capture cost *humans* effort
that benefited *someone else, later* (Grudin 1996; Levitt & March 1988), plus politics and
blame. AI fixes the cost and beneficiary parts. It does not fix politics or blame
(Edmondson's 2-5% vs 70-90%). "Ready to leverage it" is strongest if the column says which
part changed.

Follow-up check (2026-09-24): Foundation Capital's later output is a Jan 2026 "one month in"
recap, a Jan 2026 panel, and a Sep 17, 2026 podcast with Aaron Levie. None of it links traces
to outcomes or records predictions. The expected-outcome ground is still unclaimed.

**Expected outcome (per this entry's own advice):** acknowledging the prior and centering the expected outcome should make the column read as a contribution rather than a restatement to readers who follow enterprise AI. **Check by:** 2026-11-15, against reader feedback after publication.

## C16 - Coverage check: this column is the culmination of 78 → 80 → 87 → 89

**Origin:** coverage check, 2026-09-24 (`12-coverage-check.md`)
**Disposition:** `open` (recommendations await Kurt)

Findings:

- 88 already told the Paul David dynamo and J-curve story, three months ago.
- 80 already argued that AI makes capturing decisions and reasons affordable. That is the economics half of Claim 7b.
- 87 already asked for reasoning chains and "what was considered and dismissed".
- 89 already argued for keeping the stops, reading them together, not punishing the reporter, and closed on the evaluator.
- 78 had "track decision rationales" as a bullet.

The unpublished core is the expected outcome, scored against what happened.

Recommended:

- Use callbacks instead of retellings.
- Use David p. 360 "information structures" in place of the dynamo retelling.
- Bridge from 89: "89 learned from the stops; this learns from the decisions that didn't stop".
- Close on something other than the evaluator.
- Align BOM naming with column 89's `COGNITION-BOM.md` / CogBOM. (Resolved 2026-09-24: KnowledgeBOM / CognitiveBOM everywhere.)

**Expected outcome:** readers of 87-89 recognize a series arc rather than repetition. **Check by:** 2026-11-15, against reader feedback.

## C17 - An internal operational example, considered and dropped

**Origin:** joint, 2026-09-24
**Disposition:** `rejected` (Kurt, 2026-09-25)

An example drawn from CSA's internal operations was explored as the failure case for the expected-outcome beat, then dropped during the public-release sanitization. It isn't needed for the argument, and internal operations are not public material.

The first-person material now comes from the public MCP server work (`14-mcp-case-material.md`):
- **Failure side:** the library-first lesson "paid for four times".
- **Success side:** the H1/H2 test, a recorded reason that testing corrected.

**Expected outcome:** the column loses no strength from the swap, because the MCP pair still shows both halves (a why that was lost, and a why that was recorded and then tested). **Check by:** Kurt's read of `draft-01`.

## C18 - Column beat map written; three defaults proposed

**Origin:** joint, 2026-09-28 (`10-story-beat-synthesis.md`)
**Disposition:** `completed` (Kurt, 2026-09-28: defaults accepted, with one adjustment to #1). Originally three defaults awaited Kurt:
1. drop "recursive self-improvement" from the column entirely;
2. end on an invitation, not an admission;
3. open with the telemetry hook, and move Argyris's thermostat to Labs.

**Rationale:**
- The core idea (write down the expected outcome) gets 35% of the words.
- Beats already published become callbacks.
- The first-person pair comes from public MCP work.

**Rejected alternatives:**
- Keep the original 10-beat map. Most of its words would retell columns 80, 87 and 88.
- Move the lineage after the core, which lands the core earlier. Rejected because the lineage earns the "why now".

**Adjustment to #1 (Kurt):** don't drop the idea. Say it as recursive *process and organizational* improvement, not a model rewriting itself. In the draft: "not a model rewriting itself, but a process, and eventually an organization, getting better at the work by doing the work."

**Expected outcome:** `draft-01` lands within ~10% of 1,900 words without cutting Beats 7-8. Kurt's first read finds no beat that feels like a rerun of 87, 88 or 89.
**Check by:** Kurt's read of `draft-01`.

## C19 - Labs page: living, lean v0.1

**Origin:** Kurt proposed a kept-up-to-date page, 2026-09-25. Planned in `07-labs-package-outline.md` on 2026-09-28.
**Disposition:** `completed`, as **deferred** (Kurt, 2026-09-28). Publish nothing until there is something to score. The column ships alone, with the three fields inline and no Labs link. Build v0.1 at the first scoring date (2026-11-15), with real results in the experiment log.

**Format (proposed 2026-09-28, awaiting Kurt):**
- One page carries the argument, the inline template, the current scoreboard and a changelog.
- A small **public git repo** is the source: the template, an append-only experiment log, public-safe BOMs, and sources.
- Why: commit timestamps prove each prediction was recorded before its outcome, which is the thesis applied to the page.
- Fallback: the page plus Media Library downloads (the Slaughter model).

**Decision (proposed):**
- One stable page, `/why-is-telemetry`.
- v0.1 carries the one-screen argument, the try-it kit, the experiment log, a short long-form cut, and the BOM downloads.
- It is refreshed quarterly on scoring day, plus event triggers.

**Rejected alternatives:**
- A Slaughter-sized package (13 PDFs and a deck). Too much before any evidence of use.
- Column only. The close would ask readers to use a template we don't publish, and "going first" would happen nowhere visible.

**Expected outcome:** at least one person outside CSA uses the template within 90 days of launch, and the first scoring day happens on time.
**Check by:** 90 days after launch. First scoring day: 2026-12-15 (Kurt to adjust).

**Risk to watch:** Kurt's own insight that "goals decay in the direction that flatters". A living page that stops being scored becomes the stale document the column warns about, so scoring day needs a real reminder (calendar entry or scheduled agent), not good intentions.

## C20 - Direction: idea → column → public research repo → plugin (a pilot, not a standard)

**Origin:** Kurt, 2026-09-28 ("what if we have the 'backend' research repo publicly, and then cut a plugin in csa-plugins-official and make that part of the standard")
**Disposition:** `open`. The direction is recorded; the structural question is parked until 2-3 pieces have run it.

**The ladder:**

| Layer | Purpose | This piece |
|---|---|---|
| Idea | seed | the root `TODO.md` line |
| Column | *read it* | Circle News |
| Public research repo | *check it* | template, append-only experiment log, public-safe BOMs, sources |
| Plugin (csa-plugins-official) | *do it* | a skill to record intent, evidence and expected outcome before a consequential decision, plus a scoring command |
| Labs page | front door | a short page linking the rest |

**Why:**
- It is Writing 2.0 made literal: the plugin *is* the changed practice.
- Installs, issues and scored entries become telemetry on whether the column's advice works.

**Cautions:**
- Gate the plugin layer: only for pieces that prescribe a repeatable practice an AI can carry out.
- Plugins need an owner and a retirement condition.
- Keep one source of truth. The template and log are born public, so the timestamps mean something. The research is exported from the private packet via a publishing manifest and a public-safety check.
- No ADR until the pilot shows results.
- Plugin design follows the column's rules: capture before the outcome, never grade the rationale, a skill plus a command rather than forced hooks.

**Refinement (Kurt, 2026-09-28):** one public **`CloudSecurityAlliance/CINO-Research`** repo with a folder per idea, not a repo per idea.
- CINO-Writing is the private workshop and CINO-Research is the public shelf. Research is exported at milestones; experiment logs are born public.
- One public-safety guard, one license, one index with per-idea status labels (seed / column / research / plugin).
- A large idea can split out into its own repo later.
- Plugins stay in `csa-plugins-official` and link back.
- The name was free as of 2026-09-28.

**Second candidate (reviewed 2026-09-28):** CSA's internal MCP-server engineering research.
- It already has the same ladder built in: research, then a planned skill, then a plugin.
- Much of it is about public servers and vendor behaviour, and its individual experiments are already public in the server repos.
- Curate it; don't mirror it. Internal system designs and tenant-derived data stay private.
- If adopted, it is the ladder's second pilot.

**Created 2026-09-28:** https://github.com/CloudSecurityAlliance/CINO-Research. It has one folder per topic, a root README and CLAUDE.md, YAML front matter per topic README, and no meta folder (Kurt). The experiment log and the decision-record template are born there; this packet is exported to it.

**Open:**
- the plugin name;
- where the plugin lives: public `csa-plugins-official` (proposed) or an internal marketplace;
- pilot vs standard.

**Expected outcome:** by the 2026-11-15 scoring date, the repo exists with at least the column's own predictions scored, and the plugin is at least designed. Standardizing the ladder is decided after 2-3 pieces, not before.
**Check by:** 2026-11-15.

## C21 - draft-03: cut the Karvetski sentence; correct the four-times count

**Origin:** Kurt's read of draft-02, 2026-09-28
**Disposition:** `completed`

- **The Karvetski result is cut from the column** (Kurt: option A). It measures reasoning *text* to predict accuracy, which is not the column's loop of writing down the expected outcome and scoring it against what happened. Next to Beat 8's "never grade the reasoning itself" it read as a contradiction, and only its abstract had been verified. It stays in the source sweep and KnowledgeBOM H5.
- **The four-times sentence is corrected** to its traced scope: one day, one server (KnowledgeBOM G2).

**Rejected alternatives:**
- Keep Karvetski with a "measured, not rewarded" clause. Accurate, but it adds words to the densest paragraph.
- Attribute "four times" to the four MCP servers (Kurt's first hypothesis). The logs show it began as a same-branch tally.

**Expected outcome:** no reader flags an internal contradiction between Beats 5 and 8. **Check by:** 2026-11-15, against reader feedback.

## Decisions against ledger

| Rejected idea | Disposition | Reason |
|---|---|---|
| Make RSI the headline | `rejected` | Too narrow and speculative for Circle News |
| Full design-dimensions framework in the column | `rejected` | Belongs on Labs |
| Power tools as third historical analogy | `parked` | Good, but electricity/computers are enough |
| Treat rationale as ground truth | `rejected` | Rationale is evidence to test, not truth |
| Universal 3-6 iteration claim | `rejected` | Personal observation only |
| Self-reference throughout | `rejected` | The article process is a useful example, not the subject |
| Internal operational examples in public material | `rejected` | Kurt, 2026-09-25: sanitized for public release; not needed for the argument |
| Cite Foundation Capital's "context graphs" by name | `rejected` | Kurt, 2026-09-24: use the 55-year lineage plus "resurfaced with AI" instead of anchoring on a VC thesis |

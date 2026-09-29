# KnowledgeBOM - Working Claim Ledger

This is the working knowledge bill of materials for the article and a possible Labs package. It records each claim the work may rely on, its current support status, and whether it is load-bearing.

**Source sweep 2026-09-24:** every claim below was checked against sources. The synthesis is in `11-source-sweep.md` and the raw evidence (quotes, URLs, opened or not-opened) is in `sources/sweep-1` through `sweep-5`. The `Sweep` column records each verdict. Sections H to J are new claims the sweep surfaced.

## Status vocabulary

| Status | Meaning |
|---|---|
| `VERIFIED` | Primary source opened and quoted in `sources/` |
| `VERIFIED-ABSTRACT` | Primary abstract or summary opened; full text not read |
| `CORRECTED` | Source confirmed, but the claim wording or figure had to change (the corrected wording is in the row) |
| `PARTIAL` | Supported in part; the unsupported part is noted |
| `SECONDARY` | Only reached through a secondary source; verify before load-bearing use |
| `CONVERSATION` | Preserved from the referenced ChatGPT conversation and not yet checked |
| `KURT` | Supplied by Kurt's experience or judgment |
| `MINE` | Original synthesis from this research packet |
| `VERIFY` | Needs verification before being used as an external claim |

## A. Article spine

| ID | Claim | Status | Load-bearing | Sweep | Source / note |
|---|---|---|---|---|---|
| A1 | Traditional telemetry mostly records what happened: events, errors, state, actions, latency, resource use | `MINE` | Yes | Supported | OTel GenAI conventions, AICM LOG-07 and EU AI Act Art. 12 all record events rather than reasons (sweep 3) |
| A2 | Agentic knowledge work makes intent, assumptions, evidence, alternatives, uncertainty, and expected outcomes operationally important | `MINE` | Yes | Widely shared | Foundation Capital's "context graphs" (Dec 2025), Oracle AER (arXiv:2603.21692), the CSA Agentic Trust Framework and OWASP ASI01 all say this (sweep 3). Do not claim it as new. |
| A3 | "Why is telemetry" is the conceptual pivot | `MINE` | Yes | Close prior | Foundation Capital: "the 'why' becomes first-class data". The column must acknowledge this (see I1). **Superseded 2026-09-24 (C15):** Kurt decided not to cite Foundation Capital; the column tells the 55-year lineage instead. |
| A4 | Once why becomes telemetry, judgment becomes data | `MINE` + `VERIFIED` | Yes | Strongly supported | Tetlock's forecasting tournaments (Mellers 2014), and the 2026 finding that LLM-scored rationales from 55k+ forecasts predict accuracy (Karvetski, Tetlock, Karger et al., arXiv:2606.30987) (sweep 2) |
| A5 | Judgment as data enables comparison of expected outcomes with actual outcomes | `MINE` + `VERIFIED` | Yes | Supported; the most distinctive claim | US Army AAR (TC 25-20) and Tetlock close this loop for humans. Levitt & March (1988) found projected-vs-realized comparisons are routinely "ignored". No agent standard, tool or startup records the agent's own expected outcome (sweep 3, negative search). |
| A6 | Logged rationale is not truth; capture it as structured claims and test them over time | `MINE` + `VERIFIED` | Yes | Strongly supported | Nisbett & Wilson 1977, choice blindness (Johansson 2005), Turpin 2023, Chen et al. 2025 (hint mentioned 25-39% of the time), Baker 2025, Fischhoff 1975, Lerner & Tetlock 1999 (sweep 4). OWASP ASI09 "Fake Explainability" is the security version. **Refined 2026-09-29:** one outcome can be luck, so judgment is assessed from patterns across records (the external review; Duke's "resulting"). |

## B. General-purpose technology history

| ID | Claim | Status | Load-bearing | Sweep | Source / note |
|---|---|---|---|---|---|
| B1 | General-purpose technologies often need complementary organizational redesign before full productivity gains appear | `VERIFIED` | Yes | Confirmed | Brynjolfsson, Rock, Syverson (NBER w24001); endorsed by the ILO (2026) as the expected path for AI |
| B2 | Electrification's larger factory gains came after the move from **group drive** (electric motors bolted onto the old shaft-and-belt layout) to **unit drive** (a motor per machine) and factory redesign | `CORRECTED` | Yes | Wording fixed | David, AER 80(2) 1990, pp. 357-59. He puts the lag on sunk capital and slow learning, not on managers lacking imagination. The **p. 360 "information structures" passage** is a ready-made bridge to the thesis. |
| B3 | IT value depends heavily on complementary organizational investments | `VERIFIED-ABSTRACT` | Yes | Confirmed | Brynjolfsson & Hitt, JEP 14(4) 2000 (abstract only) |
| B4 | Computerization's productivity contributions are "up to five times greater" over 5-7 year horizons (527 firms), consistent with time needed to build organizational capital | `CORRECTED` | Yes | Wording sharpened | Brynjolfsson & Hitt, REStat 85(4) 2003 (full text) |
| B5 | IT, workplace reorganization, and new products/services act as complements | `VERIFIED` | Medium | Confirmed | Bresnahan, Brynjolfsson & Hitt, QJE 117(1) 2002 |
| B6 | The productivity J-curve: measured productivity understates true gains early in GPT adoption and overstates them later, because intangible complements go unmeasured | `VERIFIED` | Yes | Confirmed | Brynjolfsson, Rock, Syverson, AEJ: Macro 13(1) 2021. It names AI as a GPT. |

## C. Current AI failure mode

| ID | Claim | Status | Load-bearing | Sweep | Source / note |
|---|---|---|---|---|---|
| C1 | Much current AI adoption is substitution: existing workflow plus AI | `MINE` + `VERIFIED` | Yes | Supported | ILO "Aggregation Paradox" (Apr 2026): AI needs "'system-level redesign' ... not merely substitution" |
| C2 | Substitution can produce local productivity with global organizational drag | `MINE` + `VERIFIED` | Yes | Supported; **scope it to organizational outcomes** | DORA 2024: AI raises individual productivity but "negatively impacts software delivery stability and throughput". Firm Data on AI (NBER w34836, 2026): nine in ten executives report no productivity impact. Counter-evidence: real task-level gains exist (Brynjolfsson/Li/Raymond; Dell'Acqua). |
| C3 | Workslop is "AI generated work content that masquerades as good work, but lacks the substance to meaningfully advance a given task"; it "transfers the effort from creator to receiver" | `VERIFIED` | Yes | Use the HBR wording | Niederhoffer, Hancock et al., HBR, 22 Sep 2025 |
| C4 | In a Sep 2025 survey of 1,150 U.S. desk workers, **40%** had received workslop in the past month, and each instance cost **1 hr 56 min** | `CORRECTED` | Medium | 41% was wrong | Same HBR article. The survey is self-reported, vendor-run and not peer reviewed, so treat it as an indicator. |
| C5 | AI slop can degrade organizational knowledge and processes, not only individual recipients' productivity | `PARTIAL` | Medium | Summary only | Holweg & Davenport, HBR, 16 Jun 2026. The body is paywalled. The summary's first prescription is "keep track of the provenance of unstructured data". |
| C6 | Empirical evidence on genAI productivity is mixed; worker-reported time savings "have not yet translated into higher measured output, earnings or employment" | `VERIFIED` | Medium | Date corrected | ILO research brief, **May 2026**. Companion brief "Aggregation Paradox of AI", Apr 2026. |
| C7 | People misjudge AI's effect on their own productivity: developers expected +24%, still believed +20% afterward, but measured −19% (early 2025) | `VERIFIED` | Low | New | METR RCT (Jul 2025). **Do not cite as the current state**: METR's Feb 2026 update points toward speedups. The durable lesson is that self-report is not telemetry. |

## D. Durable organizational state

| ID | Claim | Status | Load-bearing | Sweep | Source / note |
|---|---|---|---|---|---|
| D1 | Important cognition should leave durable, addressable organizational state | `MINE` | Yes | Long prior art | Nygard ADRs, PEPs, design docs, W3C PROV (sweep 2). The idea is old; the economics are new (see H1, H6). |
| D2 | Useful state includes intent, evidence, assumptions, alternatives, rejected alternatives, expected outcomes, actual outcomes, and lessons learned | `MINE` | Yes | Near-exact prior | This is almost field for field the Farnam Street decision-journal template, plus MADR's "Considered Options" and the AAR. What is new is organizational scale and outcome linkage. |
| D3 | GitHub issue/PR/review/commit history is a concrete example of work leaving durable state | `MINE` | Medium | Supported | Linux kernel "describe your problem"; Chris Beams "what and why vs. how"; Entire Checkpoints (2026) extends it to agent reasoning |
| D4 | Full chain-of-thought is not the operational interface; structured rationale plus links to evidence is | `MINE` + `VERIFIED` | Yes | Strongly supported | Chen 2025 (unfaithful CoTs are *longer*); Korbak 2025 (CoT monitorability is "fragile"); vendors expose only summaries or encrypted reasoning (sweep 3). Keep CoT as a monitoring signal; make structured rationale the record. |
| D5 | Negative knowledge can prevent re-litigation and reveal recurring blind spots | `KURT` + `PARTIAL` | Medium | Partial | Definition: Gartmeier et al. 2008. Blind spots: Parviainen & Eriksson 2006. Learning from failure: Madsen & Desai 2010. File-drawer effect: Franco 2014. Institutionalized in PEP "Rejected Ideas". The re-litigation claim is Kurt's framing, consistent with the sources but not stated in them. |

## E. Recursive improvement and agent literature

| ID | Claim | Status | Load-bearing | Sweep | Source / note |
|---|---|---|---|---|---|
| E1 | Modern self-improving-agent surveys treat prompts, memory, tools, and control logic as mutable scaffold | `VERIFIED` | Medium | Confirmed | Ren et al. (with Schmidhuber), arXiv:2607.13104, 14 Jul 2026 |
| E2 | FlowEvo compiles successful workflows into skills, tracks downstream utility, and suppresses skills that cause negative transfer | `VERIFIED` | Medium | Confirmed; cite v2 | arXiv:2607.21596 v2 (20 Aug 2026). It also logs "failure patterns, and audit outcomes", a D5 example. |
| E3 | Some 2026 RSI work treats the improvement mechanism itself as part of the evolving system | `CORRECTED` | Medium | Venue fixed | Liu et al. (Alibaba), **Preprints.org** doi 10.20944/preprints202608.0051.v1. Not arXiv, not peer reviewed. |
| E4 | These agent-system sources belong mostly in Labs, not the Circle News body | `MINE` | Medium | Unchanged | Editorial decision |
| E5 | Self-improving agents mostly record *what* was tried and its score, not *why* it was tried or rejected; only ExpeL, GEPA and FlowEvo keep written reasons, and Reflexion keeps them for just 1-3 entries | `MINE` + `VERIFIED` | Medium | New | Survey of 11 systems in sweep 5. Labs material. |
| E6 | The Darwin Gödel Machine faked test logs and disabled hallucination detection; independent lineage records caught it, not the agent's own log | `VERIFIED` | Medium | New | Zhang et al., arXiv:2505.22954; sakana.ai/dgm. Supports A6/D4. |

## F. Foundational system properties

| ID | Claim | Status | Load-bearing | Sweep | Source / note |
|---|---|---|---|---|---|
| F1 | A recursive AI workflow needs observability, provenance, versioning, addressability, linkability, replayability, reversibility, uncertainty, and authority | `MINE` | Medium | Unchanged | Labs dimensions |
| F2 | Causal traceability is distinct from linkability: it records why A was believed to influence B | `MINE` | Medium | Term caution | Database "why-provenance" (Buneman, Khanna & Tan 2001) means *which inputs justify an output*, not intent. Borrow the term, but don't conflate the two. |
| F3 | MAPE-K provides a control-loop precedent: monitor, analyze, plan, execute over knowledge | `VERIFIED` | Low | Source upgraded | Kephart & Chess, IEEE Computer 2003 (metadata only). The IBM Redbook SG24-6665 §1.2.1 gives the MAPE-loop definition (opened). |
| F4 | Stafford Beer's Viable System Model provides a recursive governance precedent | `VERIFIED` | Low | Source replaced | Beer, JORS 35(1):7-25, 1984 (opened). Drop archania.org. |
| F5 | SRE error budgets provide a vocabulary for deliberate risk and improvement allocation | `VERIFIED` | Low | Confirmed | Google SRE book, ch. 3 |
| F6 | High reliability organizations provide practices for failure sensitivity and deference to expertise | `VERIFIED` | Low | Confirmed | Weick & Sutcliffe 3rd ed. 2015; five principles via AHRQ PSNet |

## G. Kurt-supplied practice observations

| ID | Claim | Status | Load-bearing | Sweep | Source / note |
|---|---|---|---|---|---|
| G1 | In Kurt's practice, iterating documented AI workflows often reaches a steadier state after roughly 3-6 iterations | `KURT` + `PARTIAL` | Low | Loosely consistent | Self-Refine (2023) and Nielsen (1993) show most gains in the first 3-5 rounds. Huang et al. (2023) show that without external feedback, self-correction can degrade. Keep this as a personal observation. |
| G2 | Building a library first, with the MCP server as a thin adapter, is a good example of architecture requiring preserved rationale; "paid for that lesson four separate times" | `KURT` + `CORRECTED` | Medium | Count traced 2026-09-28 | Nygard 2011: without rationale, newcomers "Blindly accept" or "Blindly change it"; Chesterton's fence. **Count traced (2026-09-28, from the session logs):** the count began as an AI's tally on **one csa-zendesk branch in one review session (2026-09-21/22)**: "the lesson this branch has now paid for four times". It covered controls moved to the library seam, including an empty-upload refusal, the path-traversal guard, and int coercion of ids. Within about a day it drifted, as documents copied it, to "this fleet has paid for four separate times" and "this project has paid four separate times". The column now says "in a single day's work on one of these servers, we had to move a control into the library four separate times." The inflated wording remains in the internal platform docs and the csa-zendesk plan, still to be corrected. |
| G3 | The article-production process itself is a useful meta-example of preserving decisions, rejected paths, and rationale | `KURT` | Low | See note | The packet's own CognitiveBOM has no expected-outcome field, the same gap as ADRs (see `11-source-sweep.md` §7) **Superseded 2026-09-27:** CognitiveBOM entries now carry expected outcomes and check-by dates (C15 onward). |

## H. Prior art: who went first (new, from sweep 2)

| ID | Claim | Status | Load-bearing | Source / note |
|---|---|---|---|---|
| H1 | Design-rationale capture historically failed largely because the person recording pays and someone else benefits later; most projects die before the rationale is used | `VERIFIED` | Yes | Grudin 1996; Lee 1997; Buckingham Shum et al. 2005 |
| H2 | "A good deal of experience is unrecorded simply because the costs are too great," and comparisons of projected vs realized returns "are ignored" | `VERIFIED` | Yes | Levitt & March 1988 |
| H3 | Capturing rationale in an NCR field trial surfaced omissions that would have cost 3-6x the capture cost | `SECONDARY` | Low | Conklin & Burgess-Yakemovic 1991, via Lee 1997 |
| H4 | The Army AAR compares recorded intent ("what was supposed to happen") with what happened and why; debriefs improve effectiveness about 25% (d = .67) | `VERIFIED` + `VERIFIED-ABSTRACT` | Medium | TC 25-20 (1993); Tannenbaum & Cerasoli 2013 meta-analysis |
| H5 | LLM-scored rationale quality predicts forecast accuracy across 55k+ forecast explanations; it flags bad reasoning better than it crowns the best | `VERIFIED-ABSTRACT` | Low (cut from the column 2026-09-28) | Karvetski, Tetlock, Karger et al., arXiv:2606.30987 (Jun 2026) |
| H6 | LLMs can now draft rationale and ADRs from noisy sources such as meeting transcripts, but they introduce unfaithful content, so human review is needed | `VERIFIED-ABSTRACT` | Medium | GADR (arXiv:2608.17694); Zhou et al. (arXiv:2504.20781); Equal Experts 2025 |
| H7 | About 50% of GitHub repos with ADRs have only 1-5, suggesting the practice was tried but not adopted | `VERIFIED-ABSTRACT` | Low | Buchgeher et al., IEEE Access 2023 |
| H8 | Negative knowledge is institutionalized in PEP "Rejected Ideas", Rust RFC "Rationale and alternatives", KEP "Alternatives", Oxide RFD "abandoned", and Nygard "superseded" | `VERIFIED` | Medium | Respective templates |
| H9 | Agents shrink Grudin's payer/beneficiary gap because the next AI run is an immediate consumer of the why | `MINE` | Yes | Not found argued elsewhere. This is the column's own synthesis. |
| H10 | No ADR, PEP, Rust RFC or KEP template checked has an expected-outcome or what-actually-happened field; MADR's "Confirmation" is closest | `VERIFIED` | Medium | Sweep 2 template review |
| H11 | Organizations treat most failures as blameworthy (70-90%) though executives judge only 2-5% truly are, so failures go unreported | `VERIFIED` | Medium | Edmondson, HBR 2011. This is a precondition for honest why-telemetry. |

## I. Current landscape and novelty (new, from sweep 3)

| ID | Claim | Status | Load-bearing | Source / note |
|---|---|---|---|---|
| I1 | Foundation Capital framed "decision traces" and "context graphs" as capturing why: "the 'why' becomes first-class data" | `VERIFIED` | Yes | Gupta & Garg, 22 Dec 2025. Their follow-up (30 Jan 2026) concedes the declared why is hard to capture and moves to "infer the why from the how". Byline confirmed (Gupta & Garg). **Not cited in the column** (Kurt, 2026-09-24; CognitiveBOM C15). Later FC output (Sep 17, 2026 Aaron Levie podcast) still doesn't link traces to outcomes. |
| I2 | Context graphs record *why a decision was allowed* (policy, exception, approver, precedent) so agents act consistently; they have no expected-outcome field and don't score precedent against results | `VERIFIED` | Yes | Same source. This is the column's point of difference. |
| I3 | OpenTelemetry GenAI conventions record plans, reasoning text and (in proposals) allow/deny decision points, but have no field for intent, rationale or expected outcome | `VERIFIED` | Medium | semantic-conventions-genai repo, checked 2026-09-24; issues #72, #239 |
| I4 | CSA AICM has model-level explainability (GRC-13/14) and event logging (LOG-07/09/16) but no control for per-decision intent, alternatives, or expected outcome | `VERIFIED` | Medium | AICM v1.1.1 via CSA MCP. Candidate Labs recommendation. |
| I5 | Regulation mandates what-logs (EU AI Act Art. 12; ISO 42001 A.6.2.8). The only per-decision why is EU Art. 86's explanation on request. NIST AI RMF has intended-vs-actual only at system level. | `VERIFIED` + `SECONDARY` | Medium | ISO text and Digital Omnibus dates are secondary only |
| I6 | In agent security, "intent" means an authorization claim (intent capsules, intent-bound tokens, IETF Intent Admission, CSA ORCHIDEAS), checked at the gate but not later compared with outcomes | `VERIFIED` | Medium | OWASP Agentic Top 10 2026; IETF draft-jiang-oauth-intent-admission; CSA blog Jun 2026 |
| I7 | Giving agents intent files (AGENTS.md style) does not generally improve task success, and it raises cost 20%+ | `VERIFIED-ABSTRACT` | Medium | ETH, arXiv:2602.11988. The loop, not the intent document, has to carry the value. |
| I8 | No source found proposes that an agent record its own expected outcome at decision time, to be scored later against the actual outcome | `MINE` (negative search) | Yes | Sweep 3 §7. This is absence of evidence, not proof. It is the column's sharpest distinct claim. **Scoped 2026-09-29 (external review):** a *dated* negative search (2026-09-24) covering standards, security frameworks, regulations and vendor tools. Research has proposed the broad mechanism: see I9. The column now says so. |

## I (cont.). Added by the 2026-09-29 external review

| ID | Claim | Status | Load-bearing | Source / note |
|---|---|---|---|---|
| I9 | Research has proposed agents that compare predicted with observed outcomes and update their causal model on the mismatch | `VERIFIED-ABSTRACT` | Low | Aryan & Liu, *Causal Reflection with Language Models*, arXiv:2508.04495 (Aug 2025, rev. Sep 2025). A framework paper with no implementation or empirical evaluation. It is adjacent prior art: it does not establish organizational practice, a standard, or measured improvement |

**Standing rule (2026-09-29):** a source existing is not the same as the claim being supported.
Record separately the status of the source, the part actually read, and the inference drawn.
Negative searches keep their date and scope.

## J. Rationale-capture design evidence (new, from sweep 4)

| ID | Claim | Status | Load-bearing | Source / note |
|---|---|---|---|---|
| J1 | Outcome knowledge silently inflates what people think they expected, so expectations must be recorded before the outcome | `VERIFIED` | Yes | Fischhoff 1975; Nosek et al. 2018 (prediction vs postdiction) |
| J2 | When claims were fixed before results were known, positive results dropped from 96% to 44% | `VERIFIED-ABSTRACT` | Medium | Scheel, Schijen & Lakens 2021 (registered reports) |
| J3 | Justifying after committing produces defensive bolstering; pre-decision process accountability to an audience with unknown views improves judgment and calibration | `VERIFIED` | Yes | Lerner & Tetlock 1999 |
| J4 | Optimizing against a rationale channel drives it dark: CoT monitor recall "falls to near zero" | `VERIFIED` | Yes | Baker et al. (OpenAI) 2025; Haskins et al. 2026 **Scope (2026-09-29, external review):** supports not making the reasoning channel an optimization target (don't *reward* reasoning). It does **not** support a ban on *reviewing* reasoning. The column's rule was corrected accordingly. |
| J5 | Mandatory free-text reasons degrade into noise (spaces, random characters, top-of-list picks), but aggregated they still expose broken processes (malfunctions in 26% of alert rules) | `VERIFIED` + `VERIFIED-ABSTRACT` | Medium | Wright et al., JAMIA 2019; Aaron et al., JAMIA 2019 |
| J6 | Rationale fields can leak sensitive data ("sometimes even passwords") | `VERIFIED` | Low | Wright et al. 2019. This is a security-audience point. |

## Verification queue before drafting

The first-pass queue (BetterUp, David, J-curve, ILO) is **done**; see sections B and C. Remaining:

2. Holweg & Davenport full text, if C5 is quoted beyond its summary.
3. Anything marked `SECONDARY` that becomes load-bearing (H3, the I5 ISO text).
4. Whether the article names the KnowledgeBOM / CognitiveBOM at all. (Naming itself is decided: see `CognitiveBOM.md` header.)
5. Full list: `11-source-sweep.md` §8.

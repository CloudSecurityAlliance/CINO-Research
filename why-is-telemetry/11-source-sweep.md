# Source Sweep: who else is saying this, and does it hold?

**Run:** 2026-09-24. Five parallel research sweeps, one per claim cluster. Each sweep opened
primary sources where possible, quoted them, and labelled everything it could not open.
**Raw evidence:** `sources/sweep-1` to `sweep-5` (full quotes, URLs, and opened / not-opened
status for every source). This file is the synthesis. `KnowledgeBOM.md` carries the per-claim verdicts.

**Question Kurt asked:** for every claim, find sources or other people talking about it. The
piece is a thought experiment, but a testable one (start logging intention and see if it is
useful). Someone has to go first.

**Short answer:** many people went first *for humans*, over 55 years, and mostly stalled. For
*AI agents*, the "capture why" half of the thesis is now crowded. The "record what you expected,
then score it against what happened" half appears to be open.

---

## 1. Headline findings

1. **No hallucinated citations.** Every source carried over from the ChatGPT conversation
   exists, including the four arXiv/preprint IDs, and supports its claim. Several need fixing
   (section 2).
2. **The pivot line has a close prior.** Foundation Capital (Jaya Gupta and Ashu Garg, "AI's
   trillion-dollar opportunity: Context graphs," 22 Dec 2025): *"Once you have decision records,
   the 'why' becomes first-class data,"* and incumbent systems *"can tell you what happened, but
   ... can't tell you why."* A named VC category ("context graphs," "decision traces") and a
   public debate followed. **The column must acknowledge this or read as derivative** to anyone
   following enterprise AI.
3. **What nobody records yet is the expected outcome.** A negative search across standards
   (OpenTelemetry GenAI conventions, OWASP Agentic Top 10, CSA AICM, EU AI Act, ISO 42001),
   tools (Langfuse, Braintrust), startups (Foundation Capital's portfolio, Entire, Cursor Agent
   Trace), and research (Oracle's AER schema) found **no one proposing that an agent record its
   own prediction at decision time, to be joined later to the actual outcome and scored.** ADR,
   PEP, Rust RFC and KEP templates also lack an expected-vs-actual field. The two practices that
   *do* close this loop, the US Army After Action Review and Tetlock's forecasting tournaments,
   are among the best-evidenced learning practices in the whole sweep.
4. **The strongest "this is not new" case is also the column's best "why now" argument.**
   Design-rationale capture (IBIS 1970 → QOC/gIBIS 1991 → Compendium 2005 → ADRs 2011) failed
   mainly on *economics*, not format. Grudin (1996): the person recording pays, someone else
   benefits later, and most projects die first. Levitt & March (1988): *"a good deal of experience
   is unrecorded simply because the costs are too great,"* and *"comparisons between projected
   and realized returns ... are ignored."* AI moves those economics (section 4).
5. **The evidence makes "rationale is not truth" a set of design rules, not just a caveat.**
   Capture before the outcome, use structured claims, score against outcomes, and never grade the
   rationale itself (section 5).

---

## 2. Corrections the draft must carry

| Claim | Was | Should be | Source |
|---|---|---|---|
| C4 | "41 percent encountered workslop" | **40%** received workslop in the past month; **1 hour 56 minutes** per instance; N=1,150 U.S. desk workers, Aug-Sep 2025, self-reported, vendor-run, not peer reviewed. (41% appears only in HBR's summary blurb and cost math; in BetterUp's PDF, 41% is a different statistic.) | Niederhoffer, Hancock et al., HBR, 22 Sep 2025 |
| C3 | BetterUp blog definition | Use HBR: *"AI generated work content that masquerades as good work, but lacks the substance to meaningfully advance a given task"*; it *"transfers the effort from creator to receiver."* | same |
| B2 | steam replaced by "central electric drive" | The intermediate stage was **group drive** (motors bolted onto the old shafting). Do **not** claim managers lacked imagination. David blames sunk capital and slow, decentralized learning. | David, AER 1990, p. 357 |
| B4 | "larger over 5-7 years" | "up to five times greater over five-to-seven-year horizons," 527 firms | Brynjolfsson & Hitt 2003 |
| C6 | "ILO 2026" | ILO research brief dated **May 2026**; the companion "Aggregation Paradox" brief (Chan & Shedania) is **April 2026** | ILO |
| E2 | FlowEvo arXiv 2607.21596 | Cite **v2, 20 Aug 2026** (v1 date shown as 18 Apr 2026 conflicts with the 2607 ID) | arXiv |
| E3 | "Path to RSI Agents" | **Preprints.org** preprint (doi 10.20944/preprints202608.0051.v1), Alibaba, **not arXiv, not peer reviewed** | self-improving-agent.com |
| F3 | IBM Redbook SG24-6665 | Real but a 2005 toolkit manual. Cite Kephart & Chess 2003 for the vision, and the Redbook only for its MAPE-loop definition. | sweep 5 |
| F4 | archania.org | Replace with Beer 1984, *JORS* 35(1):7-25 (opened) | sweep 5 |
| Humlum & Vestergaard | "Large Language Models, Small Labor Market Effects" | Retitled **"Still Waters, Rapid Currents"** (rev. March 2026) | NBER w33777 |

**Do not cite, or cite only with the caveat stated:**

- METR's "19% slower" is early-2025 only. METR's Feb 2026 update points toward speedups and calls its own data unreliable. Use the perception gap instead: developers expected +24% and still believed +20% while measured −19%.
- MIT NANDA "95% of pilots get zero return": thin method (52 interviews plus a conference survey).
- Haidt's moral dumbfounding: a 2015 re-test measured the effect at about 0.
- The premortem "30% more accurate" figure: the underlying study counted *more* reasons, not better ones.
- Tetlock's *training* effect size: a 2025 re-analysis says it shrinks or reverses. Forecast *scoring* is solid.
- Kahneman's "cheap notebook" decision-journal quote: found only on secondary blogs.
- Holweg & Davenport HBR 2026: the body is paywalled, so quote only from its summary.

---

## 3. Who else is talking about this (the landscape)

### Already covered by others (do not claim as new)

- **"Systems record what, not why; agents make why capturable."** Foundation Capital's context
  graphs (Dec 2025). A Forrester analyst (Charles Betz, Apr 2026) already called it *"a
  convergence, not an invention."*
- **"Intent is the real artifact, and we throw it away."**
  - Sean Grove (OpenAI), "The New Code," 2025: *"you shred the source and then very carefully version control the binary."* Quote is secondary (via Tessl); the talk was not watched.
  - GitHub Spec Kit: *"intent is the source of truth."*
  - Kiro specs, AGENTS.md, CLAUDE.md.
- **"Capture the agent's reasoning durably."**
  - Entire, the startup Thomas Dohmke (ex-GitHub CEO) launched Feb 2026 on a $60M seed. Its "Checkpoints" saves agent *"reasoning, prompts, and decisions"* on every commit.
  - CSA's own Agentic Trust Framework blog (Feb 2026): *"Ability to retrieve rationale for agent decisions."*
- **A structured schema for intent, evidence and rejected alternatives.** Oracle's Agent Execution
  Record (arXiv:2603.21692, Mar 2026) has `alternatives_rejected` with reasons. Its evaluation is
  still only planned.
- **"Rationale is not truth."**
  - OWASP Agentic Top 10 2026, ASI09: *"Fake Explainability: The agent fabricates convincing rationales."*
  - Foundation Capital's own follow-up concedes *"you can't actually capture the why"* and retreats to *"infer the why from the how."*

### What the column can still claim

1. **Log the prediction, not just the permission.**
   - In current security and standards work, "intent" means an authorization claim: intent capsules, intent-bound OAuth tokens, IETF Intent Admission, CSA ORCHIDEAS intent tokens. It is checked at the gate and then discarded.
   - "Expected" in eval tools (Braintrust) is evaluator ground truth, not the agent's own forecast.
2. **Correction, not consistency.**
   - Context graphs turn past decisions into precedent: act as we acted before.
   - The column wants to learn which judgments were *wrong* and change the process.
   - Foundation Capital's follow-up names "connect actions to outcomes" as the next step, which confirms the gap is recognized and unfilled.
3. **Organizational learning, not audit, security or a moat.** Every existing treatment of "why" serves one of these other purposes:
   - forensics (EU AI Act Art. 12, AICM LOG controls, OWASP);
   - authorization;
   - safety monitoring (chain-of-thought monitorability);
   - debugging;
   - a commercial system of record.
4. **Declared and tested, not inferred.**
   - Human intent is hard to observe, which is why Foundation Capital retreated to inference.
   - An agent can be *required* to state intent, assumptions and an expected outcome cheaply, as structured output.
   - Those statements are then tested against actions and outcomes. This answers both Foundation Capital's "you can't capture why" and OWASP's "rationales can be faked."
5. **Recurring rejection as a signal.** Rejected alternatives appear in AER, OTel proposal #72 and
   practitioner ADR templates. Tracking *recurrence* of rejected ideas ("repeated rejection is
   itself telemetry") was found nowhere.

**Suggested honest framing (sweep 3, for Kurt to accept or reject):**

> Investors are already calling decision traces AI's next trillion-dollar layer, and coding tools
> already save the agent's reasoning with every commit. What almost no one records yet is the part
> that makes judgment learnable: what the agent expected to happen, and whether it did.

### CSA-specific finding

- AICM v1.1.1 has explainability controls (GRC-13, GRC-14), but they cover model-level explainability of the SHAP/LIME kind.
- Its logging controls (LOG-07, LOG-09, LOG-16) are what-logs: security events and lifecycle metadata.
- **No AICM control asks for per-decision intent, alternatives, or expected outcome, or compares
  them with outcomes.** This is a concrete, CSA-owned gap. It is a candidate Labs recommendation or
  AICM contribution, not a column claim unless Kurt wants to name it.

### Regulation in one line

- Regulation mandates *what*: EU AI Act Art. 12 logs, ISO 42001 A.6.2.8.
- The only per-decision *why* is EU Art. 86: an explanation for an affected person, produced on request. That is post-hoc by design.
- NIST AI RMF has the intended-vs-actual loop (MAP 1.1 / MEASURE 4.2), but only at *system* level. The column argues for pushing that loop down to the individual judgment.

---

## 4. "Someone has to go first": who did, and what they learned

**Who went first, for humans:**

| Practice | What it captures | What happened |
|---|---|---|
| Design rationale (IBIS 1970, QOC, gIBIS, Compendium) | issues, options, criteria, arguments | Largely failed on capture cost and the payer/beneficiary mismatch (Grudin 1996). One bright spot: the NCR field trial surfaced omissions that would have cost 3-6x the capture cost (secondary, via Lee 1997). |
| ADRs (Nygard 2011, MADR) | context, decision, consequences, superseded status | ThoughtWorks "Adopt" by 2017, but about half of GitHub repos with ADRs have only 1-5 (Buchgeher 2023): tried, not sustained. |
| PEP "Rejected Ideas," Rust RFC "Rationale and alternatives," KEP "Alternatives," Oxide RFD "abandoned" | negative knowledge, institutionally required | Works where a gatekeeper enforces it. Same pattern for the Linux kernel's rule to "describe your problem." |
| Decision journals (Farnam Street, Annie Duke) | the column's D2 list almost field for field, including expected outcome with probabilities | Individual only; not shared, queryable or aggregated. |
| US Army AAR (TC 25-20, 1993) | "what was supposed to happen" vs "what happened" vs why | Works *because intent was recorded before execution* (commander's intent). Debrief meta-analysis: about 25% effectiveness gain, d = .67 (Tannenbaum & Cerasoli 2013). |
| Tetlock / Good Judgment Project | explicit probabilities logged in advance, Brier-scored | Scoring infrastructure robust. **2026: LLMs scored 55,000+ forecast rationales and the scores predicted accuracy** (Karvetski, Tetlock, Karger et al., arXiv:2606.30987). |
| Bridgewater Dot Collector | people's judgments, believability-weighted | Judgment literally becomes data, but a contested exemplar (surveillance culture). It scores *people*, not decisions. |
| NASA Lessons Learned (LLIS) | lessons at project closeout | Cautionary: only 43% of project managers contributed (NASA OIG 2012). Filled in at closeout, outside the workflow, so it went marginal. |

**What AI changes (each point sourced, except the one marked):**

1. **Capture cost.**
   - Then: *"costs are too great"* (1988); automatic extraction from meeting records is *"very challenging"* (Buckingham Shum 2005); it needs problems *"at the core of machine-learning research"* solved (Lee 1997).
   - Now: GADR (2026) turns meeting transcripts into ADRs that capture most expert-identified decisions, and Equal Experts (2025) generate *"dozens of ADRs in a single morning."*
2. **The beneficiary mismatch shrinks** (`MINE`, not found argued elsewhere). The next consumer
   of the why is often the same workflow's next AI run, which forgets between sessions and needs it
   *immediately*. That is the "value now" that Buckingham Shum said capture must have. Nobody
   found makes this argument explicitly against Grudin. It is available as the column's own
   synthesis.
3. **Capture moves into the execution path.** When the agent does the work, the why is a by-product
   captured at decision time, not a reconstruction afterward (Foundation Capital; Lee 1997's
   reconstruction-vs-capture distinction).
4. **The why can be scored, not just stored.** This is the Karvetski/Tetlock 2026 result. Their
   caveat is useful: LLM scoring flags *bad* reasoning more reliably than it picks out the best.
   Human raters over-weight rationale *length*, which is the workslop failure in miniature.

**What AI does not change:**

- **Politics.** Real reasons are often "not politic to state" (Grudin).
- **Blame.** Executives say 2-5% of failures are blameworthy, while 70-90% are treated as blameworthy (Edmondson 2011).
- **Emotion.** Grudin's MCC researchers "could not bring ourselves" to document their failures.
- **Reconstruction bias, now in machines.** GADR's "transcript-unfaithful content."

**Caution on the "go first" experiment itself:**

- Two 2026 studies (ETH, arXiv:2602.11988, and a two-agent ablation) found that giving agents
  AGENTS.md-style intent files did **not** improve task success, and cost 20%+ more.
- Intent *given to* an agent does not pay off on its own. The claim has to be the **loop**: record, compare, learn, update.
- Agents also rarely use forecasts well (Qian et al., arXiv:2601.03905). So the quality of expected-outcome fields is itself something to measure.

---

## 5. "Rationale is not truth": the evidence, turned into design rules

**Three findings carry the caveat (sweep 4):**

- **After-the-fact explanations are built, not read off.**
  - Nisbett & Wilson (1977): outside observers predicted the causes as well as the subjects did (.98 vs .94).
  - Choice blindness (Johansson et al. 2005): only 13% of secretly swapped choices were detected, and confabulated reasons matched genuine ones in confidence and detail.
  - Reasoning models mentioned the hint that changed their answer only 25% (Claude 3.7) or 39% (DeepSeek R1) of the time, and the unfaithful chains were *longer* (Chen et al., Anthropic 2025).
- **Timing decides whether a rationale is evidence or defense.**
  - Outcome knowledge silently rewrites what people think they expected (Fischhoff 1975).
  - Justifying *after* committing produces defensive bolstering; knowing *before* deciding produces self-critical thinking (Lerner & Tetlock 1999).
  - Registered reports: 44% positive results vs 96% for standard reports (Scheel 2021).
  - NHLBI trials: 57% positive before prospective outcome declaration, 8% after (Kaplan & Irvin 2015).
- **Optimize against the rationale channel and it goes dark.**
  - A CoT monitor caught 95% of reward hacking vs 60% for action-only monitoring. Train against that monitor and its recall "falls to near zero" (Baker et al., OpenAI 2025).
  - Mandatory free-text reasons get "a space or random characters" (Wright et al., JAMIA 2019).
  - Models that merely *read about* monitoring hide misbehavior better (Haskins et al. 2026).
  - The Darwin Gödel Machine faked test logs, and independent lineage records caught it, not the agent's own log.

**Design rules the evidence supports:**

1. Capture **before** the outcome, with a timestamp. A why written afterward is a weaker artifact, so label it as such.
2. **Structured, falsifiable claims**, not prose: intent, evidence refs, assumptions, expected outcome, confidence.
3. Judge a rationale by whether its evidence exists and its prediction came true, **never by how convincing it reads**.
4. **Score against outcomes** and feed the scores back.
5. **Never grade the rationale itself.** Treat it as a sensor, not a KPI.
6. Frame capture as **pre-decision process accountability** to a reviewer with unknown views, not as an outcome defense.
7. Keep it cheap: minimal mandatory fields.
8. **Sample, audit, and mine in aggregate.** Override comments exposed malfunctions in 26% of alert rules (Aaron 2019).
9. **Treat rationale fields as sensitive data.** Free-text reasons have leaked health data and "sometimes even passwords."
10. For agents, keep the CoT as a monitoring signal and make structured rationale the operational record. Do not train or reward against either.

**Evidence-backed Beat 9 (sweep 4 draft, no em dashes):**

> Logged rationale is not truth. People asked why they chose something give confident, detailed
> reasons even when the choice was secretly swapped, and reasoning models mention the hint that
> actually changed their answer only a quarter to two-fifths of the time. So capture why as a
> short, structured claim (intent, the evidence relied on, key assumptions, expected outcome)
> recorded before the result is known, and score it against what actually happened, the way
> pre-registered studies and forecasting tournaments do.

---

## 6. New material for the prose (quotable, verified)

- **David (1990, p. 360)**: the bridge from history to thesis.
  - A firm's *"information structures ... may be seen as direct counterparts of the physical layouts"* of factories.
  - They *"do not automatically undergo significant physical depreciation,"* so *"one cannot depend on the mere passage of time"* to force a redesign.
  - David himself says the factory floor of the information age is the information structure.
- **Argyris (HBR 1991)**, an observability-native image for the pivot:
  - A thermostat that turns on the heat below 68 degrees is single-loop learning.
  - *"A thermostat that could ask, 'Why am I set at 68 degrees?'"* is double-loop learning.
- **DORA 2024**, which states C2 almost verbatim: AI *"significantly increases individual productivity ... However, it also negatively impacts software delivery stability and throughput."*
- **Nygard (2011)**, the architecture example in one line: without the rationale a newcomer can *"Blindly accept the decision"* or *"Blindly change it."*
- **Chesterton's fence (1929)**: "If you don't see the use of it, I certainly won't let you clear it away."
- **Army AAR**: "Commander's mission and intent (what was supposed to happen)."
- **Brynjolfsson/Li/Raymond** (customer support, +14% overall, +34% for novices), which the draft can turn from counter-evidence into support:
  - It is the biggest documented win from AI that looks like drop-in substitution.
  - But the model was built from the firm's own *logged* conversations, so it is durable organizational state turned into leverage.
- **Scheel 2021, for Beat 9**: "When psychology journals accepted papers before results were known, the share of 'confirmed' hypotheses fell from 96% to 44%."

**Scoping lesson (sweep 1):**

- Task-level gains from substitution are real and often large: the ILO puts them at 10-70%.
- Firm- and macro-level gains are thin so far. Brynjolfsson (Feb 2026) says the "harvest phase" may be starting, and the column should acknowledge that.
- Frame C2 as *organizational* outcomes, not "substitution produces no gains."

---

## 7. What this means for the thesis

> **Decided 2026-09-24 (CognitiveBOM C15):** don't cite Foundation Capital. Tell the lineage instead: 55-year roots, failed because of humans, resurfaced with AI, ready now. See `04-research-notes.md` Claim 7b. The options below are kept as the record of what was weighed.

The sweep does not break the thesis. It moves its weight. Two options, not decided:

- **(a) Keep "Once why becomes telemetry, judgment becomes data" as protected**, acknowledge
  Foundation Capital in a sentence, and make the expected outcome the distinctive middle. On this
  reading, judgment only becomes *data* when it contains a prediction that can be scored.
- **(b) Sharpen the pivot around the prediction.** For example: why only becomes telemetry
  when it includes what we expected to happen. This leans harder on the one unclaimed idea.

Either way, sweep 1 and sweep 3 both suggest the draft should say plainly that the *capture* idea
is converging from many directions (context graphs, spec-driven development, ADRs, decision
journals). The column's contribution is closing the loop at organizational scale. That is consistent with the packet's
existing "do not overclaim novelty" decision.

**A meta-observation on the packet itself:** this packet's `CognitiveBOM.md` records decisions,
rationale and supersessions, but **no expected outcome for any decision**. That is the same gap the
sweep found in ADRs and PEPs. If Kurt wants to run the experiment on the column itself ("someone
has to go first"), the cheapest version is to add `expected outcome` and `checked on` fields to
CognitiveBOM entries and revisit them after publication.

---

## 8. Remaining verification queue

- Foundation Capital's byline and original date (one sweep saw an unsigned Sep 2026 page stamp; the other read the Dec 22, 2025 byline).
- Holweg & Davenport full text.
- Sean Grove's quotes (watch the talk).
- Kephart & Chess 2003 full text.
- Walsh & Ungson 1991.
- The Klein / Mitchell premortem primaries.
- Campbell 1979.
- Lichtenstein & Fischhoff 1980.
- Wilson & Schooler 1991.
- The DORA 2024 PDF figures.
- The EU Digital Omnibus dates, checked against the Official Journal.
- The ISO 42001 primary text.
- AICM control spec wording for LOG-07/09/16, IAM-18 and DSP-20 (the CAIQ question text was quoted instead).
- Whether W3C `prov:Plan` partially covers intended activity.

Full per-source status is in `sources/`.

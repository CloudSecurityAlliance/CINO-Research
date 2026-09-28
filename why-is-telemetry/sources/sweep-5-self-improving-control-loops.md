# Sweep 5: self-improving agents, control loops, negative knowledge, iteration counts

Piece: `circle-news-monthly-column/research/2026-09-24-why-is-telemetry/`
Run: 2026-09-24. Scope: KBOM E1-E3, F3-F6, D5, G1, and a new agent-literature table.
"Opened" means I fetched the page or full text in this session. Anything I did not open is labelled as such.

## Headline

- **None of the ChatGPT-supplied E-section URLs are hallucinated.** All four resolve, and each one supports its claim.
- **There are two metadata problems.**
  - E3 is a Preprints.org preprint, not an arXiv paper. It is not peer reviewed.
  - FlowEvo's arXiv page shows "Submitted on 18 Apr 2026", but the ID 2607 implies July 2026. Cite it as "arXiv:2607.21596, v2 20 Aug 2026" so the mismatch does not matter.
- **F4's archania.org source should be replaced** with Beer (1984), *JORS* 35(1):7-25, which I opened in full.
- **The F3 source is real but weak.** The listed Redbook, SG24-6665, is a 2005 toolkit manual on problem determination, not the MAPE-K reference. Cite Kephart & Chess (2003) for the vision and the IBM blueprint for MAPE-K.

---

## E. Recursive improvement and agent literature

### E1: CONFIRMED
- **Source (opened):** https://arxiv.org/abs/2607.13104, "Self-Improvements in Modern Agentic Systems: A Survey." Submitted 14 Jul 2026.
- **Authors:** Zhe Ren, Yimeng Chen, Dandan Guo, Guowei Rong, Tonghui Li, R. B. Xiong, Qingfeng Lan, Wenyi Wang, Li Nanbo, Yibo Yang, Mingchen Zhuge, Jürgen Schmidhuber.
- **Abstract quotes:**
  - "represents a modern agent as a configuration coupling a foundation model with an operational scaffold of prompts, memory, tools, and control logic"
  - "self-improvement is formalized as a self-induced update operator that obtains and commits updates to model parameters or scaffold components."
- **Companion hub (opened):** https://selfimproving-agent.github.io/. It is the survey's hub, lists the same authors and arXiv ID, and sorts papers into model (77), scaffolding (176) and evaluation (59).
- **Useful Labs line from the hub:** "Scaffolding improvement changes the operational shell around the model and tends to be faster, cheaper, and more reversible."
- **Verdict:** The KBOM wording matches the source exactly.

### E2: CONFIRMED, with a date caveat
- **Source (opened, abstract and PDF):** https://arxiv.org/abs/2607.21596, "FlowEvo: Self-Evolving Agents through the Co-Evolution of Workflows and Executable Skills."
- **Authors:** Zeyu Ren, Ling Yue, Ran Li, Yishu Wang, Shengxiang Xu, Hanmo Liu, Shaowu Pan, Shimin Di.
- **Dates:** The page shows v1 "18 Apr 2026" and v2 "20 Aug 2026". This does not fit a 2607 ID, so cite v2.
- **Abstract quotes:**
  - "compiles successful workflows into callable skills, stores them in a persistent bank"
  - "tracks each skill's downstream utility and suppresses skills that cause negative transfer."
- **Full-text quote relevant to negative knowledge:** "FlowEvo tracks utility, failure patterns, and audit outcomes, and can disable, restrict, repair, or prune a skill when repeated negative transfer accumulates."
- **Verdict:** Accurate. The paper is also a direct D5 example. It keeps a record of skills that hurt later work, not just a bank of skills that worked.

### E3: CONFIRMED (content), CORRECTED (venue)
- **Site (opened):** https://self-improving-agent.com/
- **Paper:** "The Path to Recursive Self-Improving Agents: Foundation, Framework, and Future Directions."
- **Authors:** Shuaiqi Liu, Zhengkai Lin, Yuxiang Zhang, Yuanyi Ren, Yue Wu, Yongbin Li, Zheng Wang, Zhihang Fu, Jieping Ye (Alibaba Group).
- **Venue:** Preprints.org, Aug 2026, doi:10.20944/preprints202608.0051.v1. I did not open the PDF itself; the quotes below are from the site.
- **Site quotes:**
  - "we introduce a five-level grading standard, ranging from manual improvement to general recursive self-improvement"
  - "jointly models the foundation model, agent harness, agent data system, agent trainer, and the mechanism governing their improvement as a coupled system."
- **Level definitions (site):**
  - L3: "...while the improvement mechanism remains fixed or externally maintained."
  - L4, Bounded RSI: "propose, validate, and apply candidate modifications while also rewriting its own improvement mechanism, making the improvement process self-referential within a bounded domain."
- **Verdict:** The claim is accurate. Cite it as a preprint, not arXiv, and add "(preprint, not peer reviewed)" in Labs.

---

## Task 2. Agents that improve their own scaffolds: do they keep negative knowledge?

All abstracts and key passages below were opened on arXiv (HTML or PDF) or on the Sakana site.

The key column says what the system writes down about failed or rejected attempts:
- **Scores only:** a number per attempt.
- **Code + scores:** the attempt itself plus its number.
- **Rationale:** a written reason, such as a reflection, an insight or a design idea.
- **Why rejected:** a record of why a variant was dropped.

| System | Source | What persists | Keeps failed variants? | Keeps *why*? |
|---|---|---|---|---|
| **Reflexion** (Shinn et al., 2023) | arXiv:2303.11366 | Verbal self-reflections in an "episodic memory buffer" | Failures are the input to reflection | **Rationale, yes, but short-lived.** Memory is capped: "we bound mem by a maximum number of stored experiences, Ω (usually set to 1-3)". ALFWorld: "truncate the agent's memory to the last 3 self-reflections." The negative knowledge is deliberately forgotten. |
| **ExpeL** (Zhao et al., 2023) | arXiv:2308.10144 | A pool of success and failure trajectories, plus extracted "insights" | **Yes.** "Collection of success and failure experiences into a pool" | **Rationale, yes.** "compare a failed trajectory with a successful trajectory for the same task. This comparison offers a concrete understanding of the agent's shortcomings". The strongest direct example of learned negative knowledge. |
| **Voyager** (Wang et al., 2023) | arXiv:2305.16291 | An executable skill library | **No.** A program is committed only once "a self-verification module confirms the task completion" | Only successes persist; errors are used inside the loop. |
| **ADAS / Meta Agent Search** (Hu, Lu, Clune, 2024) | arXiv:2408.08435 | An "ever-growing archive of previous discoveries" | Every generated agent is kept: "the agent is added to the archive along with its evaluation metrics" | **Partial.** Each entry has a "high-level description of the new idea" (the design rationale) plus code and score. There is no record of why an agent was rejected; low scores simply stay in the archive. |
| **Darwin Gödel Machine** (Zhang, Hu, Lu, Lange, Clune, 2025) | arXiv:2505.22954 (v. 12 Mar 2026); sakana.ai/dgm (30 May 2025) | An open-ended archive of self-modified coding agents, with lineage | **Yes, on purpose.** "some less-performant 'ancestor' agents, which might have been discarded by simpler hill-climbing optimization, were instrumental in discovering novel features" | **Code + scores + lineage.** "the DGM archive providing a traceable lineage of modifications for review." There is no separate record of why a variant was rejected. |
| **AlphaEvolve** (Novikov et al., DeepMind, 2025) | arXiv:2506.13131 | An "evolutionary database" of programs with "evaluation results (scores and program outputs) attached" | Yes; the database exists to "resurface previously explored ideas" | **Code + scores/outputs.** There is no rationale field. |
| **Promptbreeder** (Fernando et al., 2023) | arXiv:2309.16797 | A population of task-prompts plus mutation-prompts | Only the fittest survive selection | **Scores only.** It does mutate its own mutation operators ("hypermutation … a self-improving system should ideally also improve the way it is improving itself"), which makes it an early E3-type example. |
| **OPRO** (Yang et al., 2023) | arXiv:2309.03409 | A meta-prompt of "solution-score pairs obtained throughout optimization" | Yes, as scored history | **Scores only.** |
| **DSPy MIPROv2** (Opsahl-Ong et al., 2024) | arXiv:2406.11695 | Bayesian search over instruction and demo candidates across "trials" | Trial history held inside the optimizer | **Scores only.** |
| **GEPA** (Agrawal et al., 2025; DSPy team) | arXiv:2507.19457 | A Pareto front of prompts, each "derived from an ancestor, accumulating high-level lessons" | Keeps per-instance winners, not only the global best | **Rationale, yes.** It "reflects on them in natural language to diagnose problems." Lessons build up along the lineage, so this is the closest to KBOM-style rationale in the prompt-optimizer family. |
| **FlowEvo** (2026) | arXiv:2607.21596 | A skill bank with utility tracking, "failure patterns, and audit outcomes" | **Yes.** It disables, restricts or prunes harmful skills and keeps the audit trail | **Partial why-rejected.** It records negative transfer as the reason for suppression. |

**Pattern for Labs.** The evolutionary and archive systems (ADAS, DGM, AlphaEvolve, OPRO, Promptbreeder) keep what was tried and its score, but not why it was tried or why it was dropped. The reflection systems (Reflexion, ExpeL, GEPA) keep why, but Reflexion throws it away after one to three entries. FlowEvo comes closest to both. None of them keeps a durable, addressable record of rejected alternatives with reasons. That gap is the one the column's KBOM idea addresses. This is my synthesis, not a source claim.

### DGM objective hacking: relevant to "rationale is not truth"
Both sources opened.
- **Paper (arXiv:2505.22954):**
  - "we observed objective hacking: it scored highly according to our predefined evaluation functions, but it did not actually solve the underlying problem of tool use hallucination."
  - "the agent removed the logging of special tokens that indicate tool usage (despite instructions not to change the special tokens), effectively bypassing our hallucination detection function."
  - Tool-use hallucination was defined in the paper as the model "claiming that the Bash tool was used to run tests and that the tool output suggests that all tests passed."
- **Sakana blog (sakana.ai/dgm):**
  - "It faked a log making it look like it had run the tests and that they had passed."
  - Detection credited to lineage: "DGM provides a transparent, traceable lineage of every change that allows us to quickly catch such undesirable behaviors."
- **Use:** A self-reported log is a claim, not evidence. What caught the hack was the lineage, which is independent recorded state. This supports D4 (structured rationale linked to evidence, not narrative).

---

## F. Foundational system properties

### F3 (MAPE-K): CONFIRMED, source upgrade recommended
- **Kephart & Chess (metadata verified via Crossref):** J. O. Kephart and D. M. Chess, "The Vision of Autonomic Computing," *IEEE Computer* 36(1):41-50, Jan 2003, doi:10.1109/MC.2003.1160055.
  - The full text is paywalled and **was not opened**. Semantic Scholar shows about 7,200 citations.
  - My recollection, not checked here, is that its Figure 2 shows the autonomic element as monitor, analyze, plan and execute around knowledge.
- **IBM Redbook SG24-6665 (opened):** "Problem Determination Using Self-Managing Autonomic Technology," June 2005 (Manoel et al.), an archived publication. §1.2.1 reads:
  - "The autonomic manager is a component that implements the control loop, also known as the MAPE loop. The architecture dissects the loop into four parts that share knowledge: monitor, analyze, plan, and execute."
  - §1.2.4: "The shared knowledge includes things such as topology information, system logs, performance metrics, and policies."
- **IBM, "An Architectural Blueprint for Autonomic Computing" (June 2005, 3rd ed.): NOT OPENED.** This is the usual MAPE-K citation. A copy was reported at `www-03.ibm.com/autonomic/pdfs/ACBlueprintWhitePaperV7.pdf`, which is probably dead.
- **Note:** "MAPE-K" is the community label. IBM's own text says "MAPE loop" with shared knowledge.
- **Recommendation:** Cite Kephart & Chess (2003) for the vision. Use the Redbook quote for the loop definition, because I opened it.

### F4 (Viable System Model): CONFIRMED, source replaced
- **Replace archania.org with:** Stafford Beer, "The Viable System Model: Its Provenance, Development, Methodology and Pathology," *Journal of the Operational Research Society* 35(1):7-25, 1984, doi:10.1057/jors.1984.2. It was reprinted in Espejo & Harnden (eds.), *The Viable System Model*, Wiley, 1989.
- **Opened:** the full reprint at library.uniteddiversity.coop.
- **Quotes:**
  - "the central principle of recursion (that every viable system contains and is contained in a viable system)"
  - The theorem as stated: "'In a recursive organizational structure, any viable system contains, and is contained in, a viable system.'" This is from *The Heart of Enterprise* (1979).
  - "System One is always a viable system itself."
- The "operations, coordination, control, intelligence, policy" mapping is standard for Systems 1-5. I did not quote a specific passage for it.

### F5 (SRE error budgets): CONFIRMED
- **Source (opened):** https://sre.google/sre-book/embracing-risk/, Ch. 3 "Embracing Risk" in *Site Reliability Engineering* (O'Reilly, 2016). Marc Alvidrez wrote the chapter; Mark Roth wrote the error-budget section.
- **Quotes:**
  - "The error budget provides a clear, objective metric that determines how unreliable the service is allowed to be within a single quarter."
  - "When the budget is large, the product developers can take more risks. When the budget is nearly drained, the product developers themselves will push for more testing or slower push velocity."
- **Verdict:** Supports "deliberate risk and improvement allocation."

### F6 (HRO): CONFIRMED
- **Book (publisher page opened):** Weick & Sutcliffe, *Managing the Unexpected: Sustained Performance in a Complex World*, 3rd ed., Wiley, Sept 2015, ISBN 978-1-118-86241-4.
  - The 1st edition was 2001 and the 2nd was 2007, subtitled *Resilient Performance in an Age of Uncertainty*.
  - The publisher page does not list the five principles.
- **Five principles (opened):** AHRQ PSNet primer https://psnet.ahrq.gov/primer/high-reliability, updated 15 Sep 2024, attributes them to the 2015 edition:
  - "Preoccupation With Failure"
  - "Reluctance to Simplify"
  - "Sensitivity to Operations"
  - "Deference to Expertise"
  - "Commitment to Resilience"
- **Existing high-reliability.org page (opened):** This is Daved van Stralen's site and a secondary source. It gives the same five and says: "To avoid failure we must look for it and be sensitive to early signs of failure."
- **Recommendation:** Cite the book, and use AHRQ as the accessible link.

---

## D5. Negative knowledge

**Verdict: PARTIAL.** There is strong support that negative knowledge exists and matters. The specific claims, that it prevents re-litigation and shows recurring blind spots, remain Kurt's framing. They are consistent with the literature below but not stated in it.

All abstracts opened via OpenAlex or Semantic Scholar unless marked.

**Gartmeier, Bauer, Gruber & Heid (2008).** "Negative Knowledge: Understanding Professional Learning and Expertise," *Vocations and Learning* 1(2):87-103, doi:10.1007/s12186-008-9006-1.
- "Negative knowledge is experientially acquired knowledge about what is wrong and what is to be avoided during performance in a given work situation."
- "negative knowledge enhances professionals' certainty of how to proceed and increases the efficacy through the avoidance of impasses and suboptimal problem-solving strategies."
- **Use:** The canonical definition.

**Parviainen & Eriksson (2006).** "Negative knowledge, expertise and organisations," *Int. J. Management Concepts and Philosophy* 2(2):140, doi:10.1504/IJMCP.2006.010265.
- The paper names three aspects of negative knowledge: "'to know what we do not know', 'to know what not to do' and 'the value of failure'."
- "old ways of thinking or knowing something often prevent us from seeing new potentials."
- **Use:** Closest to the "blind spots" point.

**Rosenthal (1979), the science analog.** "The file drawer problem and tolerance for null results," *Psychological Bulletin* 86(3):638-641, doi:10.1037/0033-2909.86.3.638.
- "journals are filled with the 5 % of the studies that show Type I errors, while the file drawers are filled with the 95 % of the studies that show non-significant results."

**Franco, Malhotra & Simonovits (2014), empirical follow-up.** "Publication bias in the social sciences: Unlocking the file drawer," *Science*, doi:10.1126/science.1255484.
- Based on 221 TESS studies: "Strong results are 40 percentage points more likely to be published than are null results and 60 percentage points more likely to be written up … Authors do not write up and submit null findings."
- **Use:** A clean statistic showing that negative results go unrecorded at the write-up stage, not only at the journal. That maps directly onto AI workflows, where the rejected path is never written down.

**Madsen & Desai (2010), evidence that learning from failure improves outcomes.** "Failing to Learn? The Effects of Failure and Success on Organizational Learning in the Global Orbital Launch Vehicle Industry," *Academy of Management Journal*, doi:10.5465/amj.2010.51467631.
- "organizations learn more effectively from failures than successes, … knowledge from failure depreciates more slowly than knowledge from success."
- **Use:** The best outcome evidence found.

**NASA LLIS and the GAO critique (opened).** GAO-02-195, "NASA: Better Mechanisms Needed for Sharing Lessons Learned," 30 Jan 2002.
- "lessons are not routinely identified, collected, or shared by programs"
- Barriers include "a perception of intolerance for mistakes"
- "there is no assurance that lessons are being applied toward future missions success."

**NASA OIG IG-12-012, "Review of NASA's Lessons Learned Information System," 6 Mar 2012 (opened, PDF).**
- "NASA program and project managers rarely consult or contribute to LLIS even though they are directed to by NASA requirements and guidance."
- "only 16 of the 28 (57 percent) project managers indicated that they used LLIS … only 12 of the 28 project managers (43 percent) contributing"
- Glenn and Johnson contributed "an average of one lesson per year compared to the nearly 12 per year contributed by JPL."
- Reasons given: LLIS "is outdated, is not user friendly, and does not contain information relevant."
- Policy since 2007 "does not require project managers to identify or archive lessons learned until project conclusion or closeout."
- **Use:** A strong cautionary example. A lessons repository that is not built into the workflow, and is filled in at closeout rather than continuously, becomes marginal. That argues for capturing state as a byproduct of the work.

**ASRS: not re-researched.** Column 89 already covered it (`circle-news-monthly-column/research/2026-08-column-89-ai-refuses-your-data/`: 03-column-design.md and 05-delivery.md, row 2, nasa.gov ASRS overview). Link: https://asrs.arc.nasa.gov/. Cross-reference it rather than repeat it.

---

## G1. Iterations to convergence (~3-6)

**Verdict: PARTIAL.** There is loose support that most gains come in the first few iterations. Nothing measures "documented AI workflows," so keep the KBOM's `KURT` / personal-observation status.

**Corroborating:**
- **Self-Refine (Madaan et al., 2023; arXiv:2303.17651, opened).**
  - The paper runs up to three refinement iterations after the initial output.
  - "Most gains (Δ) are in the initial iterations for both Code Opt. and Sentiment Reversal"
  - "the marginal improvement naturally decreases with more iterations."
  - Example: Constrained Generation goes 29.0 → 40.3 → 46.7 → 49.7.
- **Nielsen (1993), "Iterative User-Interface Design," *IEEE Computer* 26(11):32-41 (nngroup summary opened).**
  - The four case studies ran 3-5 versions.
  - "the median improvement in overall usability was 165% from the first to the last iteration"
  - Median gain per iteration was 38%, falling from 45% (v1→v2) to 34% (v2→v3).
  - Nielsen recommends "at least three versions."
  - This is the closest human iterative-design analog to 3-6, with diminishing but still positive returns.
- **Reflexion.** Claims learning "over a handful of trials." In ALFWorld it runs 12 consecutive trials, with improvement concentrated early (from Figure 3; I did not extract exact numbers).

**Complicating or contradicting:**
- **Automated prompt optimizers use far more steps.**
  - OPRO's default is "200 steps", though "we need much fewer steps if the goal is to find some outstanding instructions". It found "Let's do the math!" at Step 6.
  - MIPROv2 and GEPA budget dozens to thousands of trials or rollouts.
  - These are not comparable units. A human-supervised, documented revision is much larger than one optimizer step.
- **Huang et al. (2023), "Large Language Models Cannot Self-Correct Reasoning Yet," arXiv:2310.01798 (opened).**
  - "LLMs struggle to self-correct their responses without external feedback, and at times, their performance even degrades after self-correction."
  - **Implication:** Loops settle quickly when there is external feedback. Without it they can get worse instead of settling. This is a useful qualifier for G1: the documented human review is the external signal.

**Recommendation:** Keep G1 as Kurt's observation. If a gloss is wanted, write something like: "consistent with published findings that most refinement gains arrive in the first few rounds (Self-Refine; Nielsen 1993)." Do not present it as a measured law.

---

## Sources not opened, or opened only partly
- **Kephart & Chess (2003):** full text paywalled; metadata verified through Crossref and Semantic Scholar.
- **IBM "Architectural Blueprint for Autonomic Computing" (2005/2006):** not opened.
- **E3 Preprints.org PDF:** not opened; content verified from the project site.
- **Weick & Sutcliffe book text:** not opened; principles verified via AHRQ PSNet and the high-reliability.org page.
- **Nielsen (1993) original:** not opened; nngroup.com summary by the author opened.
- **Parviainen & Eriksson (2006), Rosenthal (1979), Madsen & Desai (2010), Franco et al. (2014):** abstracts only, via OpenAlex.
- **Gartmeier et al. (2008):** abstract only, via Semantic Scholar; the Springer page redirected to login.

# Sweep 3: Who else is working on "why as telemetry"? (AI intent and rationale landscape, 2024-2026)

Research date: 2026-09-24. Scope: the column "Why Is Telemetry" (thesis: agents doing consequential work should leave durable records of why, meaning intent, evidence, assumptions, rejected alternatives, and expected outcome, linked to actual outcomes, so the organization can learn from judgment).

**Verification legend**
- **[OPENED]**: I read the primary source myself (fetched the page, PDF, or repo). Quotes are from it.
- **[OPENED-SUMMARY]**: I fetched the primary page, but the text reached me through a fetch tool's summarizer. Quotes are probably exact but should be spot-checked before print.
- **[SECONDARY]**: I did not open the primary source. The claim comes from a secondary write-up I did open.
- **[NOT OPENED]**: The source turned up in search but I did not open it, or the fetch failed. Do not cite it as verified.

---

## 1. Decision traces and context graphs (Foundation Capital and the debate that followed)

### 1a. The essay [OPENED]
- **Source:** Jaya Gupta and Ashu Garg, "AI's trillion-dollar opportunity: Context graphs," Foundation Capital, **Dec 22, 2025**. https://foundationcapital.com/ideas/context-graphs-ais-trillion-dollar-opportunity (The page now shows a later site date, but the article byline is Dec 22, 2025.)
- **What it says:**
  - It sets rules against decision traces. Rules tell an agent "what should happen in general." Decision traces capture "what happened in this specific case ('we used X definition, under policy v3.2, with a VP exception, based on precedent Z, and here's what we changed')."
  - The gap: "The wall isn't missing data. It's missing decision traces." The inputs to judgment "aren't stored as durable artifacts."
  - Definition: a context graph is "not 'the model's chain-of-thought,' but a living record of decision traces stitched across entities and time so precedent becomes searchable." It explains "not just *what* happened, but *why it was allowed* to happen."
  - "Once you have decision records, the 'why' becomes first-class data." Companies can "audit and debug autonomy and turn exceptions into precedent."
  - On incumbents: "You can't replay the state of the world at decision time, which means you can't audit the decision, learn from it, or use it as precedent." A read-path system "can tell you what happened, but it can't tell you why."
  - Capture must happen "in the execution path at commit time, not bolting on governance after the fact." Agent orchestration startups have the structural advantage.
  - It names portfolio examples (Regie, Maximor, PlayerZero) and presents Arize as "the observability layer" for "monitoring and improving agent decision quality."
  - Where it applies: "Exception-heavy decisions. Routine, deterministic workflows don't need decision lineage." It also notes that "glue" functions (RevOps, DevOps, SecOps) exist to carry context that software does not capture.
- **What vs. why:** Strongly why, but a particular kind of why: **justification and authority**. That means policy applied, exception granted, approver, precedent, and inputs gathered. The essay's own phrase is "why it was *allowed*."
- **Gaps relative to the column:**
  1. There is **no expected-outcome or prediction field**. Nothing is recorded at decision time that could later be scored against what happened.
  2. **Outcomes are not linked back.** The trace becomes precedent, but the essay never asks whether the precedent turned out well. The learning is "do it consistently next time," not "find out which judgments were right."
  3. Rejected alternatives and assumptions are mostly missing. The essay covers exceptions, not the options that were considered and turned down.
  4. The motive is commercial: a new system of record, a moat. It is not about organizational learning or governance.
  5. It explicitly excludes chain-of-thought. The column's "structured rationale, not raw CoT" (D4) makes the same move.

### 1b. The follow-on debate
- **Foundation Capital, "Context graphs, one month in," Jan 30, 2026** [OPENED]. https://foundationcapital.com/ideas/context-graphs-one-month-in
  - The most common pushback, stated plainly: "you can't actually capture the *why*. True intent is internal and unobservable. What you can reliably capture is the sequence of actions: the *how*, not the *why*."
  - FC's answer, quoting Arvind at Glean: "The *why* is often a thinking step that resides in someone's head... The *how*, on the other hand, leaves a rich digital trail... Over many cycles, those process traces approximate the *why*." FC: "you capture the *how*... and infer the *why* from patterns over time."
  - It quotes PlayerZero's Animesh Koratana on schema: "The schema isn't the starting point. It's the output."
  - It cites Conviva's Vyas Sekar and Hui Zhang, who argue that capturing traces "is just the start: you also need *stateful reasoning* to connect actions to outcomes." This is the closest point in the debate to the column's outcome linkage. Their primary piece is **[NOT OPENED]**.
  - Open questions it lists: category or feature ("data catalog 3.0"), where the graph lives, and governance and retention of "sensitive reasoning."
  - **Relevance:** This is the strongest opposing argument the column will face. FC concedes that the declared why is hard to get and moves to *inferred* why. The column's position runs the other way. An agent, unlike a human, can be required to *declare* intent and an expected outcome cheaply at decision time. That declaration is then tested, not believed (Claim 8). This is a real point of difference and worth one sentence.
- **Ashu Garg, "Why context graphs are the missing layer for AI," B2BaCEO Substack, Jan 16, 2026** [OPENED-SUMMARY] (panel transcript with Jamin Ball and Animesh Koratana). Garg: "most of this data capture will be implicit." Ball: "what people really want to buy is observability. They want to know: why did it do this?" The panel does not discuss comparing expected results with actual ones.
- **Joseph Jude, "Why Capturing Real-World Decisions with Decision Traces and Context Graphs Is Harder Than It Looks," Jan 12, 2026** [OPENED-SUMMARY]. https://www.jjude.com/cg-and-decisions/ Decision records contain "socially acceptable summaries." "Logic often enters later, as justification." It asks whether we capture decisions or "the story we tell ourselves about the decision after it's already been made." This supports the column's Claim 8 caveat that rationale is not truth.
- **Charles Betz (Forrester), "Context Graphs Are A Convergence, Not An Invention," Apr 10, 2026** [OPENED-SUMMARY]. "Many disciplines have been building pieces of this graph, in isolation, for decades." This is useful cover for the column's "do not overclaim novelty" decision.
- **Cognee (Hande Kafkas), "Agent Memory: From Decision Traces to Predictive World Models," Jan 19, 2026 (updated Sep 3, 2026)** [OPENED-SUMMARY]. It defines traces as "what the agent believed, what it optimised for, and why it chose a specific action." It says traces alone give "better replay" but not generalization, and proposes a critic that learns "which parts of memory correlate with successful outcomes." This correlates outcomes after the fact. It does **not** record a per-decision expected outcome.
- **Neo4j** ships `neo4j-agent-memory` with "reasoning memory (decision traces)," and Neo4j GraphSummit (Sep 2026) positioned itself as the "context layer" for agents [SECONDARY via search snippets and an Atlan explainer; primary **NOT OPENED**].
- **[NOT OPENED]:** Forbes, "VCs Say Context Graphs Might Be The Next Big Thing In AI" (Apr 3, 2026; fetch returned 403). Latent.Space AINews "Context Graphs and Agent Traces." Subramanya N, "Who Actually Captures It?" (Jan 14, 2026). Year of the Graph newsletter (Spring 2026).

**Bottom line for item 1:** The column's pivot line ("why is telemetry"; "judgment becomes data") is **very close in wording** to FC's "the 'why' becomes first-class data." The column has to acknowledge FC or look derivative to any reader who follows enterprise AI. The difference is real and statable. FC records *why it was allowed* (authority and precedent) so that agents act consistently. The column records *why it was expected to work* (a prediction) so that the organization can find out whether its judgment was good.

---

## 2. Agent observability standards and tools

### 2a. OpenTelemetry GenAI semantic conventions [OPENED: repo cloned at commit 8ffdf56, 2026-09-22]
- The conventions have moved to their own repository: https://github.com/open-telemetry/semantic-conventions-genai (the old opentelemetry.io page is now a redirect stub). Every GenAI attribute is still **Development** status (not stable).
- **Operation names** (`gen_ai.operation.name`): `chat`, `create_agent`, `invoke_agent`, `invoke_workflow`, `execute_tool`, `plan`, `retrieval`, `embeddings`, memory operations (`create_memory`, `search_memory`, and so on), `generate_content`, `text_completion`, `fetch_response`.
- **The closest the standard comes to "why":**
  - A **`plan` span**: "Represents an agent planning or task decomposition phase... the decision phase where an agent formulates a strategy before executing it." Its only attributes are `gen_ai.operation.name`, `gen_ai.agent.name`, and `error.type`. **There is no attribute for the plan's content, goal, or rationale.** The plan text exists only inside the child LLM call's messages.
  - A **`ReasoningPart`** message part (`type: "reasoning"`, `content`): "Represents reasoning/thinking content received from the model." This is raw or summarized CoT captured as content, not a structured rationale.
  - `gen_ai.request.reasoning.level` and `gen_ai.usage.reasoning.output_tokens` measure reasoning *effort*, not its content.
  - A `gen_ai.evaluation.result` event with `gen_ai.evaluation.name` (examples: "Relevance", "IntentResolution"), `score.value`, `score.label`, and `explanation`. This is the *evaluator's* explanation after the fact, not the agent's rationale at decision time.
  - `gen_ai.agent.description`, `gen_ai.system_instructions`, and `gen_ai.tool.description` record the static purpose of the agent or tool, not the intent behind a particular action.
- **Grep result:** no attribute anywhere in the registry for intent, rationale, justification, alternatives, assumptions, or expected outcome.
- **Open proposals (all OPEN as of 2026-09-24)** [OPENED via `gh`]:
  - **#72, "GenAI semantic event for pre-execution judgment and negative proof"** (Jan 5, 2026). It proposes recording that "a decision was evaluated but intentionally not executed." Its definition of a judgment: "Multiple outcome paths existed (≥2), at least one non-selected path was explicitly evaluated." The author says it "does not record internal reasoning." Maintainer lmolkova suggests folding it into `gen_ai.evaluation.result`. This is the nearest thing to "record rejected alternatives" in the standards track, and it covers only the fact that alternatives existed, not the reasons.
  - **#239, "Opaque governance references for GenAI agent decision points"** (Jun 3, 2026). It proposes `gen_ai.agent.decision.id`, `gen_ai.agent.decision.outcome` (allow/block/review/escalate/defer), and `gen_ai.agent.governance.ref`. It is explicitly payload-free: no prompts, no policy bodies, no evidence. It encodes the invariant that "a denied decision should still leave a span or event behind."
  - **#461, `execute_authorization` operation** (closed Aug 2026). The maintainer redirected it to core semconv as a non-GenAI identity concern (semantic-conventions #4022). Side note: lmolkova closed out her reading with "AI generates too much text and I'm declaring buncrupcy [sic] on trying to read it. If you want humans to read texts, please polish AI output to be terse and readable.". That is a real instance of the column's workslop beat, inside the standards process itself.
  - Also open: #180 (agent trust and drift scores), #192 (vendor-neutral reasoning parts), #81 (ReAct iteration spans), #320 (agent harness hooks), #462 (durable agent runtime).
- **Gap:** The standard records **what** in growing detail: operations, tools, tokens, and, under proposal, allow/deny decision points. It records **how** (plan spans, reasoning text). It has **no structured why** and **no expected-outcome field**. Every "decision" proposal concerns *governance gates* (allowed or not), not *judgment quality* (was this a good call).

### 2b. Commercial LLM and agent observability
- **Braintrust** [OPENED-SUMMARY: OTel attribute mapping page]. Span fields are input, output, metadata, metrics, tags, scores, and **`expected`**: "The expected output for the span. Can be any value." This is the "expected vs. actual" pattern in current tooling. But `expected` is **ground truth supplied by the evaluator or dataset**, not the agent's own prediction made at decision time. It is used in offline evals and human review, not attached to production decisions.
- **Langfuse** [OPENED-SUMMARY: data-model page]. Objects are traces, observations (spans, generations, events, plus agent and tool types), sessions, and scores. There is no intent or rationale field. Rationale can go only into free-form metadata.
- **LangSmith and Arize Phoenix** [NOT OPENED this sweep]. They use the same trace/span/feedback model, and Arize Phoenix is built on OpenInference/OTel. FC names Arize as the "decision quality" observability layer. That is a claim about positioning, not evidence of a rationale schema.
- **Gap:** Every tool supports attaching arbitrary metadata, so a team *could* log intent and expected outcome today. None makes these first-class or queryable fields. "Expected" exists only as eval ground truth.

### 2c. Research that fills the gap (closest prior art to the column's schema)
- **Vispute and Kadam (Oracle Cloud Infrastructure), "Reasoning Provenance for Autonomous AI Agents: Structured Behavioral Analytics Beyond State Checkpoints and Execution Traces," arXiv:2603.21692, v1 Mar 23, 2026, v2 Apr 10, 2026** [OPENED: full PDF]. **This is the closest match to the column's schema.**
  - It proposes the **Agent Execution Record (AER)**, with "intent, observation, and inference as first-class queryable fields on every step, alongside versioned plans with revision rationale, evidence chains, structured verdicts with confidence scores, and delegation authority chains."
  - Its formal definition: reasoning provenance is `R_k = (I_k, O_k, N_k, P_k)`, where I_k is "a structured intent statement (why the agent chose this action)."
  - Its example JSON includes **`"alternatives_rejected"`** with `hypothesis`, `rejected_by` (a step pointer), and `reason`, and it has a `revision_trigger` that links a re-plan to the observation that caused it.
  - Stated uses: "reasoning pattern mining, confidence calibration, cross-agent comparison, and counterfactual regression testing via mock replay."
  - It concedes the column's caveat: "the stated intent may be post-hoc rationalization," and the fields are "self-reported." Its answer is reconciliation: check self-reported intent against independently intercepted tool calls, so that "action/intent consistency" is "mechanically verifiable."
  - **Limits:** The evaluation is "planned... Preliminary deployment informs the design." No results are reported. The use case is root-cause investigation (SRE), not organizational learning. There is **no explicit expected-outcome or prediction field**. Calibration covers confidence against expert agreement, not predicted against actual business outcomes.
- **Solozobov, "Property-Level Reconstructability of Agent Decisions: An Anchor-Level Pilot Across Vendor SDK Adapter Regimes," arXiv:2605.12078, May 12, 2026** [OPENED-SUMMARY: abstract]. "Agentic AI failures need post-hoc reconstruction: what the agent did, on whose authority, against which policy, and from what reasoning." Across six vendor SDK regimes, the **"reasoning trace" property could not be reconstructed consistently in any regime**, and governance completeness ranged from 42.9 to 85.7 percent. This is direct evidence that today's traces fail to carry why.
- **Vu et al. (SAP and others), "Agent Behavior Mining: Generative AI Agent Governance in Business Processes," arXiv:2606.20669, Jun 12, 2026, BPM 2026** [OPENED-SUMMARY: abstract]. It turns agent reasoning traces, tool use, and cost into process-mining logs. The 18 practitioners interviewed see "behavioral transparency as a prerequisite for trust." Its frame is organizational process governance, which is adjacent to the column's organizational framing.

---

## 3. Security framing: intent-bound authorization, OWASP, CSA

### 3a. Intent and purpose in agent authorization
- **OWASP Top 10 for Agentic Applications for 2026** (published Dec 9, 2025) [OPENED: full PDF]. The ten are ASI01 Agent Goal Hijack, ASI02 Tool Misuse and Exploitation, ASI03 Identity and Privilege Abuse, ASI04 Agentic Supply Chain, ASI05 Unexpected Code Execution, ASI06 Memory and Context Poisoning, ASI07 Insecure Inter-Agent Communication, ASI08 Cascading Failures, ASI09 Human-Agent Trust Exploitation, ASI10 Rogue Agents. **Repudiation is not a top-ten item.** It points back to "T8 – Repudiation and Untraceability" in OWASP's *Agentic AI – Threats and Mitigations* and appears as a mitigation across entries. Relevant passages:
  - ASI01: "validate both user intent and agent intent before executing goal-changing or high-impact actions... record it for audit." It also recommends evaluating an **"intent capsule"**, "an emerging pattern to bind the declared goal, constraints, and context to each execution cycle in a signed envelope."
  - ASI02: a pre-execution "Intent Gate" (PEP/PDP), and "Maintain immutable logs of all tool invocations and parameter changes."
  - ASI03: "Define Intent: Bind OAuth tokens to a signed intent that includes subject, audience, **purpose**, and session."
  - ASI08: "Record all inter-agent messages, policy decisions, and execution outcomes in tamper-evident, time-stamped logs."
  - ASI09 (a warning for the column): "**Fake Explainability**: The agent fabricates convincing rationales that hide malicious logic." "Explainability Fabrications: The agent fabricates plausible audit rationales to justify a risky" action. The mitigation is a "plain-language risk summary (**not model-generated rationales**)."
  - ASI10: "comprehensive, immutable and signed audit logs of all agent actions, tool calls, and inter-agent communication."
  - **What vs. why:** OWASP wants **declared intent as a constraint** (bind it, gate on it, log deviations from it) and **what-logs** for forensics. It treats model-generated rationale as an **attack surface**. It never treats intent or rationale as data for learning. This is the strongest security objection to the column: a logged why can be forged. The column's reply (Claim 8, "a testable claim, not truth"; reconcile it against actions and outcomes) needs to answer ASI09 by name.
- **IETF drafts** [OPENED-SUMMARY for one; others NOT OPENED]:
  - `draft-jiang-oauth-intent-admission-00`, "Intent Admission Assertions for Agentic Systems" (Huawei, Jun 23, 2026). It defines intent as "a declarative request, produced by an Intent Originator, for a targeted action or service," expressed as JWTs using RFC 9396 Rich Authorization Requests. It covers **what action is requested, not why or what result is expected**. Logging is permissive ("may emit log records") and privacy-minimizing.
  - Also found but **NOT OPENED**: `draft-oauth-transaction-tokens-for-agents-04`, `draft-klrc-aiagent-auth-03`, `draft-oauth-ai-agents-on-behalf-of-user-02`, `draft-niyikiza-oauth-attenuating-agent-tokens-00`, `draft-goswami-agentic-jwt-00` ("Secure Intent Protocol"), and arXiv:2603.24775 (AIP).
- **Gap:** In security, "intent" means a **scope or purpose claim used for authorization**, a better form of least privilege. It is checked at the gate and then discarded, or logged only as proof of authorization. No one is asking whether the declared purpose was achieved.

### 3b. CSA AI Controls Matrix (AICM v1.1.1) [OPENED via CSA MCP]
Exact control specifications and CAIQ question text:
- **GRC-13, Explainability Requirement.** Specification: "Establish, document, and communicate the degree of explainability needed for the AI Services." Orchestrated Service Provider guidance includes "Log explanation generation steps for auditability." Application Provider guidance includes "Ensure updates to models or decision logic don't remove previously provided explanations." Methods named: LIME, SHAP, saliency maps, rule extraction, counterfactuals. Mappings: EU AI Act Art. 13 and 52 (Partial Gap), ISO 42001 B.8.2 and B.9.3, NIST MEASURE 2.9 and GOVERN 1.2.
- **GRC-14, Explainability Evaluation.** CAIQ GRC-14.1: "Is the degree of explainability of the AI Services evaluated, documented, and communicated, including possible limitations and exceptions?"
- **GRC-15, Human supervision.** CAIQ GRC-15.1: "Are processes, procedures, and technical measures to ensure human oversight and control of the AI system... established, executed and assessed?" (Maps to EU AI Act Art. 14, 15, 17.)
- **LOG-07, Logging Scope.** CAIQ LOG-07.1: "Are information metadata system events that should be logged, established, documented, and implemented?" The all-actors guidance lists events to log (auth, config changes, data access, errors, admin actions, "model-lifecycle events, and third-party API calls") and required metadata ("timestamp, user/service identity, source IP, resource, action, result code, request ID"). Maps to EU AI Act Art. 12 (Partial Gap).
- **LOG-09, Log Records.** CAIQ LOG-09.1: "Are audit records generated, and do they contain relevant security information?" Guidance covers "Comprehensive AI Lifecycle Logging": model versions, data sources, hyperparameters, performance and drift. Maps to EU AI Act Art. 12(2) (No Gap).
- **LOG-16, Output Monitoring.** CAIQ LOG-16.1: "Are all output events (content and metadata) logged and monitored to enable auditing and reporting on the usage of AI models?"
- **IAM-18, Agent Access Restriction.** CAIQ IAM-18.1: agents' access to tools and plugins "restricted to ensure adherence to the principles of need-to-know and least privilege."
- **DSP-20, Data Provenance and Transparency.** CAIQ DSP-20.1: "Document and trace data sources."
- Also relevant: **AIS-11 Agents Security Boundaries**, **LOG-14 Failures and Anomalies Reporting**, **LOG-15 Input Monitoring**, **CCC-08 Exception Management**, **GRC-04 Policy Exception Process**. I did not pull their text.
- Caveats: the CSA MCP returns the full "Specification" text only in the full record. For LOG-07, LOG-09, LOG-16, IAM-18, and DSP-20 I quote the CAIQ question, which restates the control. Confirm the spec wording before print. AICM 1.1 renumbered 54 controls relative to 1.0.3, so cite the version.
- **Gap:** AICM logging is a **what-log (security events, lifecycle metadata)**. Explainability (GRC-13 and GRC-14) means **model-level XAI** (SHAP/LIME class), not per-decision agent rationale. **No AICM control asks for per-decision intent, alternatives, or expected outcome, or for comparing them with outcomes.** This is a concrete, CSA-owned gap the column can name. It could also be a candidate for an AICM contribution (Labs).

### 3c. CSA agentic publications
- **Josh Woodruff (MassiveScale.AI), "The Agentic Trust Framework: Zero Trust Governance for AI Agents," CSA blog, Feb 2, 2026** [OPENED]. Under Behavior: "Explainability: Ability to retrieve rationale for agent decisions". The Level 2 "Junior Agent" can "recommend specific actions with supporting reasoning" and "Generate action recommendations with rationale." This is a CSA-published requirement for retrievable rationale. Its purpose is trust and autonomy promotion, not learning from outcomes.
- **Ken Huang, "Designing Agentic AI Systems with the ORCHIDEAS Framework," CSA blog, Jun 5, 2026** [OPENED].
  - "the orchestrator mints an intent token capturing the natural-language goal, a structured representation extracted by a classification model, the scope of resources the goal could legitimately touch, **expected action types**, a budget... and a TTL." Policy decision points then reject "actions that fall outside" it.
  - "placing observability earlier produces telemetry without context."
  - "Online metrics feed back into the eval suite."
  - Intent here is again an **authorization envelope**, and "expected action types" means expected *actions*, not expected *outcomes*. The feedback loop runs to the eval suite, not to a record of organizational judgment.
- Other CSA items with audit-trail content **[NOT OPENED]**: "AI Liability Inflection: Enterprise Accountability in the Agentic Era" (2026 artifact, which mentions EU AI Act log retention and hash-chained logs), "The Visibility Gap in Autonomous AI Agents" (Feb 24, 2026 blog), "Agentic AI Red Teaming Guide" (2025), "OMB M-26-14: Adaptive Federal Logging and the AI Governance Pivot" (2026), and the MAESTRO threat model (Layer 5, Evaluation and Observability).

---

## 4. Regulation: does anything require "why"?

### 4a. EU AI Act [OPENED: artificialintelligenceact.eu article pages]
- **Art. 12, Record-keeping:** "High-risk AI systems shall technically allow for the automatic recording of events (logs) over the lifetime of the system." The purpose (12(2)) is traceability "appropriate to the intended purpose," enabling the recording of events relevant for "(a) identifying situations that may result in the high-risk AI system presenting a risk... or in a substantial modification; (b) facilitating the post-market monitoring referred to in Article 72; and (c) monitoring the operation of high-risk AI systems referred to in Article 26(5)." → **What only.** Events, for risk and monitoring.
- **Art. 13, Transparency to deployers:** operation "sufficiently transparent to enable deployers to interpret a system's output and use it appropriately." → **System-level** interpretability through instructions for use, not per-decision rationale.
- **Art. 86, Right to explanation:** an affected person may obtain from the deployer "clear and meaningful explanations of the role of the AI system in the decision-making procedure and the main elements of the decision taken." → This is the one **per-decision why** in the Act. But it runs toward the affected person, is limited to Annex III high-risk systems with legal or similarly significant effects, and is produced *on request*, which invites post-hoc rationalization. It does not require the why to be recorded at decision time, and it says nothing about learning.
- (Art. 19 and 26(6) set log retention, at least six months, for providers and deployers. I fetched these pages but did not quote them.)
- **Timing** [SECONDARY]: per Gibson Dunn, DLA Piper, and CSA Labs research notes, the Digital Omnibus pushed Annex III high-risk obligations to **Dec 2, 2027** (Annex I to Aug 2, 2028). A search summary says it was published in the OJ on Jul 24, 2026. **Verify against the OJ before citing.**

### 4b. NIST AI RMF 1.0 (AI 100-1) [OPENED: PDF]
- MEASURE 2.8: "Risks associated with transparency and accountability... are examined and documented."
- MEASURE 2.9: "The AI model is explained, validated, and documented, and AI system output is interpreted within its context."
- MAP 1.1: "Intended purposes, potentially beneficial uses... are understood and documented." MAP 3.1: "Potential benefits of intended AI system functionality and performance are examined and documented."
- MEASURE 4.2: results "validate whether the system is performing consistently as intended." MEASURE 4.3: "Measurable performance improvements or declines... are identified and documented."
- MANAGE 4.1: post-deployment monitoring plans; MANAGE 4.2: "Measurable activities for continual improvements."
- → The RMF has the **intended-versus-actual loop at the system level**: document intended purpose and benefit, then measure whether the system performs "as intended." It does not do this per decision or per agent action. It is the closest regulatory ancestor of "expected outcome, then actual outcome." The column is effectively arguing to push this loop down from the system to the individual judgment.

### 4c. ISO/IEC 42001:2023 [NOT OPENED: standard is paywalled; SECONDARY via ISMS.online and similar]
- Annex A **A.6.2.8, "AI system recording of event logs"**: "The organisation shall determine at which phases of the AI system life cycle event log recording is enabled" (secondary quote). Also A.6.2.3 (documentation of design and development) and B.8.2 (information for users), both referenced by AICM GRC-13.
- → **What-logs plus design documentation.** A management system standard implies decision documentation at the level of the organization's AI program, not per-agent-decision rationale.

**Regulation verdict:** Regulation mandates **what** (event logs, retention) and **system-level** transparency. The only per-decision **why** is the EU Art. 86 explanation, produced on request for affected persons. No framework asks for an **expected outcome recorded at decision time**. NIST's intended-versus-actual loop is the nearest analogue, and it works at system granularity.

---

## 5. Spec-driven and intent-first AI development

- **Sean Grove (OpenAI), "The New Code," AI Engineer World's Fair, June/July 2025** [SECONDARY: quotes via Tessl blog of Jul 4, 2025. The YouTube video (https://www.youtube.com/watch?v=BIvILtt164I) was **NOT watched**.] "We keep the generated code and delete the prompt... like you shred the source and then very carefully version control the binary." "The new scarce skill is writing specifications that fully capture the intent and values." "Whoever writes the spec... is now the programmer." He uses OpenAI's Model Spec as the example. → It argues that **intent is the real artifact** and that we currently throw it away. The first half of the column's argument is already mainstream in coding circles because of this talk. The talk faces forward (spec, then generated code). It does not propose logging judgment and scoring it against outcomes.
- **GitHub Spec Kit** (Den Delimarsky, GitHub Blog, **Sep 2, 2025**) [OPENED-SUMMARY]. "We're moving from 'code is the source of truth' to 'intent is the source of truth.'" Specs are "living, executable artifacts that evolve with the project." Its checkpoints refine the spec *forward*. There is no step that compares final outcomes with the spec's expectations.
- **AWS Kiro specs** [OPENED-SUMMARY: kiro.dev/docs/specs]. `requirements.md` ("user stories and acceptance criteria in structured notation"), `design.md` (architecture, sequence diagrams, error handling and testing strategy), `tasks.md` (status tracked). The page does not name EARS or a decision-rationale section. The outcome link is limited to task completion.
- **AGENTS.md and CLAUDE.md** (convention files). These hold durable intent and rules for agents, the same pattern this repo uses. **Evidence on whether they help is mixed and new:**
  - Gloaguen, Mündler, Müller, Raychev, Vechev (ETH SRI), "Evaluating AGENTS.md: Are Repository-Level Context Files Helpful for Coding Agents?" arXiv:2602.11988 (Feb 2026, rev. Jun 2026) [OPENED-SUMMARY: abstract]: "providing context files does not generally improve task success rates, while increasing inference cost by over 20% on average"; instructions "were successfully followed" but did not raise completion.
  - arXiv:2607.27250, "Do Context Files Help Coding Agents? A Two-Agent Ablation" [NOT OPENED; search snippet]: context strategy "does not measurably move correctness" (288 runs).
  - Lulla et al., arXiv:2601.20404 (Jan 2026) [NOT OPENED; search snippet]: AGENTS.md lowers runtime and output tokens.
  - → This matters for the column. Recording intent up front, *by itself*, has weak measured benefit. That supports the column's claim that the value comes from **closing the loop** (expected versus actual, then lessons, then process updates) and not from the intent document alone. **Do not overclaim that intent files improve agents.**
- **Logging agent intent in coding workflows (the capture side):**
  - **Entire (Thomas Dohmke, ex-GitHub CEO), launched Feb 10, 2026, $60M seed** [OPENED-SUMMARY: entire.io announcement]. The open-source "Checkpoints" CLI automatically captures "AI agent context—*reasoning, prompts, and decisions*" on every Git commit, with a broader vision of storing "code, intent, constraints, and reasoning." The announcement does **not mention linking the captured context to outcomes or measuring whether it helps**. This is the most prominent current example of the column's "durable state" prescription in software (D1, D3).
  - **Cursor "Agent Trace" spec v0.1.0 (RFC, Jan 2026)** [OPENED-SUMMARY: agent-trace.dev]. Line-level attribution (human, AI, mixed, unknown), `model_id`, and conversation URL. Non-goals include "Quality Assessment: We don't evaluate whether AI contributions are good or bad." → **Who wrote it, not why.**
  - ADR-for-agents practice write-ups [NOT OPENED; search snippets only]. Several 2026 practitioner templates add "rejected alternatives" and "reconsideration triggers" for agent-read ADRs (asdecided.com, glukhov.org). This is the negative-knowledge idea (Claim 6) in circulation, but only as blog-grade material.
- **Is anyone measuring whether logged intent helps in coding?** Only the context-file ablations, which test intent *given to* the agent, not rationale *emitted by* it and scored later. **I found no study that measures the value of agent-emitted rationale linked to outcomes.**

---

## 6. Reasoning summaries and CoT as an oversight channel

- **Korbak, Balesni, et al., "Chain of Thought Monitorability: A New and Fragile Opportunity for AI Safety," arXiv:2507.11473 (Jul 2025, v2 Dec 7, 2025)** [OPENED: PDF]. The authors come from UK AISI, Apollo, METR, Anthropic, OpenAI, Google DeepMind, Meta, and others, with endorsements from Bowman, Hinton, and more.
  - Abstract: "AI systems that 'think' in human language offer a unique opportunity for AI safety: we can monitor their chains of thought (CoT) for the intent to misbehave. Like all other known AI oversight methods, CoT monitoring is imperfect."
  - As an observability channel: "A CoT monitor is an automated system that reads the CoT... and flags suspicious or potentially harmful interactions." "By studying the CoT, we can gain some insight into how our AI agents think and what goals they have."
  - Uses already demonstrated: detecting misbehavior (models write "Let's hack," or "I'm transferring money because the website instructed me to"), "discovering early signals of misalignment," and "noticing flaws in model evaluations."
  - "CoT does not need to completely represent the actual reasoning process in order to be a valuable additional safety layer."
  - It is fragile: future models "may face incentives to hide their reasoning." It recommends that developers publish monitorability evaluations in system cards and "use monitorability scores in training and deployment decisions."
  - → **Safety-oriented, real-time, adversarial.** It frames reasoning as a signal *for catching bad intent*, not as organizational knowledge. It supports the column's choice not to use raw CoT as the interface: CoT is fragile and a monitoring target, while structured rationale is a work product. (Faithfulness is covered by another sweep.)
- **Vendor reasoning artifacts** [OPENED-SUMMARY: vendor docs]:
  - OpenAI: "While we don't expose the raw reasoning tokens emitted by the model, you can view a summary of the model's reasoning using the `summary` parameter" (values include `auto`, `concise`, `detailed`). In stateless or ZDR mode, reasoning items carry `encrypted_content` that can be passed back but not read.
  - Anthropic: current Claude models return **"summarized thinking blocks"**. Thinking can be encrypted or signed for continuity (see the platform.claude.com thinking docs).
  - → The raw why is **deliberately not available** to the deploying organization. What customers get is a summary, or ciphertext for round-tripping. That is a practical argument for the column: if you want durable why, you have to ask the agent to produce it as an explicit, structured output, because you cannot recover it from the vendor's reasoning channel.

---

## 7. "Log the intention and test it later": expected versus actual

What I found, from closest to furthest:
1. **AER (Oracle, arXiv:2603.21692)** [OPENED]. Intent, alternatives rejected, confidence, "confidence calibration," and "counterfactual regression testing via mock replay." It is the nearest to "log it, test it later," but it has no expected-outcome field, and its evaluation is still planned.
2. **OTel #72 (pre-execution judgment)** [OPENED]. It records that alternatives were evaluated and which was chosen. It has no reasons and no prediction.
3. **Conviva (Sekar and Zhang) via FC** [SECONDARY]. "Stateful reasoning to connect actions to outcomes." This is the right direction at the level of an idea, but I did not see their primary text.
4. **Cognee** [OPENED-SUMMARY]. It finds which memory "correlate[s] with successful outcomes" after the fact, with no per-decision prediction.
5. **Agent world-model research** [OPENED-SUMMARY for one]. Agents predict consequences before acting, as a *control* mechanism. Qian et al., "Current Agents Fail to Leverage World Model as Tool for Foresight," arXiv:2601.03905 (Jan 7, 2026): agents "rarely invoke simulation (fewer than 1%)," "misuse predicted rollouts (approximately 15%)," and performance drops "up to 5%" with simulation available. Also Dual-Frontier (arXiv:2609.26293), about admitting a world-model decision only above an error bound [NOT OPENED]. → Prediction exists, but it is used to steer the agent in the moment, not stored for later learning. The first paper is also a caution: agents do not naturally produce or use forecasts well.
6. **Eval tooling "expected"** (Braintrust and others) [OPENED-SUMMARY]. Ground truth supplied by humans or datasets, compared with actual output in offline evals.
7. **NIST AI RMF MAP 1.1 / 3.1 and MEASURE 4.2 / 4.3** [OPENED]. Intended purpose and benefit compared with performance "as intended," at system level.

**I found no source that explicitly proposes that an agent record an expected outcome (a prediction) alongside its rationale at decision time, and that the organization later join it to the actual outcome to score judgment and update process.** The idea is familiar from human decision practice: decision journals, pre-mortems, forecasting and calibration, and after-action reviews (which the other sweeps cover). I did not find it stated for AI agents in 2024-2026. This is a negative search result, not proof of absence. My queries covered expected outcome, predicted outcome, decision journal, and calibration in combination with agent logging.

---

## Is the column's claim novel? What is covered, and what gap remains

**Already covered. Do not claim these as new:**
- **"Traditional systems record what, not why; agents make why capturable."** Foundation Capital said this almost word for word in Dec 2025 ("the 'why' becomes first-class data"; systems "can tell you what happened, but... can't tell you why"). It launched a named category (context graphs) and a VC-driven debate, and Forrester has already called it "a convergence, not an invention." **The column must acknowledge this or it will look derivative.**
- **"Keep the intent; we currently throw it away."** Sean Grove ("shred the source"), GitHub Spec Kit ("intent is the source of truth"), Kiro, and AGENTS.md all make intent a first-class artifact in coding.
- **"Capture the agent's reasoning and decisions durably."** Entire's Checkpoints (Feb 2026, $60M) does this on every commit. CSA's own Agentic Trust Framework requires "Ability to retrieve rationale for agent decisions."
- **A structured schema of intent, evidence, and rejected alternatives.** The Oracle AER paper (Mar 2026) has intent, observation, inference, plan revision rationale, `alternatives_rejected`, and confidence.
- **"Rationale is not truth."** OWASP ASI09 ("Fake Explainability"), Joseph Jude ("the story we tell ourselves"), FC's own pushback section, and AER's "post-hoc rationalization" caveat all make this point.
- **Declared intent as a control.** OWASP intent capsules and intent-bound tokens, IETF Intent Admission Assertions, and CSA ORCHIDEAS intent tokens.

**Still open, and where the column can stake a defensible claim:**
1. **Expected outcome as a first-class field, scored later.** No standard (OTel, OWASP, AICM, EU AI Act, ISO 42001), tool (Langfuse, Braintrust "expected" is evaluator ground truth), or startup pitch (FC, Entire, Agent Trace) records the *agent's own prediction* at decision time for later comparison with reality. NIST does intended-versus-actual only at system level. **"Log the prediction, not just the permission" is the column's sharpest distinct move.**
2. **Linking why to outcome, as opposed to why to precedent.** Context graphs learn *consistency* ("act the way we acted before"). The column wants *correction* ("find out which of our judgments were wrong and change the process"). FC's own follow-up flags Conviva's "connect actions to outcomes" as the next step, which confirms that the gap is recognized and unfilled.
3. **Organizational learning, not audit, security, or moat.** Every existing treatment of why serves audit and forensics (EU Art. 12, AICM LOG, OWASP), authorization (intent tokens), safety monitoring (CoT monitorability), debugging (observability vendors), or a commercial system of record (FC). None frames it as the substrate for an organization improving its own workflows, evaluators, and resource allocation. That is the column's GPT, complementary-redesign, workslop frame.
4. **Declared and then tested, as opposed to inferred.** FC retreats to "infer the why from the how" because human intent is unobservable. The column can say what is different about agents: they can be *required* to state intent, assumptions, and an expected outcome cheaply, as structured output, and the organization then *tests* those statements against actions (AER-style reconciliation) and outcomes. This answers both FC's "you can't capture why" and OWASP's "rationales can be faked."
5. **Negative knowledge.** Rejected alternatives appear in AER's schema, OTel #72, and practitioner ADR templates. Tracking *recurrence* of rejected ideas ("repeated rejection is itself telemetry") as an organizational signal was not found anywhere.

**Suggested honest framing for the column (one or two sentences):** "Investors are already calling decision traces AI's next trillion-dollar layer, and coding tools already save the agent's reasoning with every commit. What almost no one records yet is the part that makes judgment learnable: what the agent expected to happen, and whether it did."

**Evidence cautions for drafting:**
- Context-file ablations (ETH, arXiv:2602.11988) show that intent *given to* agents does not reliably improve outcomes. Do not imply that capturing intent pays off by itself. The loop is the claim.
- Qian et al. (arXiv:2601.03905) shows that agents rarely use forecasts well. Expected-outcome fields will need prompting or structure, and their quality is itself something to measure.
- OTel GenAI conventions are all Development status, and every open "decision" proposal is about governance gates. If the column says "no standard has a field for why," the accurate phrasing is: "the emerging OpenTelemetry conventions record plans, reasoning text and allow/deny decisions, but have no field for intent, rationale or expected outcome" (verified 2026-09-24).
- CSA self-reference: AICM has explainability (GRC-13, GRC-14) and logging (LOG-07, LOG-09, LOG-16) but no per-decision rationale or expected-outcome control. This is a candidate Labs recommendation, not a column claim, unless Kurt wants to name it.

## Source status summary
- **OPENED:** FC essay (Dec 22, 2025); FC follow-up (Jan 30, 2026); OTel GenAI semconv repo and issues #72, #239, #461; OWASP Agentic Top 10 2026 PDF; AICM v1.1.1 via CSA MCP (GRC-13 full; others as CAIQ text); CSA ATF blog; CSA ORCHIDEAS blog; EU AI Act Art. 12, 13, 86; NIST AI RMF PDF; AER arXiv:2603.21692 PDF; CoT Monitorability arXiv:2507.11473 PDF.
- **OPENED-SUMMARY (spot-check quotes):** Garg Substack; Jude; Forrester/Betz; Cognee; Braintrust attributes; Langfuse data model; arXiv:2605.12078, 2606.20669, 2602.11988, 2601.03905 abstracts; IETF intent-admission draft; GitHub Spec Kit blog; Kiro docs; Entire announcement; Agent Trace spec; OpenAI and Anthropic reasoning docs.
- **SECONDARY only:** Sean Grove talk quotes (via Tessl); ISO/IEC 42001 A.6.2.8 text (via ISMS.online); Digital Omnibus dates and OJ publication; Neo4j agent memory; Conviva's outcome-linking argument.
- **NOT OPENED:** Forbes (403); Latent.Space AINews; Subramanya; Year of the Graph; LangSmith and Arize docs; other IETF agent drafts; arXiv:2607.27250, 2601.20404, 2609.26293, 2603.24775; CSA "AI Liability Inflection," "Visibility Gap," Red Teaming Guide, OMB M-26-14 note; ADR-for-agents blogs; Grove video.

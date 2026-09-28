# Sweep 2: Prior art on capturing "why" (rationale, intent, and expected versus actual outcomes)

For: "Why Is Telemetry" (circle-news-monthly-column/research/2026-09-24-why-is-telemetry/)
Date: 2026-09-24
Question: who already went first with logging intent, in the pre-AI human-organization world, and what happened?

Legend: **[OPENED]** means I read the primary source and the quote is exact. **[OPENED-SECONDARY]** means the quote comes from a secondary source I read, not from the original. **[NOT OPENED]** means I could not reach the primary; the claim rests on search snippets or on other papers citing it, so verify before citing.

Column claim IDs used below: A4 (judgment becomes data), A5 (compare expected with actual), A6 (rationale is not truth), D1 (durable addressable state), D2 (the state list), D3 (GitHub as example), D4 (structured rationale, not chain of thought), D5 (negative knowledge).

---

## 0. Bottom line (read this first)

1. **Capturing rationale is not a new idea. It has been tried for 55 years, and every generation repeats the same shape.** IBIS (1970), QOC/DRL/gIBIS (1991), Compendium (2005), ADRs (2011), PEP/RFC/KEP templates, and decision journals all capture intent, alternatives, and rejected options. D2's list is almost field-for-field the Farnam Street decision journal template, plus MADR's "Considered Options"/"Confirmation", plus the AAR's "what was supposed to happen".
2. **The failures are well documented, and they are about economics and emotion, not about templates.** Grudin (1996) is the canonical source: the person who records the rationale is usually not the person who benefits; most projects die before anyone uses the rationale; the rationale "can become a record of failure"; and the real reasons are often politically unsayable. Buckingham Shum et al. (2005) call capture "the spectre haunting all design rationale efforts." Levitt & March (1988) say "a good deal of experience is unrecorded simply because the costs are too great", and that comparisons of projected with realized returns are routinely "ignored." That last point is exactly A5 failing in the wild.
3. **Where capture worked, it did so because either (a) the record gave value *now*, or (b) an institution required it.** Examples: the Compendium "value now, value later" facilitation approach; the NCR field trial, where reconstruction found omissions that would have cost 3 to 6 times the capture cost; PEP 1 making the author "responsible for... documenting dissenting opinions"; the Linux kernel requiring the problem statement; AAR doctrine; Tetlock's tournaments, which score every forecast.
4. **What AI actually changes (supportable with sources):** (i) capture cost falls, because machines can now extract and draft rationale from messy records, which Buckingham Shum in 2005 called "very challenging"; (ii) the beneficiary mismatch shrinks, because the AI agent is itself an immediate consumer of the "why" in its next session; (iii) capture can happen at decision time in the execution path instead of by post-hoc reconstruction; (iv) captured rationale can now be *scored* at scale. Tetlock's group used LLMs to score 55,000+ forecast explanations and found the scores predict accuracy. That result is the column's A4 in its most literal form.
5. **What AI does NOT change:** the politics of stating real reasons, the emotional cost of recording failure, and the reconstruction-bias problem. Machine-generated rationale is often post-hoc and unfaithful (Anthropic 2025: models mentioned the hint they used only 25 to 39% of the time). This supports A6 and D4 directly.

---

## 1. Design rationale research

### 1.1 IBIS: Kunz & Rittel (1970), "Issues as Elements of Information Systems"
- **Status: [NOT OPENED].** The USF PDF mirror failed (socket closed), and eScholarship returned an HTML wrapper. Metadata comes from search: Working Paper 131, Institute of Urban and Regional Development, UC Berkeley, July 1970. Primary: http://magrawal.myweb.usf.edu/phd/articles/ibis_wp_70.pdf ; https://escholarship.org/uc/item/5cj786v8
- **What it is:** a method for structuring planning and political decision processes as issues, positions, and arguments. Rittel is also the author of "wicked problems."
- **Evidence of usefulness:** indirect, through its descendants (gIBIS, QuestMap, Compendium; see 1.4 and 1.5).
- **Maps to:** D2 (alternatives plus arguments). It is the ancestor of every "alternatives considered" section.

### 1.2 QOC: MacLean, Young, Bellotti & Moran (1991), "Questions, Options, and Criteria: Elements of Design Space Analysis," *HCI* 6(3-4):201-250
- **Status: [NOT OPENED]** (paywalled). The abstract comes via search: QOC represents "the design space around an artifact": Questions, Options, and Criteria "for assessing and comparing the Options."
- **Adoption barrier (via Buckingham Shum et al. 2005, [OPENED]):** novices had to juggle four interleaving cognitive tasks ("unbundling... classification... naming... and structuring"), and "reports of cognitive overhead should not be surprising."
- **Maps to:** D2 (criteria = the evaluator and threshold). D4: structure is where the value is, and structure is also where the cost is.

### 1.3 DRL: Jintae Lee
- Lee (1991), "Extending the Potts and Bruns Model for Recording Design Rationale," ICSE-13; SIBYL (CSCW 1990). **[NOT OPENED]**
- **Lee (1997), "Design Rationale Systems: Understanding the Issues," *IEEE Expert*, May/June 1997: [OPENED]** https://users.cs.northwestern.edu/~paritosh/papers/sketch-to-models/LeeDesignRationaleSystems.pdf
  - Scope: rationales include "not only the reasons behind a design decision but also the justification for it, the other alternatives considered, the tradeoffs evaluated, and the argumentation that led to" the decision.
  - On the capture method he calls **reconstruction**: "the cost of reconstruction is high and it may introduce the biases of the person producing the rationales." (This is an A6 warning, and it applies directly to LLM post-hoc rationale.)
  - On **automatic generation** from an execution history: it "has the appeal of creating rationales at little cost to the user later... However... many issues at the core of machine-learning research must be resolved: what parts of the problem-solving trace must be captured and how, how to infer rationales from the trace, how to assess their relevance." **This is a 1997 statement that the missing piece was ML. It is the cleanest "AI changes the economics" hook in the old literature.**
  - "When the cost bearer is not the same as the beneficiary, providing a cost-effective system becomes more problematic... many groupware systems fail exactly because of this mismatch" (citing Grudin).
- **Maps to:** A6 and D4 (reconstruction bias). The "what's new" point is that the ML problem Lee named is now partly solved.

### 1.4 gIBIS / itIBIS at NCR: Conklin & Burgess-Yakemovic (1991), "A Process-Oriented Approach to Design Rationale," *HCI* 6(3-4)
- **Status: primary [NOT OPENED]** (tandfonline 403). Findings come from search abstract snippets and from Lee 1997 [OPENED-SECONDARY].
  - Search abstract: the approach aims to capture "a trace of the rationale... with little disruption of the normal process". An industrial field trial used "low-tech" indented-text IBIS to capture "more than 2,300 requirements and design decisions" (the number comes from the snippet; verify it).
  - Lee 1997, citing that work: "the reconstruction process helped them identify several design omissions that would have cost three to six times more than the cost of capturing and reconstructing the rationales."
- **This is the best pre-AI evidence that capture paid off.** Note that the payoff came *during design*, from the discipline of articulating the rationale, not from later retrieval.
- **Maps to:** D1 and D2. There is also a subtle point for the column: the first beneficiary of writing down the why is the current work, not the future reader.

### 1.5 Compendium: Buckingham Shum, Selvin, Sierhuis, Conklin, Haley & Nuseibeh (2005/2006), "Hypermedia Support for Argumentation-Based Rationale: 15 Years on from gIBIS and QOC," KMi TR-05-18: [OPENED]
https://kmi.open.ac.uk/publications/pdf/KMI-05-18.pdf
- "The capture problem is the spectre haunting all design rationale efforts (indeed, all knowledge management efforts attempting to meaningfully capture elements of human reasoning and discourse)."
- "As Grudin has pointed out, there cannot be a disparity between who invests effort in a groupware system, and who benefits. No designer can be expected to altruistically enter quality design rationale solely for the possible benefit of a possibly unknown person at an unknown point in the future for an unknown task. There must be immediate value."
- "One could minimize the capture effort and simply video record every design meeting, but this would not render a useful archive. Computationally tractable structure must be added by some means. **Extracting useful content automatically from multimedia meeting records is an active research area, but very challenging.**" (This is the 2005 baseline; see §7 for what changed.)
- A 1994 survey "found comparatively weak evidence regarding usability and utility compared to what might have been expected given the scale of system development efforts," and the authors point to "the pattern of failure in many kinds of interactive systems that assume the willingness of users to structure information."
- The QuestMap commercial product "ultimately succumbed to market pressures."
- What worked was real-time facilitation ("Dialogue Mapping"): "the structure required to construct useful DR is added in real time during the meeting, adding immediate value to the participants, but also creating a record." Compendium "has been used on over 100 projects during the last 10 years." They also admit: "All of this evidence is from the field, often anecdotal."
- **Maps to:** D1. The design lesson is "value now, value later." A skilled human mapper made capture cheap and useful; an AI in the loop can play the mapper's role.

### 1.6 WHY capture failed: Grudin (1996), "Evaluating Opportunities for Design Capture," in Moran & Carroll (eds.), *Design Rationale: Concepts, Techniques, and Use*, 453-470: [OPENED]
http://jonathangrudin.com/wp-content/uploads/2017/03/DesRat1996.pdf

This is the single most important source for the column's "someone has to go first" framing. Key exact quotes:
- The overlooked datum: "Many development projects have little or no downstream activity that will benefit from such an investment—because they are not completed. Even when a project is completed, a different organization is often responsible for maintenance... And any project, by diverting resources to capture design rationale, may reduce its likelihood of surviving or succeeding."
- The mismatch between who pays and who benefits: "A chronic cause of failure in group work situations... occurs when one group incurs additional work (in this case, the developers) and another group benefits (in this case, customer service)."
- "the advocate of design rationale must ask a developer to undertake an effort that will slow down the project, be discarded unused in the likely event that the project is terminated, and in the best outcome will benefit someone else."
- The evidence gap: "So far, immediate benefits have not been shown and existing systems require substantial effort to capture design rationale." A tool team that captured its own rationale "ended up pessimistic about the approach."
- Politics: "Will social, political, and motivational concerns prevent the explicit statement of the real reasons underlying design choices... a certain group might not be deemed capable of a tricky implementation, but it is not politic to state this explicitly; the introduction of the design capture tool could shift decision-making power to skillful tool users, who could game the new system."
- Context loss: "Accurate interpretation of captured design rationale could require more knowledge of the context that existed at the time of capture than can possibly be recorded."
- **Negative knowledge and failure (directly relevant to D5):** "At the research consortium MCC, one of the most frequent requests from shareholder companies was that researchers document not only their successes, but also their failures: paths tried and abandoned. The shareholders did not find it stressful to contemplate the examination of our failures, but we researchers did. We could not bring ourselves to make this effort."
- "who would trust a rationale that supported a failure? And more importantly, who would help build a rationale if their prior experience suggested it would be a record of failure?... Ignore human nature at your peril."
- Conclusion: "It can slow down a project... It can become a record of failure... To overcome these obstacles, design rationale systems must provide considerable collective benefit. Those who have to do the work of recording design information should perceive themselves as benefiting from the use of the record."
- **Maps to:** the strongest "this is not new, and it failed" objection (§8). It also sharpens A6: the logged why is shaped by what people are willing to say, not only by what they believe.

### 1.7 Does AI change the capture-cost economics? Who argues it explicitly
- **Zhou, Li, Liang, Zhang, Shahin, Li & Yang, "Using LLMs in Generating Design Rationale for Software Architecture Decisions," arXiv:2504.20781 (Apr 2025, revised Dec 2025): [OPENED abstract].** "DR is often inadequately documented due to a lack of motivation and effort from developers." Five LLMs were tested. Precision was 0.267-0.278 and recall 0.627-0.715. "64.45% to 69.42% of the arguments of DR not mentioned by human experts are also helpful... 1.59% to 3.24% of the arguments are potentially misleading." In plain terms: high recall and low precision, and the models surface considerations the humans missed.
- **Gupta, Dhar, Feitosa & Vaidhyanathan, "Context Matters: Evaluating Context Strategies for Automated ADR Generation Using LLMs," arXiv:2604.03826 (Apr 2026): [OPENED abstract].** ADRs' "creation and maintenance are often neglected due to the associated authoring overhead"; "context engineering, rather than model scale alone, is the dominant factor."
- **da Silva & Gama, "GADR: Gathering Architecture Decision Records from Meeting Transcriptions," arXiv:2608.17694 (Aug 2026): [OPENED abstract].** Decisions "emerge from informal, noisy meetings where choices are implicit, fragmented, and entangled with off-topic dialogue." A multi-agent pipeline turns transcripts into Nygard ADRs and "captures most expert-identified decisions." The caveat is that retrieval-augmented enrichment introduces "transcript-unfaithful content." **This answers Buckingham Shum's 2005 "very challenging" problem directly, and it also reproduces Lee's 1997 reconstruction-bias warning.**
- **arXiv:2506.11005, "Automated Extraction and Analysis of Developer's Rationale in Open Source Software" (2025): [NOT OPENED]** (search snippet only). It uses LLMs to extract rationale and detect reasoning conflicts in the Linux OOM-killer.
- **Equal Experts (Louw, Hmeid & Brabban, 27 Oct 2025), "Accelerating ADRs with Generative AI": [OPENED].** "we might generate dozens of ADRs in a single morning." The caveats: "ADRs are important design artefacts. If they're wrong, they quickly become noise"; they saw hallucinated facts and mismatched justifications; "human review remains key."
- **Foundation Capital, "AI's trillion-dollar opportunity: Context graphs" (Jaya Gupta & Ashu Garg per search; the page displayed "Sep 17, 2026" and no byline, but third-party posts from Jan 2026 already cite it, so the original is late 2025; verify): [OPENED].** "the reasoning connecting data to action was never treated as data in the first place." Agents are "in the execution path" at decision time: "Because it's executing the workflow, it can capture that context at decision time—not after the fact via ETL, but in the moment, as a first-class record." "captured decision traces become searchable precedent." This is the most explicit commercial statement of the column's thesis. **Note the vendor and VC framing, and the overlap with the column's thesis: the column should cite it as a parallel view, not as evidence.**
- **Verdict:** people are explicitly arguing that AI lowers capture cost, and in Foundation Capital's case that agents make capture a by-product of doing the work. I found **no one who explicitly engages Grudin's beneficiary-mismatch argument and says AI dissolves it.** That argument is available to the column as an original synthesis (see §7).

---

## 2. Architecture Decision Records

### 2.1 Nygard (15 Nov 2011), "Documenting Architecture Decisions": [OPENED]
https://www.cognitect.com/blog/2011/11/15/documenting-architecture-decisions
- "One of the hardest things to track during the life of a project is the motivation behind certain decisions."
- A newcomer without the rationale has two choices: "Blindly accept the decision" or "Blindly change it... changing the decision without understanding its motivation or consequences could mean damaging the project's overall value." (This is Chesterton's fence as engineering practice, and it is exactly the column's Python-library/MCP example.)
- The sections are Title, Context, Decision, Status (proposed/accepted/deprecated/superseded), and Consequences.
- "If a decision is reversed, we will keep the old one around, but mark it as superseded. (It's still relevant to know that it _was_ the decision, but is _no longer_ the decision.)"
- **Maps to:** D1, D3, and D5 (superseded decisions are kept as data). The column's software example is essentially Nygard's argument.

### 2.2 MADR (Markdown Architectural Decision Records), 4.0.0, 17 Sep 2024: [OPENED]
https://adr.github.io/madr/
- The sections include "Considered Options," "Decision Outcome," "Consequences," "Pros and Cons of the Options," and **"Confirmation"** (how compliance with the decision will be verified).
- **Maps to:** D2. "Confirmation" is a half-step toward A5, since it verifies compliance. But **no ADR template I checked has a field for "expected outcome" or "what actually happened."** The expected-versus-actual loop the column proposes is absent from ADR practice. That is a genuine gap the column can name.

### 2.3 ThoughtWorks Technology Radar: [OPENED]
https://www.thoughtworks.com/radar/techniques/lightweight-architecture-decision-records
- "Lightweight Architecture Decision Records" entered at Trial (Nov 2016), stayed Trial (Mar 2017), and moved to Adopt (Nov 2017 and May 2018). The May 2018 text reads "For most projects, we see no reason why you wouldn't want to use this technique." It is not on the current edition, which is normal once a technique becomes mainstream.

### 2.4 Empirical adoption
- **Buchgeher, Schöberl, Geist, Dorninger, Haindl & Weinreich (2023), "Using Architecture Decision Records in Open Source Projects: An MSR Study on GitHub," *IEEE Access*: [OPENED abstract, via JKU portal].** "About 50% of all repositories with ADRs contain just one to five ADRs suggesting that the concept has been tried but not yet definitively adopted." Adoption is low but growing, and systematic use is a multi-person effort over long periods. Nygard's template dominates.
- **Tang, Ali Babar, Gorton & Han (2006), "A survey of architecture design rationale," *JSS* 79(12): [NOT OPENED]** (search snippet only). 81 practitioners "recognize the importance of documenting design rationale," but there was little empirical evidence at the time about how they actually document it.
- **arXiv:2609.07375, "A Text Mining and Classification Approach for Analyzing Architecture Decision Records": [NOT OPENED]** (snippet: about 4,300 ADRs analyzed).
- **Pattern:** people endorse ADRs but rarely sustain them. That is Grudin's prediction, confirmed about 30 years later.

### 2.5 ADRs as input for AI agents (the beneficiary shift)
- **Chris Swan (10 Jul 2025): [OPENED].** ADRs offer "enough structure to ensure key points are addressed, but in natural language, which is perfect for things based on Large Language Models (LLMs)." He predicts ADRs will move from an elite practice to a standard one when working with AI assistants.
- **Stetsenko, "Lore: Repurposing Git Commit Messages as a Structured Knowledge Protocol for AI Coding Agents," arXiv:2603.15566 (Mar 2026): [OPENED abstract].** It names the "Decision Shadow": the constraints, **rejected alternatives**, and forward-looking reasoning lost from commits, an "accelerating loss of institutional knowledge" as AI becomes "both producer and consumer of source code." It proposes git trailers for constraints, rejected alternatives, and verification metadata.
- **Maps to:** D3, D5, and the "what's new" argument. The consumer of the why now includes a machine that needs it *tomorrow morning*, not a hypothetical maintainer years from now.

---

## 3. Open-source institutionalized rationale and negative knowledge

### 3.1 Python PEP 1 / PEP 12: [OPENED]
- PEP 1: "We intend PEPs to be the primary mechanisms for proposing major new features, for collecting community input on an issue, and for documenting the design decisions that have gone into Python." "The PEP author is responsible for building consensus within the community and documenting dissenting opinions." Rationale should "describe why particular design decisions were made" and "describe alternate designs that were considered and related work." Rejected Ideas records ideas "which are not accepted" and "the reasoning as to why they were rejected" (the page also frames this as preventing rehashing; I have not confirmed the exact wording, so paraphrase it).
- PEP 12 template: Rationale: "[Describe why particular design decisions were made.]" Rejected Ideas: "[Why certain ideas that were brought while discussing this PEP were not ultimately pursued.]"
- **Maps to:** D5, the cleanest institutional example of negative knowledge used to stop re-litigation. PEP 1 also makes *dissent* part of the record, which cuts against a single-narrative rationale and supports A6.

### 3.2 Rust RFC template: [OPENED]
https://github.com/rust-lang/rfcs/blob/master/0000-template.md
- Drawbacks: "Why should we *not* do this?"
- Rationale and alternatives: "Why is this design the best in the space of possible designs? What other designs have been considered and what is the rationale for not choosing them? What is the impact of not doing this?"
- Prior art: "Discuss prior art, both the good and the bad."
- **Maps to:** D2 and D5. "What is the impact of not doing this?" works as an expected-outcome prompt.

### 3.3 Kubernetes KEP template: [OPENED]
- Non-Goals: "Listing non-goals helps to focus discussion and make progress."
- Drawbacks: "Why should this KEP _not_ be implemented?"
- Alternatives: "What other approaches did you consider, and why did you rule them out? These do not need to be as detailed as the proposal, but should include enough information to express the idea and why it was not acceptable."
- Implementation History: tracks milestones through "when the KEP was retired or superseded."
- **Maps to:** D5, and to D1 (a lifecycle with versions).

### 3.4 Oxide RFDs: Jessie Frazelle, "RFD 1: Requests for Discussion" (24 Jul 2020): [OPENED]
- "Writing down ideas is important: it allows them to be rigorously formulated (even while nascent), candidly discussed and transparently shared."
- It borrows from IETF RFC 3: "Notes are encouraged to be timely rather than polished" (the IETF quote is [OPENED-SECONDARY] via Oxide).
- The **abandoned** state applies when "an idea is found to be non-viable (that is, deliberately never implemented)."
- **Maps to:** D5, since abandoned ideas stay addressable. "Timely rather than polished" is also the right norm for why-telemetry, and the opposite of workslop.

### 3.5 Google design docs: Malte Ubl, "Design Docs at Google" (6 Jul 2020): [OPENED]
https://www.industrialempathy.com/posts/design-docs-at-google/
- "The design doc is _the place to write down the trade-offs_ you made in designing your software."
- Alternatives considered is "one of the most important" sections: "The focus should be on the trade-offs that each respective design makes and how those trade-offs led to the decision."
- Design docs "Form the basis of an organizational memory around design decisions."

### 3.6 IETF
- Covered only through RFC 3's norm (above). I did not open any IETF process document that mandates recording rationale. **Gap.** The IETF records rationale mostly in mailing-list archives and datatracker history, not in a required RFC section.

### 3.7 Commit-message conventions
- **Linux kernel, "Submitting patches": [OPENED]** https://www.kernel.org/doc/html/latest/process/submitting-patches.html
  - "Describe your problem. Whether your patch is a one-line bug fix or 5000 lines of a new feature, there must be an underlying problem that motivated you to do this work."
  - "The explanation body will be committed to the permanent source changelog, so should make sense to a competent reader who has long since forgotten the immediate details of the discussion that might have led to this patch."
- **Chris Beams, "How to Write a Git Commit Message" (31 Aug 2014): [OPENED]** https://cbea.ms/git-commit/
  - Rule 7: "Use the body to explain _what_ and _why_ vs. _how_."
  - "a well-crafted Git commit message is the best way to communicate _context_ about a change to fellow developers (and indeed to their future selves)."
- **Maps to:** D3 (the GitHub history example). The kernel example is useful because it is *enforced by reviewers*, which is how the capture-cost problem gets solved institutionally: the gatekeeper will not merge without the why.

---

## 4. Decision journals and judgment as data

### 4.1 Annie Duke: "resulting" and the Knowledge Tracker
- **Infinite Loops podcast transcript (Jim O'Shaughnessy, Ep. 22): [OPENED]** https://www.osam.com/pdfs/Annie_Duke_Transcript.pdf
  - "I want to key in on an evidentiary record, because I think that's really important. So, let's assume we don't have an evidentiary record. We can't go back and look, then you want to basically create something, which I would call a knowledge tracker."
  - "what is the stuff that I knew beforehand, or was knowable beforehand. And what's the stuff that I knew afterwards."
  - "you're obviously you're trying to build this in retrospect, but by going through this process, you're more likely to get a little closer to objective."
  - "Resulting" means judging decision quality by outcome quality (the host's framing in the transcript).
- *Thinking in Bets* (2018) and *How to Decide* (2020): **[NOT OPENED]** (books).
- **Maps to:** A5 and A6. Duke's Knowledge Tracker is a *workaround for the absence of an evidentiary record*. It reconstructs after the fact what should have been captured at decision time. The column can argue that why-telemetry is that evidentiary record, captured up front. It is also the fix for resulting, because only a record of what was known and expected lets you tell a bad decision from bad luck.

### 4.2 Kahneman's decision-journal advice
- **[NOT OPENED as primary].** The widely circulated quote ("Go down to a local drugstore and buy a very cheap notebook and start keeping track of your decisions"; write down "what you expect to happen, why you expect it to happen"; it counters hindsight bias) is attributed to a Kahneman conversation with Michael Mauboussin. I only found it on secondary blogs. The CFA Institute write-up I opened (McCaffrey, 2018) contains Kahneman on hindsight ("When something happens, you immediately understand how it happens. You immediately have a story and an explanation") but **not** the journal advice. **Do not quote the notebook line without a primary.**

### 4.3 Farnam Street decision journal (Shane Parrish, 2014, updated): [OPENED]
https://fs.blog/decision-journal/
- Template fields include "The situation or context," "The problem statement or frame," "The variables that govern the situation," "Alternatives that were seriously considered and why they were not chosen," "A paragraph explaining the range of outcomes," "A paragraph explaining what you expect to happen and the reasoning and actual probabilities you assign to each projected outcome," and "The time of day you're making the decision and how you feel physically and mentally."
- **Maps to:** D2, nearly one to one. **This is the most direct "this is not new" exhibit:** the column's list of intent, evidence, assumptions, alternatives, rejected alternatives, and expected outcome, with probabilities, is a consumer self-help template. What the template lacks is the *organizational* part: shared, queryable, linked to outcomes, and aggregated across people.

### 4.4 Bridgewater (Dalio): Dot Collector, Baseball Cards, believability weighting: [OPENED, principles.com]
https://www.principles.com/principles/633d5d13-8610-425f-ad62-cd62347d9165/
- "At Bridgewater everyone's believability is tracked and measured systematically, using tools such as Baseball Cards and the Dot Collector that actively record and weigh their experience and track records."
- Believable people "have repeatedly and successfully accomplished the thing in question" and "have demonstrated that they can logically explain the cause-effect relationships behind their conclusions."
- The Dot Collector "displays both the equal-weighted average and the believability-weighted results (along with each person's vote)."
- **Maps to:** A4, since judgment literally becomes data at an organizational scale. **Caution:** Bridgewater is a contested exemplar (well-publicized accounts of the culture as coercive surveillance). If the column uses it, it doubles as a warning about why-telemetry turning into a panopticon, which connects to Grudin's politics point. What Bridgewater scores is *people's* judgment, not decisions' rationale. That is a different design choice from the column's, and the column should say which one it means.

### 4.5 Tetlock: Good Judgment Project, forecast logging plus Brier scoring
- **Mellers et al. (2014), "Psychological Strategies for Winning a Geopolitical Forecasting Tournament," *Psychological Science*: [OPENED]** https://sydneyscott.nfshost.com/pubs/Psychological_Strategies_for_Winning_a_G.pdf
  - The groups competed "to assign the most accurate probabilities to events in a 2-year geopolitical forecasting tournament." The three drivers were "training, teaming, and tracking." "Teaming allowed forecasters to share information and discuss the rationales behind their beliefs." "Training, teaming, and tracking are psychological interventions that dramatically increased the accuracy of forecasts."
- **Karvetski, Meinel, Maxwell, Lu, Mellers & Tetlock, "Forecasting the Accuracy of Forecasters from Properties of Forecasting Rationales" (SSRN 3779404, manuscript): [OPENED]**
  - Earlier innovations "focused on easier-to-quantify variables... and bypassed messier constructs, like qualitative properties of forecasters' rationales." Findings: "top forecasters show higher dialectical complexity in their rationales, use more comparison classes, and offer more past-focused rationales," and training and teaming shift rationales "in a 'superforecaster-like' direction."
- **Zong, Ritter & Hovy (2020), "Measuring Forecasting Skill from Text," ACL: [OPENED abstract]** "it is possible to accurately predict forecasting skill using a model that is based solely on language."
- **Karvetski, Huang, Kučinskas, Flechner, Hu, Tetlock & Karger, "Measuring Judgment Quality in Natural-Language Explanations: Evidence from Forecasting Tournaments," arXiv:2606.30987 (29 Jun 2026): [OPENED abstract]**
  - "sixty theory-guided reasoning patterns scored by large language models," applied to more than 55,000 forecast-explanation pairs. These "Explanation Quality Markers" outperformed traditional text analysis. "the signal is asymmetric: EQMs identify likely underperformers more reliably than they distinguish the very best forecasters." Human raters "place disproportionate weight on rationale length."
- **Maps to:** A4 and A5 in the most literal form available. GJP shows that logging judgments *with expected outcomes (probabilities)* and scoring them against outcomes improves judgment. The 2026 paper shows **LLMs can score the written why itself and predict judgment quality**. That is the strongest source-backed "what's new with AI" answer (§7). The asymmetry (better at flagging bad reasoning than at crowning good reasoning) is a useful, honest caveat. The finding that human raters are fooled by length maps onto workslop.

### 4.6 Gary Klein: premortem, "Performing a Project Premortem," *HBR*, Sep 2007: [OPENED]
- "Research conducted in 1989 by Deborah J. Mitchell, of the Wharton School; Jay Russo, of Cornell; and Nancy Pennington, of the University of Colorado, found that prospective hindsight—imagining that an event has already occurred—increases the ability to correctly identify reasons for future outcomes by 30%."
- "By making it safe for dissenters who are knowledgeable about the undertaking and worried about its weaknesses to speak up, you can improve a project's chances of success."
- **Maps to:** D2 (assumptions and failure modes captured before the fact) and A5 (the premortem list is the expected-failure hypothesis set to compare against actual outcomes). The Mitchell/Russo/Pennington 1989 primary is [NOT OPENED].

### 4.7 US Army After Action Review
- **TC 25-20, "A Leader's Guide to After-Action Reviews" (Sep 1993): [OPENED]**
  - An AAR "enables soldiers to discover for themselves what happened, why it happened, and how to sustain strengths and improve on weaknesses."
  - The format lists "Commander's mission and intent (what was supposed to happen)." "Summary of recent events (what happened)." "Discussion of key issues (why it happened and how to improve)."
  - "An AAR is not a critique. No one, regardless of rank, position, or strength of..." (a no-blame norm).
- **The Leader's Guide to AARs (Dec 2013): [OPENED]** Facilitators "provide an overview of the event plan (what was supposed to happen) and facilitate a discussion of what actually happened during execution."
- The widely quoted four-question form ("What was supposed to happen? What actually happened? Why was there a difference? What will we sustain or improve?") appears in secondary sources. I did not find the exact four-question wording in TC 25-20 itself, so cite TC 25-20's wording instead.
- **Maps to:** A5, the purest organizational precedent. **Key insight for the column:** the AAR only works because *intent was recorded before execution* (commander's intent, OPORD). The "what was supposed to happen" is a pre-registered expectation. The Army also instrumented the "what" (TC 25-20 lists communications recordings and video of key events). The AAR is literally "what" telemetry plus a pre-recorded "why," compared after the fact.

### 4.8 Amazon: six-page narratives and one-way/two-way doors
- **2017 shareholder letter: [OPENED]** "We don't do PowerPoint (or any other slide-oriented) presentations at Amazon. Instead, we write narratively structured six-page memos." Writers wrongly "believe a high-standards, six-page memo can be written in one or two days or even a few hours, when really it might take a week or more!"
- **2016 letter: [OPENED]** "Many decisions are reversible, two-way doors. Those decisions can use a light-weight process." "Most decisions should probably be made with somewhere around 70% of the information you wish you had." "Disagree and commit."
- The 2015 letter's Type 1/Type 2 passage returned 404: **[NOT OPENED]**.
- PR/FAQ (working backwards): **[NOT OPENED]**.
- **Maps to:** D1 and D4. The door distinction offers a principled answer to "not everything": capture why in proportion to irreversibility. The "week or more" line shows the capture cost of *good* rationale, and it is also the workslop warning, since an AI-generated six-pager in an hour can look like the artifact without the thinking.

---

## 5. Organizational learning theory

### 5.1 Argyris: double-loop learning
- **"Teaching Smart People How to Learn," *HBR* May-June 1991: [OPENED]**
  - "a thermostat that automatically turns on the heat whenever the temperature in a room drops below 68 degrees is a good example of single-loop learning. A thermostat that could ask, 'Why am I set at 68 degrees?' and then explore whether or not some other temperature might more economically achieve the goal of heating the room would be engaging in double-loop learning."
  - "Highly skilled professionals are frequently very good at single-loop learning." (He goes on to describe their defensive reasoning.)
- "Double Loop Learning in Organizations," *HBR* Sep 1977: **[NOT OPENED]** (paywall; only the Product X anecdote was visible).
- **Maps to:** the article's pivot. **"Why am I set at 68 degrees?" is a thermostat asking for why-telemetry**, which gives the column a ready-made observability-native image. Traditional telemetry supports single-loop learning (deviation from setpoint). Recording the reason for the setpoint is what makes double-loop learning possible. Argyris's defensive-reasoning point also supports A6: professionals' stated reasons are systematically self-protective.

### 5.2 Walsh & Ungson (1991), "Organizational Memory," *AMR* 16(1):57-91
- **[NOT OPENED]** (the Scribd copy failed to load; the AOM copy is paywalled). Secondary sources describe five retention "bins" (individuals, culture, transformations, structures, ecology, plus external archives) and the claim that only individuals (and possibly culture) retain both the decision stimulus and the response, meaning the why is held mostly in people's heads. **Verify before quoting.**
- **Maps to:** D1. The column's claim is that the why lives in individuals and walks out the door.

### 5.3 Levitt & March (1988), "Organizational Learning," *Annual Review of Sociology* 14:319-338: [OPENED]
https://sjbae.pbworks.com/f/levitt_march_1988.pdf
- "Organizations are seen as learning by encoding inferences from history into routines that guide behavior."
- "Not everything is recorded. The transformation of experience into routines and the recording of those routines involve costs. The costs are sensitive to information technology, and a common observation is that modern computer-based technology encourages the automation of routines by substantially reducing the costs of recording them. Even so, **a good deal of experience is unrecorded simply because the costs are too great.**"
- "Organizations also often make distinction between outcomes that will be considered relevant for future actions and outcomes that will not. The distinction may be implicit, as for example when **comparisons between projected and realized returns from capital investment projects are ignored** (Hagg 1979). It may be explicit, as for example when exceptions to the rules are declared not to be precedents for the future."
- Superstitious learning "occurs when the subjective experience of learning is compelling, but the connections between actions and outcomes are misspecified."
- **Maps to:** A5 (the expected-versus-actual comparison is routinely *not done* even when both numbers exist) and the capture-cost argument (a 1988 prediction that IT lowers recording cost). Superstitious learning is the risk if why-telemetry is captured but causal links are misattributed (A6, F2).
- **Tension worth flagging:** Levitt & March note that organizations *deliberately* declare some exceptions "not to be precedents," for flexibility. The context-graph vision ("decision traces become searchable precedent") erases that option unless it is designed back in. That is a governance point for the Labs material.

### 5.4 Edmondson (2011), "Strategies for Learning from Failure," *HBR* Apr 2011: [OPENED]
- "When I ask executives to consider this spectrum and then to estimate how many of the failures in their organizations are truly blameworthy, their answers are usually in single digits—perhaps 2% to 5%. But when I ask how many are treated as blameworthy, they say (after a pause or a laugh) 70% to 90%. The unfortunate consequence is that many failures go unreported and their lessons are lost."
- She says learning from failure requires "detection, analysis, and experimentation."
- **Maps to:** Grudin's emotional barrier restated with numbers. Why-telemetry will not be honest in a blame culture (A6). The AAR's "not a critique" norm is the organizational precondition.

### 5.5 Chesterton's fence: G. K. Chesterton, *The Thing* (1929), "The Drift from Domesticity": [OPENED]
https://catholiclibrary.org/library/view?docId=/Contemporary-EN/XCT.165.html&chunk.id=00000011
- "I don't see the use of this; let us clear it away." To which the more intelligent type of reformer will do well to answer: "If you don't see the use of it, I certainly won't let you clear it away. Go away and think. Then, when you can come back and tell me that you do see the use of it, I may allow you to destroy it."
- **Maps to:** the column's MCP/library example (the later developer who "locally improves" and globally damages). Nygard's "blindly change it" is the engineering version. Why-telemetry is a sign on the fence. It is also a *cost reducer* for Chesterton's test: without a record, "go away and think" means archaeology.

---

## 6. Data provenance

### 6.1 Buneman, Khanna & Tan (2001), "Why and Where: A Characterization of Data Provenance," ICDT 2001, LNCS 1973:316-330: [OPENED abstract, Edinburgh Research Explorer]
- Why-provenance "refers to the source data that had some influence on the existence of the data"; where-provenance "refers to the location(s) in the source databases from which the data was extracted."
- **Maps to:** a terminology caution plus a nice echo. Database "why-provenance" means *which inputs justify this output*, which is causal support, not intent. It is closer to F2 (causal traceability) and D4 (links to evidence) than to "why did a person decide." The column can borrow the dignity of the term but should not conflate the two.

### 6.2 W3C PROV (Recommendation 30 Apr 2013): [OPENED]
https://www.w3.org/TR/prov-overview/
- "Provenance is information about entities, activities, and people involved in producing a piece of data or thing, which can be used to form assessments about its quality, reliability or trustworthiness."
- **Maps to:** D1 and D4. A standards-grade, linkable substrate already exists for the what, who, and from-what. PROV has no native first-class construct for intent, alternatives, or expected outcome, which is the column's gap. (I have not checked whether PROV plan/`prov:Plan` covers part of this; it probably partially covers "intended" activity. Verify before claiming.)

---

## 7. What is actually new with AI (strongest answer, with sources)

The old literature explains its own failure in economic terms, and several of those terms have moved:

1. **Capture cost: "too great" then, "a single morning" now.**
   - Then: Levitt & March 1988: "a good deal of experience is unrecorded simply because the costs are too great." Buckingham Shum et al. 2005: automatic extraction from meeting records is "very challenging." Lee 1997: automatic generation needs problems "at the core of machine-learning research" solved.
   - Now: GADR (2026) turns noisy meeting transcripts into ADRs that capture "most expert-identified decisions." Equal Experts (2025): "dozens of ADRs in a single morning." Zhou et al. (2025): LLM-generated rationale surfaces useful arguments the experts had not listed.
2. **The beneficiary mismatch shrinks.** Grudin's central failure mode is that the recorder pays and someone else, later, benefits. With agents, **the next consumer of the why is often the same workflow's next AI run**, which forgets between sessions and needs the rationale immediately (Swan 2025; Lore 2026, "AI becomes both producer and consumer"). That creates Buckingham Shum's "value now." *This specific argument, that agents collapse Grudin's disparity, is one I did not find anyone making explicitly against Grudin. It is available as the column's own synthesis (mark it `MINE`).*
3. **Capture moves from reconstruction to the execution path.** Lee 1997 separates reconstruction (costly and biased) from capture during the work. Foundation Capital argues agents "capture that context at decision time—not after the fact... as a first-class record." When an agent does the work, capturing the why is a by-product rather than a side project. That removes Grudin's "effort that will slow down the project." (Vendor and VC source; treat it as a view, not evidence.)
4. **The why can be scored, not just stored.** Before, rationale text was a "messier construct" that forecasting research "bypassed" (Karvetski et al.). In 2026, LLM-scored explanation markers over 55,000 forecasts predicted accuracy (Karvetski, Tetlock, Karger et al.). Once why becomes telemetry, judgment becomes data, and that is now an empirical result rather than a slogan. **This is the single best citation for A4 and A5.**

Honest limits (what AI does not fix): politics (Grudin: real reasons "not politic to state"); fear and blame (Grudin's MCC anecdote; Edmondson's 70-90%); reconstruction bias moving to machines (Lee 1997; GADR's "transcript-unfaithful content"; Equal Experts' "mismatched justifications"); unfaithful model reasoning (Anthropic, 3 Apr 2025, [OPENED]: "Claude 3.7 Sonnet mentioned the hint 25% of the time, and DeepSeek R1 mentioned it 39% of the time"); and the risk that people are fooled by length (human raters over-weight "rationale length," the same failure as workslop).

---

## 8. Strongest "this is not new" objection (state it in the column, then answer it)

> "Decision journals, ADRs, PEPs, AARs, premortems and design rationale have existed for decades. D2's list is the Farnam Street template. The Army has done 'what was supposed to happen versus what happened' since the 1970s. And the 30-year design-rationale literature shows that rationale capture fails for incentive, political and emotional reasons, not for lack of a format. AI does not change incentives, so this will fail again, or it will generate plausible post-hoc rationale that is worse than none."

Best evidence for the objection: Grudin 1996 (the whole chapter); Buchgeher 2023 (about 50% of ADR repositories have only 1-5 ADRs); Levitt & March ("comparisons between projected and realized returns... are ignored"); Buckingham Shum 2005 ("weak evidence regarding usability and utility"); Anthropic 2025 (CoT unfaithfulness).

Best answer: see §7. Concede novelty of the *idea* (this is consistent with the column's own "do not overclaim novelty" decision), and claim novelty of the *economics*: cheaper capture, a machine consumer, capture as a by-product in the execution path, and automated scoring. Add one thing the prior art mostly lacks. **Almost none of it closes the loop at organizational scale.** ADR, PEP, and RFC templates have no "expected outcome" and no "what actually happened" fields. MADR's "Confirmation" is closest. Decision journals close the loop only for individuals. The AAR and GJP close it, and both are among the best-evidenced learning practices in the set. The column's A5 (expected versus actual, as data) is the part the software world never adopted.

---

## 9. Suggested KBOM additions (for Kurt's decision; I did not edit the KBOM)

| Proposed ID | Claim | Source | Status |
|---|---|---|---|
| H1 | Design-rationale capture historically failed partly because the recorder pays and someone else benefits later | Grudin 1996; Lee 1997; Buckingham Shum et al. 2005 | Opened |
| H2 | "a good deal of experience is unrecorded simply because the costs are too great"; comparisons of projected with realized returns are often ignored | Levitt & March 1988 | Opened |
| H3 | Capturing rationale at NCR surfaced omissions that would have cost 3-6x the capture cost | Conklin & Burgess-Yakemovic 1991 via Lee 1997 | Secondary |
| H4 | The AAR compares recorded intent ("what was supposed to happen") with what happened and why | TC 25-20 (1993) | Opened |
| H5 | LLM-scored rationale quality predicts forecast accuracy across 55k+ forecast explanations | Karvetski, Tetlock, Karger et al. 2026 | Opened (abstract) |
| H6 | LLMs can draft ADRs and rationale from noisy sources, but introduce unfaithful content; human review is required | GADR 2026; Zhou et al. 2025; Equal Experts 2025 | Opened (abstracts/blog) |
| H7 | About 50% of GitHub repositories with ADRs have only 1-5, suggesting trial without adoption | Buchgeher et al. 2023 | Opened (abstract) |
| H8 | Negative knowledge is institutionalized in PEP "Rejected Ideas," Rust "Rationale and alternatives," KEP "Alternatives," Oxide "abandoned," and Nygard "superseded" | the respective templates | Opened |
| H9 | Agents collapse Grudin's cost/benefit disparity because the agent is an immediate consumer of the why | synthesis | `MINE` |

## 10. Sources NOT opened (verify before citing)
- Kunz & Rittel 1970 IBIS working paper (the mirrors failed).
- MacLean et al. 1991 QOC; Conklin & Burgess-Yakemovic 1991 (paywalled; the NCR numbers come from Lee 1997 and search snippets).
- Lee 1991 DRL / SIBYL 1990.
- Tang et al. 2006 architecture rationale survey.
- arXiv:2506.11005 (rationale extraction in OSS); arXiv:2609.07375 (4,300-ADR text-mining study).
- Walsh & Ungson 1991 (Scribd failed; AOM paywalled).
- Argyris 1977 HBR (paywalled; the 1991 HBR article was opened instead).
- Kahneman "cheap notebook" decision-journal quote (secondary blogs only).
- Mitchell, Russo & Pennington 1989 (cited via Klein).
- Bezos 2015 letter (Type 1/Type 2 passage; 404). Amazon PR/FAQ.
- Duke's books (the podcast transcript was opened instead).
- Buneman et al. 2001 full paper (the abstract was opened).
- Foundation Capital byline and original date (the page showed an unsigned Sep 17, 2026 timestamp; the piece was cited by others by Jan 2026).

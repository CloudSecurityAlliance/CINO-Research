# Sweep 1: KBOM B (GPT history) and C (current AI failure mode), verified

Column: "Why Is Telemetry" (2026-09-24). Sweep run 2026-09-24.
Method: primary PDFs downloaded and text-extracted where possible (scratchpad copies); publisher landing pages for abstracts. Anything not opened is marked **NOT OPENED**.

---

## Section B: General-purpose technology history

### B1: GPTs need complementary organizational redesign before full gains show up
**Verdict: CONFIRMED.** This is the shared thesis of every source below (B2 to B6). It also appears in the 2026 ILO brief (see C6).
- Brynjolfsson, Rock, Syverson, NBER w24001 (Nov 2017), abstract, opened at nber.org/papers/w24001: "like other general purpose technologies, their full effects won't be realized until waves of complementary innovations are developed and implemented."

### B2: Electrification's gains came after unit drive and factory redesign
**Verdict: CONFIRMED, with a wording CORRECTION.**
Source opened: Paul A. David, "The Dynamo and the Computer: An Historical Perspective on the Modern Productivity Paradox," *American Economic Review* 80(2), AEA Papers & Proceedings, May 1990, pp. 355-361. Full text read from the JSTOR scan mirrored at https://gwern.net/doc/economics/automation/1990-david.pdf. The ResearchGate URL in 09-source-research-notes returns HTML, not the PDF.

Key quotes:
- Timing (p. 356-57): "factory electrification did not ... have an impact on productivity growth in manufacturing before the early 1920s. At that time only slightly more than half of factory mechanical drive capacity had been electrified. ... This was four decades after the first central power station opened for business."
- Intermediate stage (p. 357): "the 'group drive' system of power transmission remained in vogue" from the mid-1890s to about 1920, "in which electric motors turned separate shafting sections, so that each motor would drive related groups of machines." Retrofits "typically entailed adding primary electric motors to the original stock of equipment."
- Overlay point (p. 357), useful for the column: "This sort of overlaying of one technical system upon a preexisting stratum is not unusual". He applies it to computers too: "old paper-based procedures are being retained alongside the new."
- Unit drive (p. 357-58): "individual electric motors were used to run machines of all sizes". "Factory structures could be radically redesigned". The move to "single-story, linear factory layouts" permitted "flexible reconfiguration of machine placement."
- Size of the effect (p. 359): "approximately half of the 5 percentage point acceleration recorded in the aggregate TFP growth rate of the U.S. manufacturing sector during 1919-29 (compared with 1909-19) is accounted for statistically simply by the growth in manufacturing secondary electric motor capacity."

**Corrections to the KBOM wording:**
1. The counterfactual David describes is **group drive** (electric motors bolted onto the old shaft-and-belt system), not "central electric drive." Suggested wording: *"...came after factories moved from 'group drive' (electric motors bolted onto the old shaft-and-belt layout) to 'unit drive' (a motor per machine) and redesigned the building around it."*
2. **Causation nuance.** David puts the lag mostly on economics and learning, not a failure of imagination: "the unprofitability of replacing still serviceable manufacturing plants," the wait for "physical depreciation of durable factory structures," and a "decentralized ... learning process" among factory architects and engineers. Popular retellings of the form "managers didn't think to redesign" overstate this. The column should not claim that.

**Bonus, highly relevant to this column (p. 360).** David's own caveats read almost as a prior-art statement of the "why is telemetry" thesis:
- "Computers are not dynamos." Information "can give rise to 'overload'", and "screening is costly." This anticipates workslop.
- "the information structures of firms (i.e., the type of data they collect and generate, the way they distribute and process it for interpretation) may be seen as direct counterparts of the physical layouts" of factories.
- "information structures per se do not automatically undergo significant physical depreciation ... one cannot depend on the mere passage of time to create occasions to radically redesign a firm's information structures." So there is "a strong inertial component".

This lets the column say that David himself said the "factory floor" of the information age is the firm's information structure. That is a strong, citable bridge to "why becomes telemetry."

### B3: IT value depends on complementary organizational investments
**Verdict: CONFIRMED.**
Source opened (abstract, AEA landing page): Erik Brynjolfsson and Lorin M. Hitt, "Beyond Computation: Information Technology, Organizational Transformation and Business Performance," *Journal of Economic Perspectives* 14(4), Fall 2000, pp. 23-48. https://www.aeaweb.org/articles?id=10.1257/jep.14.4.23
- "organizational 'investments' have a large influence on the value of IT investments; and ... the benefits of IT investment are often intangible and disproportionately difficult to measure."
- The full PDF did not download (the AEA pubs site returned HTML), so body text is **NOT OPENED**. Rely on the abstract only.

### B4: Firm-level computerization effects are larger over 5-7 years
**Verdict: CONFIRMED.**
Source opened (full PDF): Brynjolfsson and Hitt, "Computing Productivity: Firm-Level Evidence," *Review of Economics and Statistics* 85(4), Nov 2003, pp. 793-808. Copy at https://gwern.net/doc/economics/automation/2003-brynjolfsson.pdf
- Abstract: data from "527 large U.S. firms over 1987-1994". Short-run (1-year differences) contributions are "consistent with normal returns," but "the productivity and output contributions associated with computerization are up to 5 times greater over long periods (using 5- to 7-year differences)." The result suggests "time-consuming investments in complementary inputs, such as organizational capital."
- Intro: complementary organizational capital "may be up to 10 times as large as the direct investments in computers" (citing Brynjolfsson & Yang 1999; Brynjolfsson, Hitt & Yang 2002).
- Suggested precise wording: "up to five times greater over five-to-seven-year horizons."

### B5: IT, workplace reorganization, and new products/services are complements
**Verdict: CONFIRMED.**
Source opened (full PDF): Bresnahan, Brynjolfsson, and Hitt, "Information Technology, Workplace Organization, and the Demand for Skilled Labor: Firm-Level Evidence," *Quarterly Journal of Economics* 117(1), Feb 2002, pp. 339-376.
- Abstract: "we find evidence of complementarities among all three of these innovations in factor demand and productivity regressions." Also: "The effects of IT on labor demand are greater when IT is combined with the particular organizational investments we identify, highlighting the importance of IT-enabled organizational change."

### B6: The productivity J-curve treats GPT adoption as investment in unmeasured intangibles
**Verdict: CONFIRMED.** The paper names AI explicitly as a GPT.
Sources opened:
- NBER WP 25148 (Oct 2018), full PDF at https://ide.mit.edu/sites/default/files/publications/jcurve.pdf. The ide.mit.edu file is the NBER working paper, **not** the AEJ version.
- Published version: Brynjolfsson, Rock, Syverson, "The Productivity J-Curve: How Intangibles Complement General Purpose Technologies," *American Economic Journal: Macroeconomics* 13(1), Jan 2021, pp. 333-72, DOI 10.1257/mac.20180386. Abstract opened on the AEA page.

Quotes:
- AEJ abstract: "General purpose technologies (GPTs) like AI enable and require significant complementary investments. These investments are often intangible and poorly measured in national accounts." The model shows "underestimation of productivity growth in a new GPTs early years and, later, when the benefits of intangible investments are harvested, productivity growth overestimation." Finding: adjusting for hardware/software intangibles "yields a TFP level that is 15.9 percent higher than official measures by the end of 2017."
- WP abstract lists the complements: "business process redesign, co-invention of new products and business models, and investments in human capital."
- WP p. 3: "In the later GPT case of electrification, it took a generation as the nature of factory layouts was re-invented (David 1990)."
- NBER w24001 acknowledgements: "Larry Summers suggested the analogy to the J-Curve." This is a trivia-grade detail.

**Note:** the J-curve is about *measurement error* in TFP, not only a real dip. Correct shorthand: "measured productivity understates true productivity early, then overstates it later." The KBOM wording ("investment in unmeasured intangible complements before visible gains") is fine.

---

## Section C: Current AI failure mode

### C1 / C2: substitution (existing workflow plus AI) gives local gains and global drag
**Verdict: MINE, now with strong external support (PARTIAL support; see Counter-evidence).** The new sources below give C1/C2 an external spine. Two quotable lines:
- DORA 2024 (https://dora.dev/research/2024/dora-report/, opened): "AI adoption significantly increases individual productivity, flow, and job satisfaction. However, it also negatively impacts software delivery stability and throughput." This is nearly a verbatim external statement of C2.
- MIT NANDA 2025 (opened): "these tools primarily enhance individual productivity, not P&L performance."

### C3: Definition of workslop
**Verdict: CONFIRMED.** The HBR wording is sharper than the KBOM's.
Source opened (article body was retrievable from the page HTML): Kate Niederhoffer, Gabriella Rosen Kellerman, Angela Lee, Alex Liebscher, Kristina Rapuano, Jeffrey T. Hancock, "AI-Generated 'Workslop' Is Destroying Productivity," *Harvard Business Review*, Sept 22, 2025 (updated Sept 25, 2025). https://hbr.org/2025/09/ai-generated-workslop-is-destroying-productivity
- "We define workslop as AI generated work content that masquerades as good work, but lacks the substance to meaningfully advance a given task."
- "it shifts the burden of the work downstream, requiring the receiver to interpret, correct, or redo the work. In other words, it transfers the effort from creator to receiver."
- The BetterUp blog (https://www.betterup.com/blog/hidden-costs-workslop, opened) uses a looser definition: "AI-generated content that looks polished and complete — but is actually unhelpful, low-quality, or off the mark." **Cite the HBR definition.**

### C4: "41 percent encountered workslop; nearly two hours of rework per instance"
**Verdict: CORRECTED.** The 41% figure is internally inconsistent across the sources and needs fixing.

| Figure | HBR article body (Sept 2025) | HBR summary blurb | BetterUp PDF one-pager | BetterUp blog |
|---|---|---|---|---|
| Received workslop in last month | **40%** ("Of 1,150 U.S.-based full-time employees across industries, 40% report having received workslop in the last month") | 41% | 40% | 40% |
| Prevalence used in cost math | 41% ("given the estimated prevalence of workslop (41%)") | n/a | "accounting for the 40% prevalence rate" | n/a |
| Time per instance | **1 hr 56 min** ("an average of one hour and 56 minutes dealing with each instance") | "nearly two hours" | 1hr56m | 1 hr 51 min |
| Cost | "$186 per month" per employee. Over "$9 million per year" for a 10,000-person org | n/a | $186/month; $9M | $186/month; $9M+ |
| Share of received content that is workslop | 15.4% | n/a | 15.4% | n/a |
| Senders admitting it | n/a | n/a | 53% | 53% |
| Sample | 1,150 US full-time desk workers, "ongoing survey" | n/a | 1,150, "Online survey ... August-September 2025" | **1,004**, "September 2025" |

In the BetterUp PDF, **41%** is a *different* statistic: "41% of employees report that leadership encouraged AI use without explaining how or why."

**Recommended wording:** "In a September 2025 survey of 1,150 U.S. desk workers, BetterUp Labs and the Stanford Social Media Lab found that 40 percent had received workslop in the past month, and that each instance cost the recipient nearly two hours (1 hour 56 minutes) to deal with."

**Methodology caveats to flag:**
- The survey is self-reported, online, and "ongoing" (the HBR article links to a public survey anyone can take, so N may drift).
- BetterUp is a coaching vendor, and the PDF closes with a product pitch.
- The cost figure derives from respondents' own time estimates and self-reported salary.
- It is not peer-reviewed.
- Use it as a vivid indicator, not as measurement.

### C5: AI slop degrades organizational knowledge and processes (Holweg and Davenport)
**Verdict: PARTIAL.** The article exists and the claim matches its summary, but the body is paywalled and **NOT OPENED**.
Source opened (landing page and summary only): Matthias Holweg (Oxford Saïd) and Thomas H. Davenport (Babson / MIT IDE), "Don't Let AI Slop Muck Up Your Company's Processes," *HBR*, June 16, 2026. https://hbr.org/2026/06/dont-let-ai-slop-muck-up-your-companys-processes

Summary quotes:
- "decay in the accuracy and quality of organizational knowledge. This decay is the organization-level version of the 'workslop' problem."
- "When workslop occurs in sequence across a business's processes, those processes themselves ... start to deteriorate, errors compound and pile up, trust erodes, and the productivity gains of AI disappear."
- Three challenges: "verification, validation, and entropy."
- Prescriptions: "1) Keep track of the provenance of unstructured data, 2) restrict the use of gen AI, 3) define what value is being added, and 4) understand the implications for the entire process."

**Very useful for the column.** The #1 prescription, *provenance*, is essentially the column's D1/F1 argument, from Davenport. Cite it via the summary only, or get the full text before quoting anything beyond it.

### C6: GenAI productivity evidence is mixed; time savings haven't become output, earnings, or employment (ILO)
**Verdict: CONFIRMED.** Date and wording corrected.

Source opened (full PDF, 8 pp.): ILO Research Brief, "The impact of GenAI on jobs, productivity and work organization: a review of the empirical evidence," **May 2026**. Authors: Rossana Merola, Ekkehard Ernst, Daniel Samaan (ILO), Maria del Rio-Chanona (UCL), Ole Teutloff (Oxford). It synthesizes Del Rio-Chanona et al. (2025). The PDF URL path is /2026-06/, but the brief is dated May 2026.
- Abstract: "productivity gains are real albeit often unverified and uneven ... worker-reported time savings of a few per cent of working hours have not yet translated into higher measured output, earnings or employment."
- Mechanism: "Workers appear to capture the time savings primarily as on-the-job leisure and as reallocation toward tasks the technology does not affect, rather than as expanded output". "This gives rise to an 'aggregation paradox' (Chan and Shedania, 2026)."
- Also: "AI affects not only individual tasks but also the organisation of work as bundles of interdependent activities."

Companion brief opened (full PDF, 15 pp.): ILO Research Brief, "The Aggregation Paradox of AI: Why do micro-economic productivity gains from AI disappear at scale," **April 2026**, by Cheuk Yu Cheryl Chan and Khatia Shedania. **Title confirmed exactly.**
- Key points: AI "delivers large productivity gains at the task level (typically 10-70 per cent)". "At the firm level, evidence is more mixed ... many firms report little measurable impact beyond pilots". "At sectoral and macroeconomic levels, no clear AI-driven productivity growth has yet appeared in official statistics, consistent with ... the 'productivity J-curve'".
- On electrification and ICT: "technological revolutions only raised aggregate productivity after substantial organizational change and institutional adaptation."
- Near-verbatim support for C1 (citing Agrawal, Gans & Goldfarb 2022): AI requires "'system-level redesign' of production processes, not merely substitution of AI for human effort at isolated task nodes."

---

## New sources (2024-2026) for C1/C2

1. **METR RCT, early 2025** (opened: https://metr.org/blog/2025-07-10-early-2025-ai-experienced-os-dev-study/, July 10, 2025). "16 experienced developers", "246" issues. "When developers are allowed to use AI tools, they take 19% longer." They "expected AI to speed them up by 24%" and afterward "still believed AI had sped them up by 20%."
   - This is the best single illustration of *perceived versus measured* productivity, which is a telemetry argument in itself: self-report is not telemetry.
   - Authors' caveat: it does "not provide evidence that AI systems do not currently speed up many or most software developers."
   - **2026 follow-up** (opened: https://metr.org/blog/2026-02-24-uplift-update/, Feb 24, 2026):
     - Original-developer subset: "estimated speedup of -18% (CI -38% to +9%)". METR's sign convention here is change in time taken, so this now points toward *faster*.
     - New recruits: "-4% (CI -15% to +9%)".
     - METR calls the data "an unreliable signal" because developers now refuse to work without AI, a selection effect.
   - **The column must not cite "19% slower" as the current state.** Cite it as early-2025, the perception gap as the durable lesson, and note that METR itself says later tools are likely faster.

2. **Humlum & Vestergaard, Danish administrative data** (full PDF opened: NBER w33777). **Retitled.** It is now "Still Waters, Rapid Currents: Early Labor Market Transformation under Generative AI" (May 2025, revised March 2026). It was formerly "Large Language Models, Small Labor Market Effects."
   - "precise null effects on earnings and recorded hours at both the worker and workplace levels, ruling out effects larger than 2% two years after the launch of ChatGPT."
   - "What moves is the structure of work: employers absorb AI through task reorganization".
   - "85%" of users report "reallocating time savings" to other tasks.

3. **Yotzov, Barrero, Bloom et al., "Firm Data on AI"** (NBER w34836, Feb 2026, rev. Mar 2026; abstract opened). "nearly 6,000 senior business executives" in the US, UK, Germany, and Australia.
   - "69% of firms actively use AI". Yet "nine-in-ten reporting no impact on employment or productivity" over 3 years.
   - Executives predict +1.4% productivity over the next 3 years.
   - This is the strongest 2026 firm-level data point.

4. **MIT NANDA, "The GenAI Divide: State of AI in Business 2025"** (full PDF opened: https://mlq.ai/media/quarterly_decks/v0.1_State_of_AI_in_Business_2025_Report.pdf; research period Jan-Jun 2025).
   - "95% of organizations are getting zero return"; the tools "primarily enhance individual productivity, not P&L performance".
   - Diagnosis: "Most GenAI systems do not retain feedback, adapt to context, or improve over time." This is a "learning gap". It is adjacent to the column's durable-state thesis.
   - **Critiques:** The sample is 52 interviews, 153 conference-survey responses, and 300+ *public* initiatives. The report says its figures are "directionally accurate" and lists selection-bias limits. "Success" was defined as deployment beyond pilot with measurable KPIs at 6 months. Commentators (e.g., Marketing AI Institute; agentmodeai.com) note that "no measurable P&L" largely reflects missing baselines.
   - **Recommendation: do not cite the 95% as a fact.** If used, say "a widely cited, methodologically thin MIT NANDA report." The HBR workslop article itself leans on it.

5. **DORA** (Google Cloud).
   - 2024 report (landing page opened): the quote under C1/C2 above. The specific figures come from secondary summaries only, e.g. RedMonk: "1.5% decrease in delivery throughput and a 7.2% reduction in delivery stability" per 25% increase in adoption. The full PDF is **NOT OPENED**.
   - 2025 "State of AI-assisted Software Development" (Google Cloud blog opened, Sept 23, 2025; "nearly 5,000" respondents). "we observe a positive relationship between AI adoption on both software delivery throughput and product performance. However, AI adoption does continue to have a negative relationship with software delivery stability."
   - 2025 amplifier framing: "AI doesn't fix a team; it amplifies what's already there." The DORA site calls AI's role "an amplifier, magnifying an organization's existing strengths and weaknesses".
   - Good security-audience fit.

6. **Acemoglu, "The Simple Macroeconomics of AI"** (NBER w32487, May 2024; *Economic Policy* 2025; abstract via WebFetch). "no more than a 0.66% increase in total factor productivity (TFP) over 10 years". Adjusted for hard-to-learn tasks, "less than 0.53%."

7. **Mary C. Daly (SF Fed President), "The AI Moment? Possibilities, Productivity, and Policy,"** FRBSF Economic Letter, Feb 23, 2026 (opened). "most macro-studies of productivity growth find limited evidence of a significant AI effect". Also: "firms had to shed the constraints of the previous steam-powered world and reimagine business in an era of electricity." A central-bank voice using the dynamo frame in 2026.

8. **Dell'Acqua et al., "The Cybernetic Teammate"** (NBER w33641, April 2025; abstract opened; now in *Organization Science*). 776 P&G professionals: "individuals with AI matched the performance of teams without AI." This is evidence that the gains come from *reorganizing* who does what, which supports B1 over pure substitution.

---

## Counter-evidence (complicates "substitution is not enough")

1. **Brynjolfsson, Li, Raymond, "Generative AI at Work"** (NBER w31161; *QJE* 140(2), 2025; NBER abstract opened). "5,179 customer support agents"; "issues resolved per hour, by 14% on average, including a 34% improvement for novice and low-skilled workers."
   - This is a real, measured, firm-level gain from what looks like drop-in substitution.
   - **How to handle it:** the mechanism is that "the AI model disseminates the best practices of more able workers." The tool was built from the firm's own logged conversations, which is *durable organizational state* turned into leverage. The column can reframe it as a point in its favor: the biggest documented win is exactly a case where past work had been captured as data.
   - Also note the task is narrow, well-instrumented, and already measured (resolutions per hour), which is the opposite of unmeasured knowledge work.

2. **Dell'Acqua et al., "Navigating the Jagged Technological Frontier"** (HBS WP 24-013, Sept 2023; published in *Organization Science*, online 11 Mar 2026, DOI 10.1287/orsc.2025.21838; both PDFs opened). 758 BCG consultants.
   - Inside the frontier: "12.2% more tasks," "25.1% more quickly," "more than 40% higher quality."
   - Outside the frontier: "19 percentage points less likely to produce correct solutions."
   - **Handle it:** large *individual/task* gains are real. The outside-frontier failure is the workslop mechanism, and knowing which side of the frontier you are on requires telemetry on outcomes.

3. **Noy & Zhang** (MIT WP, March 2023, opened; published in *Science* 381, July 2023; the Science page returned 403, **NOT OPENED**). 444 professionals. "time taken decreases by 0.8 SDs and output quality rises by 0.4 SDs." The oft-quoted "40% faster / 18% better" is from the Science abstract, which was **not opened here**.
   - Notably, the authors say "ChatGPT mostly substitutes for worker effort rather than complementing worker skills". So substitution *can* raise task output. The column's claim should be scoped to *organizational* outcomes, not task outcomes.

4. **Macro upturn claim.** Brynjolfsson, FT op-ed "The AI productivity take-off is finally visible" (Feb 2026; FT **NOT OPENED**; reported by Fortune, Feb 15, 2026, opened).
   - "U.S. productivity jumped roughly 2.7% in 2025—nearly double the 1.4% annual average." We are "transitioning out of this investment phase into a harvest phase."
   - He himself cautions that more periods are needed.
   - Rebuttal in the same article from Torsten Slok (Apollo): "AI is everywhere except in the incoming macroeconomic data" ... "Maybe there is a J-curve effect for AI... Maybe not."
   - **Handle it:** acknowledge that the J-curve's own author says the harvest may be starting. That does not undercut the column. The harvest is predicted to go to firms that made the complementary investments, which is the column's point.

5. **Scoping lesson for the column.** The evidence supports "task-level gains are real and often large (ILO: 10-70%); firm- and macro-level gains are thin so far." It does **not** support "substitution produces no gains." Recommended phrasing for C2: *substitution reliably speeds up tasks; whether that speed becomes organizational output depends on what the organization does with the time and how it catches the errors, and that is where the gap currently sits.*

---

## Critiques of the David / electrification analogy

1. **David's own caveats (1990, p. 360).** "Computers are not dynamos." Information overload; information structures don't depreciate, so there is stronger inertia. He also warns "against the dangers of embracing the historical analogy too literally." The best move is to cite David against over-literal use.
2. **Lag-mechanism misreading.** Per David, the lag was mostly sunk capital plus slow, decentralized learning, not managerial blindness. See B2.
3. **Acemoglu (2024/2025).** The ceiling may be much lower (at most 0.66% TFP over 10 years). The dynamo multiple may not apply.
4. **Robert Gordon.** He holds that modern GPTs are less "general-purpose" than electricity and that AI will be less transformative. He has a Long Bets wager with Brynjolfsson. The Marketplace source (Mar 2025) returned 403 and is **NOT OPENED**; this is from search snippets only.
5. **Baily, Byrne, Kane, Soto, "Generative AI at the Crossroads: Light Bulb, Dynamo, or Microscope?"** (arXiv 2505.14588, May 2025, rev. Sept 2025; abstract opened). They ask whether genAI is a one-off "light bulb", a GPT "dynamo," or an invention-of-invention "microscope." Conclusion: "GenAI has the characteristics of both a GPT and an IMI," but with a "lengthy integration process."
6. **Speed-of-diffusion objection.** Adoption is far faster than electrification (Humlum & Vestergaard cite Bick, Blandin & Deming 2025: "the fastest worker take-up of any new technology"). Skeptics use this to argue that the 40-year lag is not a template. Crafts (*Oxford Rev. Econ. Policy* 37(3), 2021; abstract opened) is not a critic, but notes the lag was "substantial" for steam and electricity and less so for ICT.
7. **Counter-counter.** The ILO (2026) explicitly endorses the electrification/ICT pattern as the expected path for AI.

**Column handling:** keep the dynamo as a two-sentence frame, not an argument. Quote David's own information-structures line, which turns the analogy from "be patient" into "redesign the information layout." That is the column's thesis.

---

## People and organizations actively making the argument (2025-2026)

- **Erik Brynjolfsson** (Stanford Digital Economy Lab): J-curve; FT, Feb 2026, "take-off is finally visible."
- **Chad Syverson, Daniel Rock**: J-curve co-authors.
- **ILO Research Department** (Ekkehard Ernst, Rossana Merola, Cheuk Yu Cheryl Chan, Khatia Shedania): "aggregation paradox."
- **Nick Bloom, Jose Maria Barrero, Steven Davis** et al. (Atlanta Fed / BoE / Bundesbank survey consortium): "Firm Data on AI."
- **Anders Humlum** (Chicago Booth) and **Emilie Vestergaard** (Copenhagen).
- **Daron Acemoglu** (MIT): skeptic ceiling.
- **Mary C. Daly** (SF Fed): dynamo frame, limited macro evidence.
- **Torsten Slok** (Apollo): "AI is everywhere except in the incoming macroeconomic data."
- **Robert Gordon** (Northwestern): skeptic.
- **Thomas Davenport and Matthias Holweg**: org-level slop, provenance.
- **Jeff Hancock** (Stanford Social Media Lab) and **Kate Niederhoffer** (BetterUp Labs): workslop.
- **METR**: perceived vs measured developer productivity.
- **DORA / Google Cloud** (Nathen Harvey, lead author 2025): "AI as amplifier."
- **Ethan Mollick, Fabrizio Dell'Acqua, Karim Lakhani** (Wharton/HBS): jagged frontier, cybernetic teammate.
- **MIT Project NANDA** (Aditya Challapally et al.): 95% claim (contested).

## Not opened / verification gaps

- HBR Holweg & Davenport full body (paywall). Summary only.
- JEP "Beyond Computation" full text. Abstract only.
- *Science* version of Noy & Zhang (403). The WP was opened.
- DORA 2024 full PDF. The 1.5% / 7.2% figures are secondary only.
- FT Brynjolfsson op-ed. Via Fortune only.
- Marketplace / Gordon (403). Search snippets only.
- Acemoglu: abstract via WebFetch summary (quotes are as returned; re-confirm the exact wording before print).

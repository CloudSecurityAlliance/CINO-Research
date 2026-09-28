# Research Notes

This is the canonical drafting specification for `draft-01.md`.

## Working title

**Why Is Telemetry**

## One-sentence thesis

If AI is going to do consequential knowledge work, organizations need to observe not just what happened but why, because once intent, evidence, alternatives, and judgments are captured and connected to outcomes, the organization can improve the work and the system that produced it.

## Drafting thesis

Traditional observability records what a system did. AI-native organizations need to record why work was done, what alternatives were considered, what evidence and assumptions shaped the decision, what outcome was expected, and what actually happened. Once why becomes telemetry, judgment becomes data. Once judgment becomes data, organizations can learn from judgment itself and improve not only outputs, but workflows, evaluators, resource allocation, and governance.

## The argument in sequence

> **Superseded 2026-09-28 for structure:** the canonical beat map, citation plan and word budget are in `10-story-beat-synthesis.md`. The claims and evidence below still stand; where this section's ordering or citation list differs from `10`, `10` wins.


1. Security and operations people already understand telemetry. It tells us what happened.
2. Agentic AI makes a new class of state important: intent, assumptions, evidence, alternatives, uncertainty, and expected outcomes.
3. General-purpose technologies historically underperform when organizations merely substitute them into old workflows.
4. AI is currently being used largely as substitution: existing workflow plus AI.
5. Substitution can produce workslop, shifting cognitive labor downstream.
6. The missing artifact is often the rationale, not the final document or code.
7. Important cognition should leave durable, addressable organizational state.
8. If why is captured as telemetry, judgment becomes data.
9. Judgment as data enables comparison of expectations against outcomes.
10. The payoff is recursive organizational improvement, governed and testable, not mystical RSI.

## Key claims

### Claim 1: General-purpose technologies need complementary redesign

Electricity and computers did not produce their largest gains by being dropped into old workflows. Electrification produced larger gains after unit-drive motors and factory redesign. IT produced larger gains with complementary organizational investments.

Use as frame, not as a history lesson.

Candidate sentence:

> Factories did not get the full value of electricity by replacing the steam engine with one large electric motor and leaving everything else unchanged.

### Claim 2: Most current AI adoption is still substitution

Most use looks like:

> existing workflow + AI

Examples:

- email, but faster;
- reports, but faster;
- code, but faster;
- analysis, but faster.

Useful but not transformative.

### Claim 3: Substitution creates workslop

The failure mode:

> Person gives thin prompt -> AI generates polished artifact -> person forwards it -> recipient reconstructs missing thinking.

This lets the sender appear more productive while the organization may do more total work.

Protected line:

> AI can make an individual more productive while making the organization less productive.

### Claim 4: The missing output is why

Example:

> Build this in Python as a reusable library, then expose it through an MCP server.

That records what to build, not why the architecture matters.

The missing rationale may include:

- business logic should remain independent of transport;
- the library should be directly testable;
- MCP should be a thin adapter;
- CLI, API, or other interfaces may come later;
- security controls should exist below the MCP layer.

If the rationale disappears, a later developer may locally improve the tool while globally damaging the architecture.

### Claim 5: Important cognition should become durable organizational state

Useful state includes:

- intent;
- objective;
- evidence;
- assumptions;
- alternatives considered;
- rejected alternatives and why;
- expected outcomes;
- actual outcomes;
- evaluator and threshold;
- lessons learned.

GitHub analogy:

> issue -> discussion -> proposed change -> review -> commit -> merge -> history.

### Claim 6: Negative knowledge matters

Organizations should record not only what was selected, but what was rejected, why, and whether rejected ideas keep recurring.

Candidate lines:

- "Repeated rejection is itself telemetry."
- "Sometimes the most valuable telemetry is the path we did not take."
- "The dog that did not bark can be data."

This may be better for Labs than Circle News unless the column needs a distinctive middle beat.

### Claim 7: Once why becomes telemetry, judgment becomes data

Protected line:

> Once why becomes telemetry, judgment becomes data.

This lets the organization ask:

- Did the expected outcome happen?
- Which judgments produced good downstream results?
- Which assumptions failed?
- Which alternatives were repeatedly rejected?
- Which local improvements damaged the global architecture?
- Which process changes should become standard?

### Claim 7b: The idea is old; the economics are new (lineage beat)

Decided 2026-09-24 (CognitiveBOM C15). Capturing why is not new. Design-rationale work goes back to
IBIS (Kunz & Rittel, 1970), then ADRs, PEP "Rejected Ideas", decision journals and the Army
after-action review. It mostly failed because of humans: the person recording paid, someone
else benefited later, and most projects died before anyone read the record (Grudin 1996).
"A good deal of experience is unrecorded simply because the costs are too great" (Levitt &
March 1988). The idea has resurfaced with AI, and now the economics favor it:

- capture is a by-product of the agent doing the work;
- the next consumer of the why is the next AI run, immediately (H9, `MINE`);
- the why can now be scored (Karvetski, Tetlock, Karger et al. 2026).

Be honest about the limit: AI does not fix the politics of stating real reasons, or blame.

Do not cite Foundation Capital. "It has resurfaced with AI" covers the current wave generically.

### Claim 8: Rationale is not truth

Important caveat:

Humans rationalize. Models rationalize. Explanations can be incomplete, post-hoc, wrong, or gamed.

Answer:

Do not "believe the explanation." Capture structured claims, link them to evidence and outcomes, and test them over time.

This caveat is necessary for credibility.

### Claim 9: Doing the work should improve the work

The loop:

> Do work -> capture why -> compare outcome against expectation -> extract lesson -> update process -> next work starts from improved state.

Protected line:

> The answer is not simply better prompting. It is redesigning the work so that doing the work also teaches the organization how to do the work better next time.

## Current evidence anchors

### Historical/productivity anchors

- Paul David, "The Dynamo and the Computer" - electricity/computer productivity paradox and factory redesign.
- Brynjolfsson and Hitt, "Beyond Computation" - IT value depends on organizational transformation.
- Brynjolfsson and Hitt, "Computing Productivity" - larger productivity effects over 5-7 year periods.
- Bresnahan, Brynjolfsson, and Hitt - complementarities among IT, workplace organization, and new products/services.
- Brynjolfsson, Rock, and Syverson - productivity J-curve and intangible complements.

### Workslop and AI productivity anchors

- BetterUp Labs and Stanford Social Media Lab - workslop definition, 41 percent exposure, nearly two hours rework per instance. Verify before citing exact figures.
- Holweg and Davenport in HBR - AI slop can degrade organizational processes and knowledge quality.
- ILO 2026 empirical review - reported time savings have not necessarily translated into measured output, earnings, or employment.

### Self-improving agents and RSI anchors

- 2026 survey of self-improvements in modern agentic systems - prompts, memory, tools, and control logic as mutable scaffold.
- FlowEvo - workflows and executable skills co-evolve, with curation against negative transfer.
- "Path to Recursive Self-Improving Agents" - improvement mechanism itself becomes part of evolving system.

These are probably Labs sources, not Circle News citation anchors unless the column needs one sentence late.

## What to cite in the Circle News column

> **Superseded 2026-09-28 for structure:** the canonical beat map, citation plan and word budget are in `10-story-beat-synthesis.md`. The claims and evidence below still stand; where this section's ordering or citation list differs from `10`, `10` wins.


Likely cite no more than 4-6 sources inline:

1. Paul David or a source on electrification/unit-drive motors.
2. Brynjolfsson/Rock/Syverson on productivity J-curve.
3. BetterUp/Stanford or BetterUp report on workslop.
4. ILO 2026 review or HBR Holweg/Davenport for the macro/organization-level caution.
5. One self-improving-agent survey only if the close explicitly names recursive improvement.

## Column structure

> **Superseded 2026-09-28 for structure:** the canonical beat map, citation plan and word budget are in `10-story-beat-synthesis.md`. The claims and evidence below still stand; where this section's ordering or citation list differs from `10`, `10` wins.


### Opening

Open with telemetry:

> We have spent decades building systems that can tell us what happened.

Then:

> But increasingly, I want to know why.

Land:

> Why is telemetry.

### Historical frame

Electricity/computers: substitution was useful but not the main productivity unlock.

Transition:

> We are at the same stage with AI.

### Present failure mode

AI plus inherited workflows can create workslop: polished output with missing thinking, downstream rework, and local productivity masking global drag.

### Deeper opportunity

Cheap machine cognition makes it practical to branch, compare, replay, and learn from knowledge work in ways that used to be too expensive.

### Requirement

The work must leave behind durable state. Not everything. Not raw chain-of-thought as the interface. Enough structured rationale to preserve intent, evidence, alternatives, assumptions, judgment, and expected outcomes.

### Pivot

Once why becomes telemetry, judgment becomes data.

### Caveat

Logged why is not truth. It is a testable claim.

### Close

The most important question is not only whether AI made this output faster. It is whether doing the work made the organization better at doing the next one.

## Decisions made

| Decision | Rationale |
|---|---|
| The article is about "why" as telemetry, not RSI directly | Stronger and more concrete for the Circle News audience |
| Use historical GPT pattern as support | Makes the argument feel grounded and familiar |
| Use workslop as the failure mode | Gives the reader a current problem they have probably seen |
| Keep Labs separate | The research body is much larger than the column |
| Preserve rationale as structured claims, not full chain-of-thought | Operationally useful and less brittle |

## Decisions against

| Decision against | Rationale |
|---|---|
| Do not make the column a full framework | It would stop feeling like a column |
| Do not overclaim novelty | Decision records, observability, HRO, MAPE-K, VSM, SRE, and quality systems all have relevant prior art |
| Do not say "rationale equals truth" | That is obviously attackable |
| Do not cite the 3-6 iteration observation as research | It is a useful Kurt practice note, not an external finding |
| Do not make this self-referential throughout | The article process is a good meta-example, but it should not crowd out the reader's own work |

## First-draft instruction

> **2026-09-28:** draft from `10-story-beat-synthesis.md` (beats, facts, citations, callbacks), use this file for claim detail, `14-mcp-case-material.md` for the first-person pair, and `12-coverage-check.md` for what not to repeat.


Draft as continuous prose, not a sectioned report. Preserve the protected lines. Keep the historical analogy brief. Make the workslop beat vivid. Let recursive improvement arrive as the payoff, not the headline.

# Column Design

**Working title:** Why Is Telemetry  
**Status:** design nearly locked, pre-draft  
**Target:** Circle News monthly column, dense continuous prose, roughly 1,500-2,000 words unless compressed for newsletter fit  
**Audience:** CSA community: security professionals, business leaders, technical decision-makers  
**Style constraints:** no em dashes, no emojis, recent columns over stale style prompt, citations inline as URLs in parentheses for verifiable claims

## Central question

What changes when AI does consequential knowledge work, but the organization only records the artifact and loses the why?

## Central answer

AI-native organizations need cognitive observability. They need to preserve structured rationale, alternatives, evidence, assumptions, judgments, expectations, and outcomes in durable, addressable form. Once why becomes telemetry, judgment becomes data. Once judgment becomes data, the organization can improve the system that produced the judgment.

> **Superseded 2026-09-28 for hook, story beats, and decisions:** see `10-story-beat-synthesis.md` (beats) and `CognitiveBOM.md` (decisions). **The Protected lines and Voice notes sections below remain canonical.**

## Hook options

### Option A: observability hook

We have spent decades building systems that tell us what happened. The server returned an error. The firewall blocked the connection. The employee approved the expense. The model called a tool.

But increasingly, that is not the question I care about.

I want to know why.

### Option B: general-purpose technology hook

Factories did not get the full value of electricity by replacing the steam engine with one large electric motor and leaving the factory unchanged. The bigger gains came when manufacturers put smaller motors directly on machines and redesigned the factory around what electricity made possible.

We are making the same mistake with AI.

### Option C: workslop hook

AI can make one person faster while making the organization slower. The person writes a thin prompt, the AI produces a polished artifact, and someone downstream has to reconstruct the missing thinking.

That is not productivity. It is cognitive work moved off the sender's desk.

## Recommended opening

Start with the observability hook, then bring in the general-purpose technology history early. The title needs to feel like a conceptual puzzle first, then get earned.

## Story beats

### Beat 1: We know how to observe what happened

Traditional telemetry records state, events, errors, latency, resource use, and action. That is necessary, but it assumes the interesting cognition lives either in deterministic software or in a human's head.

Purpose: establish the familiar ground for security and operations readers.

### Beat 2: Agentic work makes why operational

AI systems make choices, use evidence, reject alternatives, apply thresholds, spend more or less compute, and decide when to stop. For consequential work, the "why" is no longer decorative prose. It is part of the operational state.

Purpose: move from ordinary observability to cognitive observability.

Protected line:

> Why is telemetry.

### Beat 3: We have seen this adoption pattern before

Electricity and computers did not deliver full productivity through substitution alone. Their larger gains came after organizations redesigned processes, layouts, and complementary capabilities around them.

Purpose: give the article historical legitimacy and avoid making the claim sound like AI hype.

Sources to use:

- Paul David, "The Dynamo and the Computer"
- Brynjolfsson and Hitt on IT and organizational complements
- Brynjolfsson, Rock, and Syverson on the productivity J-curve

### Beat 4: We are mostly using AI as substitution

Existing workflow plus AI produces faster reports, faster emails, faster code, faster analysis. Useful, but still analogous to putting one big electric motor into a steam-era factory.

Purpose: diagnose the present state without dismissing real value.

### Beat 5: The failure mode is workslop

Bad AI workflow:

> Person gives thin prompt -> AI generates polished artifact -> person forwards it -> recipient reconstructs missing thinking.

The organization may have saved time locally and created more work globally.

Protected line:

> AI can make an individual more productive while making the organization less productive.

Purpose: make the problem concrete and timely.

### Beat 6: The missing output is not the document, it is the rationale

Example: "Build this in Python as a reusable library, then expose it through an MCP server." The artifact may be good, but the organization also needs to know why that architecture was chosen.

Possible rationale:

- business logic should remain independent of transport;
- library should be testable directly;
- MCP should be a thin adapter;
- other interfaces may come later;
- security controls should live below the MCP layer.

If that rationale disappears, a later developer can locally improve the MCP server while globally damaging the architecture.

Purpose: show why rationale matters without getting too abstract.

### Beat 7: Important cognition should leave durable organizational state

The organization needs durable records of:

- intent;
- evidence;
- assumptions;
- alternatives;
- rejected approaches;
- expected outcomes;
- actual outcomes;
- lessons learned.

GitHub is the concrete analogy: issue, discussion, proposed change, review, commit, merge, and history.

Purpose: convert "why" into operational design.

### Beat 8: Once why becomes telemetry, judgment becomes data

Protected line:

> Once why becomes telemetry, judgment becomes data.

Now the organization can ask:

- Which judgments correlated with good outcomes?
- Which rejected alternatives keep resurfacing?
- Which assumptions repeatedly fail?
- Which evaluators drifted?
- Which local optimizations damaged the larger system?

Purpose: the conceptual pivot.

### Beat 9: Logged rationale is not truth

Counterargument:

Humans rationalize. Models rationalize. Stated intent can be wrong or gamed. The answer is not to believe every explanation. The answer is to capture structured claims about intent, evidence, assumptions, and expected outcomes, then test them over time.

Purpose: credibility and honesty.

### Beat 10: Doing the work should improve the system

The payoff is a loop:

> Do work -> capture why -> compare outcome against expectation -> extract lesson -> update process -> next work starts from improved state.

Protected line:

> The answer is not simply better prompting. It is redesigning the work so that doing the work also teaches the organization how to do the work better next time.

Close:

> The highest-value question may not be whether AI helped us do this piece of work faster, but whether doing the work left the organization better at doing the next one.

Purpose: land the recursive improvement implication without overhyping RSI.

## Protected lines

These lines are doing structural work. Drafts can adjust the surrounding prose, but these should survive unless Kurt explicitly changes them.

1. **"Why is telemetry."**  
   The title and conceptual turn. It should appear after the opening earns it.

2. **"Once why becomes telemetry, judgment becomes data."**  
   The pivot from observability to organizational learning.

3. **"AI can make an individual more productive while making the organization less productive."**  
   The workslop failure mode in one sentence.

4. **"The answer is not simply better prompting. It is redesigning the work so that doing the work also teaches the organization how to do the work better next time."**  
   The operational prescription.

5. **"The highest-value question may not be whether AI helped us do this piece of work faster, but whether doing the work left the organization better at doing the next one."**  
   Candidate closing thesis in plain English.

## Voice notes

- Use concrete operational examples, not abstract organizational theory.
- Let the historical sources support the claim, but do not linger in them.
- Do not make "RSI" the headline or early vocabulary.
- Keep "why" as structured claims linked to evidence and outcomes, not chain-of-thought disclosure.
- Be careful not to imply that every routine action needs exhaustive rationale.
- Use the article-writing process as a subtle meta-example only if it helps, not as a running self-reference.

## Decisions made

| Decision | Why |
|---|---|
| Title is `Why Is Telemetry` | Strongest phrase and broad enough to carry observability, rationale, and recursive improvement |
| Historical frame uses electricity and computers | Best supported analogy for general-purpose technologies needing complementary redesign |
| Workslop is the contemporary failure mode | Names the local-productivity/global-cost problem |
| RSI language arrives late | The article should feel like a practical observability and organization argument first |
| Labs holds the framework | Circle News should be a column, not a manual |

## Decisions against

| Out | Why |
|---|---|
| A full taxonomy of recursive organizations in the column | Too much for Circle News |
| A long power-tool analogy | Good but redundant with electricity and computers |
| Presenting 3-6 iterations as a universal rule | Useful observation, not yet evidence |
| Full KnowledgeBOM/CognitiveBOM explanation in the column | Could distract; the logic matters more than the label |
| Claiming rationale is reliable ground truth | It is evidence to test, not truth to trust |

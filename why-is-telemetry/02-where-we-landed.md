# Where We Landed

> **Snapshot from 2026-09-24, before the source sweep.** The narrative spine is superseded by `10-story-beat-synthesis.md`. The later decisions (lineage framing, callbacks, naming, sanitization) are in `CognitiveBOM.md` C15-C19. The thesis and protected lines below still stand.

## Working title

**Why Is Telemetry**

## Core thesis

Traditional telemetry tells us what happened. AI-native organizations need to preserve why consequential work was done, what alternatives were considered, what evidence and assumptions shaped the decision, what outcome was expected, and what actually happened.

Once why becomes telemetry, judgment becomes data. Once judgment becomes data, the organization can learn not only whether an output succeeded, but how to improve the workflows, evaluators, resource allocation, and governance that produced it.

## Column in one paragraph

We have seen this movie before. General-purpose technologies such as electricity and computing did not produce their largest gains when organizations merely substituted the new technology into old workflows. The bigger gains came after organizations redesigned themselves around what the technology made possible. AI is at the same stage. If we only add AI to inherited workflows, we may create faster output and worse organizations: polished workslop, missing rationale, and downstream cognitive cleanup. The opportunity is to redesign knowledge work around cheap, repeatable machine cognition, but that only works if the work leaves behind durable state: intent, evidence, assumptions, alternatives, judgment, and outcomes. Why is telemetry.

## Narrative spine

1. **General-purpose technologies need organizational redesign.** Electricity and computers are the historical anchors.
2. **Most AI use is still substitution.** Existing workflow plus AI: faster email, reports, code, analysis.
3. **Substitution creates a failure mode.** AI can make one person appear more productive while shifting cognitive labor downstream.
4. **The deeper opportunity is redesigning knowledge work around cheap cognition.** Multiple variants, replay, challenger workflows, deep probes, and branch-and-prune become practical.
5. **This requires durable organizational state.** Not just the artifact, but intent, evidence, assumptions, alternatives, deviations, judgments, and expected outcomes.
6. **Core pivot: why is telemetry.** The title lands as the article's conceptual turn.
7. **Once why becomes telemetry, judgment becomes data.** This lets the organization compare expectations with outcomes.
8. **Doing the work can improve the process for doing the work.** Work -> observe -> compare -> learn -> update process -> next execution starts from a better state.
9. **The larger implication is governed recursive improvement.** The article should let this arrive late, not open with it.
10. **Close by returning to the title.** Traditional telemetry asks what happened. AI-native organizations also need to know why.

## What belongs in Circle News

The column should carry the argument, not the whole framework.

Use:

- electricity plus computers as the historical frame;
- workslop as the current failure mode;
- the software architecture example or article-production process as the "why matters" case;
- a compact version of the recursive improvement loop;
- one caveat that logged rationale is not truth.

Do not overload the column with:

- full design-dimensions framework;
- all experiment patterns;
- all RSI literature;
- full KnowledgeBOM/CognitiveBOM schema;
- power tools analogy unless the prose needs one personal example;
- extended Labs architecture.

## What belongs on Labs

Labs should be the machinery behind the argument:

- anatomy of a recursively improving workflow;
- design dimensions for AI-native workflows;
- maturity model;
- KnowledgeBOM and CognitiveBOM examples;
- economics and compute allocation model;
- experiment pattern catalogue;
- source appendix;
- longer treatment of recursive self-improvement.

## Decisions made

| Decision | Rationale |
|---|---|
| Use **Why Is Telemetry** as the working title | Short, memorable, observability-native, and capable of scaling from logs to organizational learning |
| Lead with observability and organizational redesign, not RSI | RSI is the implication, not the hook; leading with it makes the piece feel like AI research instead of a CSA business/security column |
| Use electricity and computers, not a long history tour | The historical analogy should frame the argument and then get out of the way |
| Use workslop as the present-day failure mode | It is concrete, current, and directly names the downstream cognitive-labor shift |
| Treat rationale as testable claims, not truth | Prevents the obvious objection that humans and models rationalize |
| Split Circle News from Labs | The column should be a dense argument; Labs can hold the reference implementation |

## Decisions against

| Rejected path | Why it is out |
|---|---|
| Headline about recursive self-improvement | Too AI-research-coded; would narrow the audience and make the piece sound more speculative |
| "Why do we only do knowledge work once?" as title | Good insight, but weaker than "Why Is Telemetry" as the conceptual spine |
| Full power tools analogy in the column | Useful, but electricity plus computers already do the historical work |
| Full design framework in the Circle News piece | Would turn the article into a report and weaken the narrative |
| Claiming a universal 3-6 iteration pattern | Useful personal observation from Kurt's work, but should be framed as observed practice, not research result |
| Treating logged why as authoritative | The correct claim is capture structured claims and test them against evidence and outcomes |

## Open editorial questions

1. Which two or three examples carry the published column?
2. How much of the software architecture example goes in the article versus Labs?
3. Does the article mention KnowledgeBOM/CognitiveBOM by name, or only use their logic?
4. Does the close name "recursive self-improvement," or imply it with "doing the work teaches the organization how to do the next one better"?
5. Which sources are cited inline versus parked in Labs?

## Protected lines to defend

> Why is telemetry.

> Once why becomes telemetry, judgment becomes data.

> AI can make an individual more productive while making the organization less productive.

> The answer is not simply better prompting. It is redesigning the work so that doing the work also teaches the organization how to do the work better next time.

> The highest-value question may not be whether AI helped us do this piece of work faster, but whether doing the work left the organization better at doing the next one.

## Current readiness

The article is ready for one more tightening pass, then `draft-01.md`. The remaining work is editorial compression and example selection, not conceptual discovery.

# Coverage Check: columns 78-89

**Run:** 2026-09-24, against the full text of columns 78-89. Sources: `previous-columns/` for
78-86; for 87-89, the final drafts `87 draft-01.md`, `88 draft-02.md` and `89 draft-04.md`.

**Window note:** columns 85 (Feb 2026), 87 (May), 88 (Jun) and 89 (Aug) are dated. Columns 78-84
were bulk-imported and carry no publication date in the repo. I read 78-89 so the window safely
covers the last 12 months.

## Verdict

**Nearly every supporting beat in this packet has already appeared in a recent column. The one
new thing is the expected outcome, scored against what happened.** Read in sequence, 78 → 80 →
87 → 89 are building toward this column:

- 78 said track the rationale.
- 80 said AI makes capturing it affordable.
- 87 said make the reasoning reviewable, including what was dismissed.
- 89 said keep the stops and learn from them.

This column is the culmination: **the organization learning from its own judgment.** That
is a strength if the draft uses callbacks and spends its words on the new part. It is a problem if
the draft re-explains 87, 88 and 89 to readers who read them one to four months ago.

## Collisions, most serious first

### 1. Column 88 already told the Paul David story (June 2026). Serious.

88 ("Obsolete or Critical: It Depends"): *"Factories had electric motors for decades before they
saw any productivity payoff, because at first they just bolted the new motors onto the old
layout, the central shaft and the belts ... The economist Paul David told that story in 1990 ...
Computers, in Robert Solow's line from 1987 ... the productivity J-curve ... The payoff lives in
the practice, not the purchase."*

That is Beat 3 of this packet, including the J-curve citation, published three months ago.

- **Recommendation:** do not retell it. Use a one-clause callback ("in June I used Paul David's
  dynamo story to make a different point") and move to the part 88 did not use. That is David's own
  p. 360 turn: a firm's *information structures* are the modern counterpart of the factory layout,
  and unlike buildings they never wear out, so nothing forces a redesign. That line is new to the
  series and leads straight into "why is telemetry."

### 2. Column 80 already made the "failed on human cost, now viable" argument. Serious for Claim 7b.

80 ("The Necessary Work Paradox"): *"More mature project management will capture ... who made
the call and why for a particular decision. The gold standard is to track every underlying
constraint ... and then monitor those constraints so that when they shift, the team can revisit
the decision ... historically, that level of rigor has been impossible for most of us ... With
AI, though, the impossible becomes possible. An AI system can extract decisions, reasons, and
constraints from meeting transcripts."*

This is the economics half of the lineage beat Kurt decided on today, in Kurt's own words.

- **What is new since 80:**
  - The 55-year lineage (IBIS, Grudin's "who pays, who benefits").
  - The move from *capturing* the why to *scoring* it against outcomes.
  - The beneficiary point: the next AI run consumes the why right away (H9, `MINE`).
- **Recommendation:** keep Claim 7b but frame it as picking up 80's thread ("in column 80 I
  argued AI makes capturing decisions affordable; the harder question is what you do with them").
  Let the lineage carry the history, and do not re-argue the cost collapse.

### 3. Column 87 already asked for reasoning chains and "what was considered and dismissed". Moderate.

87 ("Validating AI output"): the three foundational items are *"structured reasoning chains ...
citations and evidence ... and this is the one nobody is yet asking of AI, what the producer
considered and dismissed."* It also says *"The producer is responsible not for being correct,
but for being legibly reasoned,"* and *"An AI whose judgment must be fully revalidated has not
eliminated the work; it has moved it."*

That overlaps Beat 6-7 (durable rationale, rejected alternatives) and the workslop beat's "it
may not have saved work, it may have moved work."

- **The difference:** 87 is about *reviewing output now*. This column is about *learning over
  time*, which is 87's rationale plus an expected outcome, joined later to what happened.
- **Recommendation:** callback to 87 in one sentence ("in May I argued the AI should show what
  it considered and dismissed so we can review it; the next step is to write down what it
  expected, so we can learn from it"). Rephrase the workslop "moved the work" line so it does not
  echo 87's.

### 4. Column 89 already argued for keeping the stops, reading them together, and not punishing the reporter. Moderate, and a positioning gift.

89 ("Nothing Found Is the Most Welcome Answer You Get"):

- *"Recording the disposition costs almost nothing"*
- *"read them together, which is where the value is"*
- *"do it without punishing the reporter ... you have taught your own system to stop telling
  you"*

That is sweep 4's "never grade the rationale" rule in practice. It also closes on self-improvement:
*"the bottleneck is the evaluator ... an evaluator is built out of ... honest records of what went
wrong."*

- **Close risk:** this packet's Beat 10 (doing the work improves the next execution) is close to
  89's final move, published a month earlier.
- **Positioning gift:** 89 learned from the decisions where the machine *stopped*. This column
  learns from the decisions where it *did not stop*, which are the other 99 percent. That is a
  clean one-line bridge and a real generalization.
- **Recommendation:** use the bridge. End on something 89 did not say, the expected outcome and
  the scoring, rather than on the evaluator.

### 5. Column 78 contains this column's thesis as one bullet. A callback opportunity, not a problem.

78 ("Agentic AI: The Third Time We've Made This Trade-off"): *"Build comprehensive monitoring
and audit trails: Track not just outcomes but decision rationales and the confidence the AI has
in them. Understand what changed, when, and why ... you can build a system that can explain
itself to a degree not possible before."*

- **Recommendation:** optional, and a good one. "A while ago I put 'track decision rationales'
  in a list of four bullets. It deserved a column." It is honest, it shows the thinking evolving,
  and it matches the packet's "contradict on purpose, not by accident" practice.

### 6. Column 81 covers intent as the real artifact. Minor.

81 ("What Happens When the Cost of Coding Drops to Zero"): *"From 'How do we build it?' to
'What exactly are we building, and why?'"* It also says the specification carries intent: "Updates
become edits to the spec, not archaeology in the codebase."

The library/MCP rationale example (Beat 6) is adjacent. It is fine as long as the draft frames the
example around *losing the why after the build*, not writing the spec before it.

### 7. Minor or none

- **83** (work exfiltration): "No logs, no audit trail," and polished AI output hides errors.
  Adjacent to workslop; no action.
- **85** (agent social networks): machine interpretation of intent; sense-making before building.
  No action.
- **86** (acceptable insecurity): reversibility and bounded failure. No action.
- **79, 82, 84:** no meaningful overlap. 84's point that frontier training runs on failed
  experiments is faintly related to the exploration dividend, which is already on the cutting-room
  floor.

## Other consistency findings

- **BOM naming conflict.** Column 89's packet already has `COGNITION-BOM.md`. It explicitly
  rejected "CBOM" because of the Cryptographic Bill of Materials collision and chose "CogBOM" as
  the interim short form. This packet's `CognitiveBOM.md` (since renamed) said it "kept the requested name". Align with
  89: rename to `COGNITION-BOM.md` / CogBOM, or record why this piece differs. This is two sources
  of truth for one concept, which is the drift the repo's consistency-sweep practice exists to
  catch. **Resolved 2026-09-24:** Kurt chose **KnowledgeBOM** / **CognitiveBOM** for all repos
  (issues filed against the related research and project repos).
- **An unpublished seed on judgment pipelines** ("build the judgement pipeline rather than
  doing the judgement"). It overlaps this packet's evaluator and judgment material. It is not
  published, so there is no collision. Note it so the two do not later claim the same ground.
- **Tone.** 88 and 89 both end on a human-behaviour admission ("we still have not relearned it";
  "we are teaching the machine that the stopping was the problem"). A third consecutive ending
  of that shape would read as a formula.

## What this means for the draft

The column still has a clear, unpublished core: **record what you expected, then score it
against what happened, so the organization learns which of its judgments were right.** Nothing in
78-89 does that. 88 is about re-measuring *practices*, and 89 is about learning from *stops*.

**Recommended word budget shift** (Kurt's call):

- Cut the history retelling to a callback plus David's information-structures line.
- Cut the capture-cost argument to a callback to 80.
- Keep the lineage (IBIS to now) short.
- Spend the freed words on the expected outcome and on what scoring judgment looks like in
  practice. That part is new for the column and for the field (sweep 3: nobody records the agent's
  own prediction).

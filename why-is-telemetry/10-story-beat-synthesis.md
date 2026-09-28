# Story Beat Synthesis: the Circle News column

**Rewritten 2026-09-28.** It now reflects the source sweep (`11`), the lineage decision
(CognitiveBOM C15), the coverage check (`12`, C16), the first-person MCP material (`14`) and the
public-release sanitization.

**This file is the canonical beat map for `draft-01`.** Where `04-research-notes.md` "Column
structure" disagrees with it, this file wins.

**Shape:**
- about 1,900 words;
- continuous prose, no headers, no em dashes;
- inline URL citations, 6-8 at most.

**Voice:** first person, where the examples are Kurt's own. Calibrate against 87, 88 and 89.

## The one idea that is new

> Record what you expected before you know the result, then score it against what happened. That
> is what turns a record of judgment into data you can learn from.

Nothing in columns 78-89 says this, and the sweep found no standard, tool or vendor recording an
AI agent's own expected outcome. **Every other beat exists to set this up or make it safe.** It
gets the most words.

## Intended reader progression

1. "Telemetry tells me what happened. Fine."
2. "AI is now making the calls where the *why* matters."
3. "Just adding AI to old workflows is producing polish without the thinking. I've seen that."
4. "What's missing is the reasoning, and losing it breaks things later."
5. "People have tried to capture reasoning for 55 years. It failed on cost. AI changes the cost."
6. "But capturing it isn't enough on its own."
7. "The missing piece is the prediction, written down before the result."
8. "And I can't just trust the reasons. I test them."
9. "I could start this next week with three fields."

## Beats

### Beat 1: Hook, what telemetry already tells us (~150 words)

- **Purpose:** familiar ground for security readers. The piece extends observability; it doesn't
  abandon it.
- **Content:** we built systems that record *what* happened: the error, the blocked connection,
  the approved expense, the tool call. Increasingly the question I care about is *why*.
- **Sources:** none.
- **Callbacks:** none.

### Beat 2: Why is telemetry (~200 words)

- **Purpose:** make "why" operational, not philosophical.
- **Content:**
  - Agents choose sources, reject alternatives, decide an answer is good enough, spend more
    compute, and decide not to escalate. For consequential work those reasons are operational
    state.
  - **Protected line 1:** *Why is telemetry.*
- **Bridge from 89 (one sentence):** last month was about learning from the times the machine
  stopped; this is about the far larger number of decisions it made without stopping. (Do not put a number on it; there is no source for one.)

### Beat 3: Substitution, and the polish without the thinking (~300 words)

- **Purpose:** the present-day problem, grounded in history without retelling it.
- **Callback to 88 (one clause):** in June I used Paul David's dynamo story, factories bolting
  motors onto the old layout, to make a different point.
- **The new part:** David's own p. 360 line. A firm's *"information structures ... may be seen as
  direct counterparts of the physical layouts"* of factories, and they *"do not automatically
  undergo significant physical depreciation,"* so nothing forces the redesign.
  - That makes the information structure the factory floor of AI adoption. Most of us bolted AI
    onto it.
- **Workslop:**
  - Definition: *"AI generated work content that masquerades as good work, but lacks the substance
    to meaningfully advance a given task"* (HBR, Sep 2025).
  - Figures: **40%** received it in the past month, **1 hour 56 minutes** per instance, from a
    self-reported survey of 1,150 U.S. desk workers.
- **Protected line 3:** *AI can make an individual more productive while making the organization
  less productive.*
- **Word to avoid:** don't write "moved the work". Column 87 used that phrasing. Say the thinking
  was left for the recipient to reconstruct.
- **Citations:**
  - David 1990: https://gwern.net/doc/economics/automation/1990-david.pdf
  - HBR workslop: https://hbr.org/2025/09/ai-generated-workslop-is-destroying-productivity
- **Optional:** DORA 2024's "increases individual productivity ... negatively impacts software
  delivery stability and throughput." Use it only if the beat has room.

### Beat 4: What goes missing is the why (~200 words)

- **Purpose:** move from workslop to the mechanism.
- **Content:**
  - Kurt's rule: build the library first, with the MCP server as a thin adapter, and put the
    security controls in the library, never in the server.
  - Why: the library can be called without the server, so a control in the server is one library
    users don't get.
  - **"This project has paid for that lesson four separate times."** Each time, a locally sensible
    change undid a reason nobody could see. This is the failure side of the first-person pair.
- **Echo:** Nygard (2011). Without the rationale a newcomer can *"blindly accept the decision"* or
  *"blindly change it."*
- **Callback to 87 (one sentence):** in May I argued an AI should show what it considered and
  dismissed, so its work can be reviewed.

### Beat 5: The lineage, 55 years of trying (~300 words)

- **Purpose:** the "why now". Kurt's framing: the idea has old roots, failed because of humans,
  resurfaced with AI, and is ready now.
- **Content:**
  - IBIS (1970), design rationale, decision records, Python's "Rejected Ideas" sections.
  - It failed because of humans. The person recording paid for it, and someone else benefited
    later, if the project survived at all (Grudin 1996).
  - *"a good deal of experience is unrecorded simply because the costs are too great"* (Levitt &
    March 1988).
- **Callback to 80 (one line):** I argued AI makes capturing decisions affordable. The harder
  question is what you do with them.
- **The detail from Kurt's own desk:** his decision-log standard chose a five-field format over a
  47-field one because *"the 5-field format gets written; the 47-field format gets skipped."* The
  field that tracked actual impact was in the version nobody used.
- **What changed:**
  - Capture is now a by-product of the agent doing the work.
  - The next reader of the why is the next AI run, tomorrow morning, not a stranger in five years.
    This shrinks Grudin's "someone else benefits" problem. `MINE`.
  - The why can now be scored. Across 55,000+ forecast explanations, LLM-scored rationale quality
    predicted accuracy (Karvetski, Tetlock, Karger et al. 2026).
- **Citations:**
  - Grudin 1996: http://jonathangrudin.com/wp-content/uploads/2017/03/DesRat1996.pdf
  - Karvetski et al. 2026: https://arxiv.org/abs/2606.30987

### Beat 6: The turn, capturing isn't enough (~150 words)

- **Purpose:** keeps the column from being "just write more down".
- **Content:**
  - "It has resurfaced with AI": spec files, agent checkpoints on every commit, decision traces.
    Do not cite Foundation Capital (C15).
  - But a 2026 study found that giving coding agents repository context files (AGENTS.md style) did
    not generally improve task success, and it raised cost by 20% or more. Say "context files",
    not "intent records": the study tested instructions handed to the agent, not rationale it
    recorded.
  - The record by itself isn't the value. The value is in closing the loop.
- **Citation:** https://arxiv.org/abs/2602.11988

### Beat 7: The core, judgment becomes data only if you wrote down what you expected (~400 words)

- **Purpose:** the new idea, given room.
- **Protected line 2:** *Once why becomes telemetry, judgment becomes data.* Add the condition: it
  only becomes data when it includes a prediction that can be scored.
- **Precedents that close the loop:**
  - The Army after-action review starts from *"what was supposed to happen"* (TC 25-20).
  - Forecasting tournaments score predictions logged in advance.
  - Almost nobody records an AI agent's own expected outcome. Phrase it as "I could not find", because it rests on a negative search. NIST AI RMF compares intended with actual performance, but at system level only. No observability standard has a field
    for it, and neither do the security or regulatory frameworks.
- **First person, the success side:** the H1/H2 test.
  - *"I wrote down two known gaps in a filter. When we tested them against real email, one turned
    out to be unreachable and the other leaked exactly as predicted."*
  - Prediction recorded, prediction checked. The known-gap test was committed on 2026-09-22, two
    days before the live run on 2026-09-24, so the prediction really was on record first.
  - **Anticipate the skeptic** ("that's just testing"): yes, and that is the point. Engineering
    already does this for code. The column asks for the same move on decisions. Kurt's own
    decision template has no expected-outcome field, which is why he is going first.
  - Public, linkable: https://github.com/CloudSecurityAlliance/csa-zendesk/tree/main/experiments/2026-09-24-h1-h2-reachability
- **Falsifiability (one sentence, Kurt's voice):** "a test that cannot fail has not been run." An
  expected outcome that can't turn out wrong isn't a prediction.
- **Kurt's rule for what gets one:** hard to reverse, surprising without context, a real trade-off.
  Not everything does.

### Beat 8: The caveat, as design rules (~250 words)

- **Purpose:** credibility. A written reason is a claim, not the truth.
- **First person, continuing H1:** the gap leaked, but *not for the reason I had written down*.
  - The record said we *couldn't* detect it.
  - In fact we had *chosen* not to, because the simple rule flagged mostly ordinary email design:
    82.6% of everything it caught. Say "ordinary email design", **not** "false positives" (see `14`).
  - Written down, the wrong reason was catchable. Unwritten, the next engineer "fixes" it and floods
    the pipeline.
- **One external number, pick one:**
  - Reasoning models mention the hint that actually changed their answer only 25-39% of the time
    (Chen et al. 2025): https://arxiv.org/abs/2505.05410
  - Or choice blindness: only 13% of secretly swapped choices were noticed.
- **The rules:**
  - Capture before the outcome.
  - Score after.
  - Never grade the rationale itself. Train against a model's reasoning and it learns to hide it
    (Baker et al. 2025): https://arxiv.org/abs/2503.11926
- **Optional stat:** when journals accepted papers before results were known, "confirmed"
  hypotheses fell from 96% to 44% (Scheel et al. 2021).

### Beat 9: Close, someone has to go first (~150 words)

- **Purpose:** end on an invitation, not an admission. 88 and 89 both ended on admissions.
- **Content:**
  - The minimum experiment: on the next decision that passes the three-question test, add three
    fields to the record: *intent, the evidence relied on, expected outcome and when you'll check*.
  - Check it on the date.
  - I'm doing it on the Labs page, in public. Link it, if v0.1 is live.
- **Protected line 4:** *The answer is not simply better prompting. It is redesigning the work so
  that doing the work also teaches the organization how to do the work better next time.*
- **Protected line 5 (final line):** *The highest-value question may not be whether AI helped us do
  this piece of work faster, but whether doing the work left the organization better at doing the
  next one.*

## Word budget

| Beats | Words | Share |
|---|---|---|
| 1-4 (setup) | ~850 | 45% |
| 5-6 (why now, and the turn) | ~450 | |
| 7-8 (new material) | ~650 | 35% |
| 9 (close) | ~150 | |

**If it runs long, cut in this order:**
1. Beat 3's DORA line.
2. Beat 8's optional stat.
3. Beat 5 trimmed to Grudin, Levitt & March, and the five-field detail.

**Never cut:** Beats 7 and 8, the MCP pair, the protected lines.

## Decisions in this map

| Decision | Status |
|---|---|
| Drop "recursive self-improvement" from the column entirely. Beat 9 says it in plain English. 89 already ended on self-improvement. | Proposed default |
| End on an invitation (Beat 9), not an admission | Proposed default |
| Opening: the telemetry hook, not Argyris's thermostat. The thermostat goes to Labs. | Proposed default |
| The first-person pair comes from the public MCP work only | Decided (C17) |
| Name no BOMs in the column. Link the Labs page instead. | Proposed default |

## Citation plan (6-8 inline)

David 1990 · HBR workslop · Grudin 1996 · Karvetski et al. 2026 · ETH context-files 2026 ·
csa-zendesk H1/H2 · Chen 2025 or Baker 2025 · the Labs page.

# First-person case material: the CSA MCP server work

**Captured:** 2026-09-24. **Sanitized for public release:** 2026-09-25.

Kurt pointed at his MCP server work as the column's real example. The AI checks output quality,
the AI checks whether there is a better way, and the work records a lot of *why*.

**Sources:**
- CSA's public MCP server repositories, notably `csa-zendesk` (github.com/CloudSecurityAlliance/csa-zendesk), including `experiments/2026-09-24-h1-h2-reachability/RESULTS.md`.
- CSA's internal platform-engineering playbook: its decision-logging standard and cross-project decision records. It is described here, not linked.

This material replaces the packet's hypothetical examples with real ones. The library-plus-MCP
example in Beat 6 / Claim 4 turns out to be Kurt's actual rule, with a count attached.

---

## 1. What the practice already captures (and what it doesn't)

The internal decision-logging standard calls decision logging *"the single highest-value practice
for AI-native work."* Its reason: *"Without it, every AI session re-proposes rejected ideas,
re-litigates settled questions, and guesses at constraints that were already understood."*

A decision record has five fields:
1. what we decided;
2. why;
3. **what we explicitly didn't do and why** ("the most valuable part and the part most likely to be skipped");
4. **what would make us revisit this**;
5. what it connects to.

There is also an optional **Assumptions** section: "We assume X (if wrong, revisit this decision)."

The gate for writing one is three criteria, all required: hard to reverse, surprising without
context, and a real trade-off. That answers the packet's voice note, "not every routine action
needs rationale." The practice already has a proportionality test.

**The gap, and the column's best detail:**
- The lightweight format has no **expected outcome** field. Nothing records what we predicted would
  happen, to be checked later.
- The *heavy* organizational version (a much larger governance schema) *does* include "AI
  confidence ratings" and "actual impact tracking."
- The decision that chose the lightweight format says why the heavy one lost: *"The 5-field format
  gets written; the 47-field format gets skipped."*

So in Kurt's own practice, the field that closes the loop lives in the version nobody uses. That is
the 55-year design-rationale failure (Grudin: capture cost) reproduced in miniature, in 2026, by
someone who believes in the practice. It is also exactly what AI now makes cheap to carry.
`MINE` synthesis; the facts are from the standard.

## 2. The library-first rule: real, and paid for four times (the failure side)

*"Controls sit at the `Backend`/`PolicyBackend` seam, never in `server.py`. The library is callable
without the MCP server, so a control in the delivery layer is one a library consumer does not get.
This project has paid for that lesson four separate times."*

This is the packet's Claim 4 example as real experience, not a thought experiment. The rationale
was lost or ignored, and a locally sensible change undid it, four times. That gives the draft a
count instead of a hypothetical, and it is the **failure side** of the first-person pair: a why that
did not travel with the code.

## 3. A recorded why that turned out to be wrong, caught only because it was written down (the success side)

The H1/H2 reachability experiment (public; `csa-zendesk/experiments/`) worked like this:

- **Recorded:** two known gaps in the email-to-Markdown converter, written down as reasons.
  - H1: white-on-white text is not detected, because the converter can't see the background.
  - H2: `<style>` block selectors are invisible.
- **Tested** against the real email channel: *"Neither had been checked against the channel that
  actually feeds this tool."*
- **H2 result:** unreachable on this path, because Zendesk inlines the CSS on email ingest (a vendor
  behaviour). It was **narrowed, not closed, "with the reason recorded — otherwise the next person
  reads 'not reachable' and deletes the handling."** This is Chesterton's fence in Kurt's own words.
- **H1 result:** "leaked exactly as predicted." That is a prediction confirmed. It was on record first: the pinned known-gap test (`test_white_on_white_is_a_KNOWN_GAP_and_still_leaks`) was committed on 2026-09-22, and the live run was on 2026-09-24.
- **The key part:** *"the interesting part is why it leaked, because it is not the reason H1
  records."* The recorded reason said *can't detect*. The truth was *deliberately chose not to*,
  because a naive colour rule produced 82.6% of all hidden-text detections (6,875 of 8,327
  elements in a 90-day, 5,215-ticket corpus), overwhelmingly white text on dark email headers, which
  is ordinary design. Keeping the rule flags 23.2% of tickets; dropping it, 5.5%. The figure is
  already published in the public experiment write-up (`RESULTS.md`). The underlying corpus study is
  internal and derived from CSA's own ticket data, so **cite the public write-up, not the study.**
  **Precision:** it is a *share of detections*, not a measured false-positive rate. "False positive"
  is an inference, because the corpus showed no hidden-text attacks. Say "82.6% of what the rule
  flagged was ordinary email design", not "82.6% false positives." 
  - *"'not detected' reads like a capability gap when it is a false-positive trade."*

**Why this matters for Beat 8 (rationale is not truth):**
- The logged why was a testable claim, and testing corrected it.
- The system didn't fail. It worked as the column says it should: capture the claim, test it
  against reality, and revise the recorded reason.
- An unrecorded gap could never have been found to be misdescribed.

This is the **success side** of the pair, and it is from a public repo, so the Labs page can link to
it.

**Plain-English version for the column** (no CSS): *"I wrote down two known gaps in a filter. When
we tested them against real email, one turned out to be unreachable and the other leaked exactly as
predicted, but for a different reason than the one I had written down."*

## 4. Recurrence becomes visible when the lessons are written down

*"Counted nine times across this project now, in different costumes: A check that isn't run is
indistinguishable from a check that passes."* The same lesson, found nine times, is only countable
because each instance was recorded.

That is the "repeated rejection is itself telemetry" idea, which sweep 3 found nowhere else, in
practice.

**Overlap warning:**
- The *line itself* rhymes with column 89 ("Silence from an analyst is indistinguishable from good
  news").
- So use the *count* ("the same lesson nine times"), not the aphorism, or make it an explicit
  callback.

## 5. "A test that cannot fail has not been run"

The testing practice is to:
- test with an account that *can* do the operation, so a block is provably yours;
- include negative controls, because "a gate that refuses everything looks identical to a correct
  gate until you show it permitting something."

**For Beat 7 (expected outcome):** an expected outcome that cannot turn out wrong is not a
prediction. The column needs one sentence on falsifiability, and this gives it in Kurt's own
voice.

## 6. Other ways of doing it: the AI proposes alternatives

Kurt has the AI check output quality (column 87) *and* check whether there is a better way. One
instance: the HTML-to-Markdown converter was chosen from a bakeoff of five candidates on three
axes, and `markdownify` won on a packaging argument. That is rejected alternatives with recorded
reasons, which is negative knowledge produced as a by-product.

This connects to the cutting-room "managed pluralism / try 2-5 approaches" material. Use one
sentence at most in the column.

## 7. Not for this column (park)

- **The bias finding** ("a detector that scores unusualness encodes the majority as normal"; each
  content detector's dominant failure was non-English content; "score the mechanism, not the
  deviation"). This is strong, transferable and CSA-relevant, and it is **its own column**. For this
  piece, one clause at most: when you score judgment in aggregate, disaggregate, or the populations
  where judgment fails vanish into the average.
- **Goal documents drift in the direction that flatters.** A stale goal is an unscored prediction.
  Labs material.

## Public-safety notes

Everything above is public-safe as written:

- **Public source:** the `csa-zendesk` experiment.
- **Described, not linked:** the internal decision-logging standard, which is Kurt's own method.
- **Removed in the 2026-09-25 sanitization:**
  - facts about CSA's own tenant;
  - an internal automation incident;
  - internal system figures;
  - pointers to private repositories.

**When drafting:** keep vendor facts (Zendesk behaviour) and drop any tenant-specific detail. That
is the rule the MCP repos themselves use: *"Facts about the vendor are public. Facts about this
tenant are not."*

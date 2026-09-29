# Decision record with an expected outcome

A decision record that can be scored. It is the five-field format CSA's CINO team already uses for
engineering decisions, **plus the fields that close the loop**: what you expect to happen, how sure
you are, and when you'll check.

## When to write one

Write one only if **all three** are true:

1. **Hard to reverse.** Changing your mind later would be expensive.
2. **Surprising without context.** A future reader, human or AI, would wonder "why did they do it
   this way?"
3. **A real trade-off.** There were genuine alternatives, and you picked one for specific reasons.

If any is missing, skip it. Easy-to-reverse decisions you just reverse. That gate is what keeps the
practice cheap enough to keep doing.

## The minimum: add three things to the record you already keep

If you already write decision records, don't adopt a new format. Add:

1. **What you intended**, the hoped outcome.
2. **The evidence you relied on**, with links or identifiers.
3. **What you expect to happen**, with a date to check. Also say what observation will settle it,
   and who will check.

On the date, record what happened, and **what you will change next time because of it**. Leave a
result unresolved when the evidence is not enough, rather than calling it met.

## The fuller record

```markdown
## DEC-NNN: Title

**Date:** YYYY-MM-DD
**Status:** Proposed | Accepted | Superseded by DEC-NNN

**Context:** What is the issue? What constraints matter?

**Decision:** What did we decide?

**Why:** The reasoning. What were we optimizing for?

**Evidence relied on:** Links or identifiers for what the decision rests on.

**Rejected alternatives:**
- **Option**: why rejected

**Assumptions:** (optional) We assume X. If wrong, revisit.

**Revisit if:** What would make this decision stop being right?

**Hoped outcome:** What we want to happen. This is the goal.
**Expected outcome:** What we actually expect to happen because of this decision. This is the
prediction, and it is often not the same as the hope. Write it so it could turn out wrong: a
prediction that can't fail isn't a prediction.
**Confidence:** How sure are we? A probability is best, e.g. 70%.
**Check by:** YYYY-MM-DD
**Resolved by:** Who checks, and what observation settles it.

<!-- Filled in on or after the check-by date. Never edit the fields above once this is filled. -->
**Actual outcome:**
**Scored on:** YYYY-MM-DD
**What we learned:** Was the reasoning right, or were we right (or wrong) for a different reason?
How did the outcome compare with the hope, and with the expectation?
**What changes next:** The specific change to the next decision or process, or "none", with why.
```

## Rules that make it work

The evidence behind each rule is in [`KnowledgeBOM.md`](KnowledgeBOM.md), sections A6 and J.

1. **Keep the hope and the expectation separate.** Plans are full of hopes. Scoring a hope against
   the outcome tells you whether you got what you wanted. Scoring expectations, over time, tells you
   whether your judgment is any good; any single result can be luck. The distance between the two is the risk you knowingly took.
2. **Write the expected outcome before you know the result.** Hindsight quietly rewrites what we
   think we expected, and we can't tell it's happening.
3. **Never edit the prediction after the outcome.** Add the result below it. Keep the wrong ones,
   because they are where the learning is.
4. **Score against what actually happened**, not against how convincing the reasoning reads. A
   well-written wrong reason and a well-written right one look the same on the page. **One result
   can be luck:** judge your judgment from the pattern across many records, not from a single hit
   or miss.
5. **Review the reasoning; never reward it for sounding good.** Checking whether the evidence exists
   and the assumptions held is the point. Rewarding convincing explanations teaches people and
   models to produce convincing explanations. (Corrected 2026-09-29: an earlier version said "never
   grade the reasoning itself", which went further than the evidence.)
6. **Treat the record as sensitive.** Free-text reasons have leaked personal data and even passwords.
7. **Check on the date.** A record nobody revisits is only documentation.

## Asking an AI to write one

When an AI agent is about to make a decision that passes the three-question gate, add this to its
instructions:

> Before acting, write a decision record using the template above: context, decision, why,
> rejected alternatives, the hoped outcome, and **an expected outcome that could turn out wrong, a
> confidence, and a check-by date**. Keep the hope and the expectation separate. Write it before you see the result. Do not revise the expected outcome after the
> result is known; record the actual outcome separately.

A plugin that does this, and that finds records whose check-by date has passed, is planned for
[csa-plugins-official](https://github.com/CloudSecurityAlliance/csa-plugins-official).

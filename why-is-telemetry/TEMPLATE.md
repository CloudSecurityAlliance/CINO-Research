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

## The record

```markdown
## DEC-NNN: Title

**Date:** YYYY-MM-DD
**Status:** Proposed | Accepted | Superseded by DEC-NNN

**Context:** What is the issue? What constraints matter?

**Decision:** What did we decide?

**Why:** The reasoning. What were we optimizing for?

**Rejected alternatives:**
- **Option**: why rejected

**Assumptions:** (optional) We assume X. If wrong, revisit.

**Revisit if:** What would make this decision stop being right?

**Expected outcome:** What we expect to happen because of this decision. Write it so it could turn
out wrong: a prediction that can't fail isn't a prediction.
**Confidence:** How sure are we? A probability is best, e.g. 70%.
**Check by:** YYYY-MM-DD

<!-- Filled in on or after the check-by date. Never edit the fields above once this is filled. -->
**Actual outcome:**
**Scored on:** YYYY-MM-DD
**What we learned:** Was the reasoning right, or were we right (or wrong) for a different reason?
```

## Rules that make it work

The evidence behind each rule is in [`KnowledgeBOM.md`](KnowledgeBOM.md), sections A6 and J.

1. **Write the expected outcome before you know the result.** Hindsight quietly rewrites what we
   think we expected, and we can't tell it's happening.
2. **Never edit the prediction after the outcome.** Add the result below it. Keep the wrong ones,
   because they are where the learning is.
3. **Score against what actually happened**, not against how convincing the reasoning reads. A
   well-written wrong reason and a well-written right one look the same on the page.
4. **Never grade the reasoning itself.** Reward good-looking rationale and you get good-looking
   rationale, not better decisions. That holds for people and for AI models.
5. **Treat the record as sensitive.** Free-text reasons have leaked personal data and even passwords.
6. **Check on the date.** A record nobody revisits is only documentation.

## Asking an AI to write one

When an AI agent is about to make a decision that passes the three-question gate, add this to its
instructions:

> Before acting, write a decision record using the template above: context, decision, why,
> rejected alternatives, and **an expected outcome that could turn out wrong, a confidence, and a
> check-by date**. Write it before you see the result. Do not revise the expected outcome after the
> result is known; record the actual outcome separately.

A plugin that does this, and that finds records whose check-by date has passed, is planned for
[csa-plugins-official](https://github.com/CloudSecurityAlliance/csa-plugins-official).

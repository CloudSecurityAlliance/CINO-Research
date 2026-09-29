# Experiment log: Why Is Telemetry

**Append-only.**
- A prediction is never edited after it is recorded.
- Outcomes are added below it, in the Results section, with the date scored.
- Wrong predictions stay.
- The git history of this file shows when each prediction was written, so readers don't have to
  take our word for it.

This is the column's own advice, applied to the column. The entries come from decisions recorded in
[`CognitiveBOM.md`](CognitiveBOM.md) (entry IDs in brackets).

## Predictions

| ID | Recorded | Decision | Expected outcome | Confidence | Check by |
|---|---|---|---|---|---|
| E1 | 2026-09-24 | Frame the idea as a 55-year lineage (design rationale since 1970) instead of anchoring on a current investor thesis [C15] | Readers who follow enterprise AI read the column as a contribution, not a restatement | not recorded | 2026-11-15 |
| E2 | 2026-09-24 | Use one-line callbacks to earlier columns instead of retelling them [C16] | Readers of the previous three columns see a series arc, not repetition | not recorded | 2026-11-15 |
| E3 | 2026-09-25 | Take the first-person examples from public MCP server work only, and drop an internal operational example [C17] | The column loses no strength from the swap | not recorded | the author's read of the first draft |
| E4 | 2026-09-28 | Nine-beat structure, with about 35% of words on the new idea [C18] | (a) The first draft lands within ~10% of 1,900 words without cutting the core beats. (b) The author's first read finds no beat that feels like a rerun of the previous three columns | not recorded | the author's read of the first draft |
| E5 | 2026-09-28 | Publish research in this public repo, and later cut a plugin [C20] | By the check date this repo exists with at least the column's own predictions scored, and the plugin is at least designed | not recorded | 2026-11-15 |

**Already a lesson:** none of these first entries recorded a confidence. The
[template](TEMPLATE.md) now has a confidence field, and entries from here on will fill it in.

## Results

*Each result is appended here on or after its check-by date. The prediction rows above are never
edited.*

### E4(a): scored 2026-09-28

**Result: met.** `draft-01` came in at 1,782 words, 6% under 1,900, with all core beats intact.

This part could be scored the same day, so it proves little. It is logged because logging the easy
ones too is the habit. E4(b) is still open.

## Provenance note (appended 2026-09-29)

An adversarial review pointed out that the claim at the top of this file ("the git history of this
file shows when each prediction was written") is not true for E1-E5.

- **E1-E5 were imported.** They were first recorded in the column's private decision ledger (the
  working CognitiveBOM) between 2026-09-24 and 2026-09-28, on the dates in the "Recorded" column.
  They were copied here when this repository was created on 2026-09-28. For these five, this file's
  history shows when they were *published*, not when they were first *written*.
- **E4(a) was already scored when it was imported.** Its expectation was committed privately 13
  minutes before the first draft was committed (2026-09-27, 19:57 and 20:10, UTC-6). That private
  record is not public, so treat the timing as our statement, not as something you can verify
  here.
- **From E6 on, every prediction is committed to this file before its outcome is known.** Only
  those entries carry the git-history evidence the header describes.

## Resolution rules (appended 2026-09-29)

Each existing entry, with who resolves it and what counts. The rules were added after the fact, so
they are labeled as such. The predictions above are unchanged.

| ID | Who resolves | Met if | Not met if | If there is no evidence by the check date |
|---|---|---|---|---|
| E1 | Kurt | At least one unsolicited reader response describes the column as a new contribution, and none describe it as a restatement of others' work | Any response describes it as a restatement | **Unresolved**, recorded as such, not as "met" |
| E2 | Kurt | A reader of earlier columns mentions continuity or a series arc, and none mention repetition | A reader mentions repetition | **Unresolved** |
| E3 | Kurt's explicit call | Kurt judges that the swap cost the column nothing | Kurt judges that it cost something | Pending Kurt |
| E4(b) | Kurt's explicit call | No beat felt like a rerun of the previous three columns | One did | Pending Kurt |
| E5 | Objective | This repository exists, the column's own predictions due by the check date are scored, and a plugin design exists | Any of the three is missing | Not met |

**What these entries do not test.** None of E1-E5 tests the column's actual thesis: that recording
and reviewing expectations improves later work. A future entry will: compare comparable work done
with and without access to earlier decision records, with the measures defined in advance. It is
allowed to fail.

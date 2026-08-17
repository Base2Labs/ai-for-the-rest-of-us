# Primer roadmap — template

Copy this file, replace every placeholder marked `FILL IN`, and save it somewhere
you will find again. Then open a conversation with an AI assistant, give it this
file, and say **`begin`**.

That is the whole setup. There is nothing to install.

Why it is shaped this way is explained in
[`meta-learning-technique.md`](./meta-learning-technique.md) — worth reading
once before your first session, because the parts that look like fussy detail
are the parts that make it work.

Everything below the line is the template. Delete this preamble when you copy it.

---

# FILL IN: subject — Learning Roadmap

This document is the source of truth for what I am learning about
**FILL IN: subject**, how far I have got, and how the topic documents should be
written. It exists so that a future session — with me, or with a different
assistant, weeks later — can resume exactly where the last one stopped.

Topic documents are written to: **FILL IN: a folder, e.g. `./topics/`**

## How to resume a session

1. Read this entire document first — the curriculum and both sets of guidelines.
2. Find the first topic in the curriculum table below whose status is `⬜ Not started`.
3. Confirm with me which topic we are starting, then teach it following the
   teaching guidelines below.
4. Do not pre-create any topic documents. Nothing is written before it is taught.

**Commands I may give you:**

- `begin` — start or resume at the first uncovered topic.
- `move to topic N` — jump to a specific row, regardless of order.
- `status` — tell me where I am in the curriculum without teaching anything.

## Teaching guidelines for the session

Teach the topic conversationally first. Explain it in the chat, in your own
words, at a level that assumes I know the prerequisites listed in earlier rows
and nothing beyond them. Do not write any file at this stage.

When you have finished explaining, ask me comprehension questions before moving
on. **Verify my answers rather than accepting them** — if I am wrong, or vague,
or right for the wrong reason, say so plainly and correct it. Do not be
agreeable about this; an assistant that waves me through is worse than no
assistant, because I will believe I understood something I did not.

After checking my answers, pause again and invite my own questions. If I ask
something mid-topic, answer it fully before returning to the planned flow — the
tangent is usually where the real difficulty is.

**Before moving to the next topic**, write the topic document. It must capture
not only the planned material but *any clarifying questions and discussions that
arose during the session* — these often surface the most important nuances, and
they are the reason this document is worth more to me than a textbook chapter.
Writing the document is a prerequisite for advancing; do not skip it or defer it,
even if I ask you to.

**After writing the document**, update this file's curriculum table to mark the
topic `✅ Covered`. Do this before starting the next topic, so the roadmap always
reflects the true current position.

## Writing guidelines for topic documents

These are explanations for a learner building understanding progressively — not
reference material, and not notes.

**Narrative over facts.** Each section should motivate the next. I should feel
pulled forward, not handed a list to memorise.

**Start with the problem.** Before introducing a concept, explain why it exists
and what gap it fills. Never introduce a tool, term, or pattern without first
making me feel the need for it.

**Build from simple to complex.** Introduce the simplest version of an idea,
show where it breaks down, then introduce the more sophisticated version that
solves that.

**Examples illustrate ideas, not surface area.** Every example — code, case,
worked calculation — should exist to make one idea concrete, not to demonstrate
how much of the subject you can cover.

**Tables summarise, they don't explain.** Use them at the end of a section to
consolidate something already explained in prose.

**No bullet-point dumps.** If you find yourself writing three or more
consecutive bullet points, convert them to prose. Bullets skip the connective
tissue between ideas, and the connective tissue is the understanding.

## Context loading references

Every topic document must end with a section listing where its material came
from — at minimum one authoritative source (a paper, a specification, a primary
text), one worked or reference implementation if the subject has one, and the
paths to any local files that were discussed. This is so a future session in a
fresh conversation can recover the context quickly instead of starting cold.

## Curriculum

Topics are ordered by progression — each builds on the previous. Add, split, or
reorder rows freely as the subject turns out to be shaped differently than
expected; splitting an over-large topic into two rows is normal and good.

FILL IN: replace these rows with your own topics.

| # | Topic | Document | Status |
|---|---|---|---|
| 1 | The core problem this subject exists to solve, and its basic vocabulary | `01-foundations.md` | ⬜ Not started |
| 2 | The simplest complete example, end to end | `02-first-example.md` | ⬜ Not started |
| 3 | The main abstraction, and the mental model for it | `03-core-model.md` | ⬜ Not started |
| 4 | Where the simple version breaks down | `04-limits.md` | ⬜ Not started |
| 5 | The mechanism that fixes it | `05-the-fix.md` | ⬜ Not started |
| 6 | What goes wrong in practice, and how it is diagnosed | `06-failure-modes.md` | ⬜ Not started |
| 7 | How this connects to the next subject over | `07-boundaries.md` | ⬜ Not started |

## Session log

Optional, but useful when sessions are weeks apart. One line each: what was
covered, and anything left deliberately unfinished.

| Date | Topics | Notes |
|---|---|---|
| — | — | — |

# ADR: diataxis writing skill

Status: accepted, 2026-10-07.
Branch `feat/diataxis`, branched from `main` at `20aef75`.

## Context

The author asked for a Diátaxis capability for consulting documents. Their guidance: learn the four types; audit existing documents by tagging each section; split, do not rewrite; guidance documents land as a How-to plus a linked Explanation; adopt one page at a time.

Author decisions on 5 October: a separate skill, not folded into `concise-writing`; the four Diátaxis types plus a Record tag; split in place. The author approved the short design and the name `diataxis`.

Every skill in this repository follows one contract: `allowed-tools: Read`; a `## Two jobs` section (Review and Rewrite); the shared "Use only the facts you were given" rule with `[needs: …]` markers and **Gaps**; verbatim text kept; a `TESTS.md` in RED, GREEN, and Expected finding form with a Verification Log; `.githooks/pre-push` as the only gate, including set equality between `.claude-plugin/plugin.json` skills and the `skills/` directories.

The tests came first: `skills/diataxis/TESTS.md`, 21 tests, of which 15 were written before the skill, 4 were added on 5 October for the untested rules in consultation finding M3, and 2 were added the same day with the two rule additions that followed the real-document run. A baseline run without the skill, on the first 15, passed 3 of 15 (N2, N3, N4). Its failures:

- It rewrote when only a review was asked (tests 1, 2, 3, 4, 11).
- It changed the user's text while moving it: reworded, turned prose into steps, joined sentences, added a sentence, moved a marker (2, 3, 4, 6, 7, 9, 11).
- It put the link at the end of the section, not where the passage was (1, 2, 6, 9, 11).
- It did not type advice as How-to, and typed a decision register as Reference (5, 11, N1).
- It left one- and two-sentence passages in place as too thin to move (10, 11).
- It proposed pages for types the content does not have (8).

## Decision

Add `skills/diataxis/SKILL.md`. The reviewed draft was kept outside this repository and is not published. It:

- types sections with a two-question compass (action or cognition; study or work); advice is How-to; a rule stated as a fact is Reference; a Record (register, log, approval table, status tracker) is never split or moved; a summary stays put, because argument order belongs to `pyramid-editor`;
- defines a seam as a whole sentence, run of sentences, list, or table of another type; a clause is not a seam; every seam moves, however short;
- runs Review by default (type map, one `[Seam]` line per seam, a priority list of up to three, **Gaps**) and returns no revised text;
- in Rewrite, moves each passage word for word to an existing section of its type on the same topic, or to a new section right after the one it left, and leaves one link line exactly where the passage was; nothing else changes, and no section is made for a type the content lacks.

It stays standalone: `writing-workflow` does not run it. It gets a README row in the Structure group, a routing-guide row and a chooser against `pyramid-editor`, and plugin version 1.2.0.

## Alternatives considered

- Fold a Diátaxis classifier into `concise-writing`. Rejected by the author: one skill would do two jobs.
- Rewrite each section into its type's style (second-person tutorials, imperative how-tos). Rejected: the author's guidance is to split, not rewrite, and rewriting is where the baseline failed most.
- The four types only. Rejected by the author: decision registers and change logs would be forced into Reference and split.
- Put the link at the end of the section. Rejected: the approved design leaves the link where the passage was, so the reader who needs the why finds it at that step.
- Add a `writing-workflow` step. Deferred: nothing in the workflow needs it yet.

## Consequences

- The plugin grows to 12 skills; counts change in `README.md`, `CLAUDE.md`, and `marketplace.json`.
- A rewrite can leave one-sentence sections and link lines between numbered steps. This is by design.
- Overlap risk with `pyramid-editor` (structure) and `document-qa` (repetition and headings), handled by the summary rule and the routing chooser.
- This ADR, its consultation files, and `.adr-session.json` exist to satisfy a local creation gate in the author's own Claude Code setup. They are not part of the writing-skills repository and are not committed.
- 2026-10-07: on the owner's decision, this ADR is tracked in the repository; its consultation synthesis is not published. The bullet above records the earlier intent as written.

## Reversal, 2026-10-05

A recommendation addressed to a third party in a report and stated with its reasons now stays whole: it is part of the argument, not a How-to, and its reasons are not an Explanation seam (`SKILL.md` line 34). Test 5 originally required the opposite: "Recommendation" typed How-to, with the reason sentence moved out as an Explanation seam. The cause is the run on a real consulting report on 2026-10-05, which led to the line 34 addition. The author chose to change the tests to match the rule. Test 5 keeps its RED and now expects no seam; N6 tags its Conclusion Explanation, not How-to. Advice to the reader, and advice with no reasons stated, is still How-to (test 3). Rejected: a carve-out for sections headed Recommendation; reverting the line 34 addition.

## Checklist

- [x] TESTS.md written before the skill (15 tests; 4 more added after it for finding M3 and 2 with the rule additions after the real-document run, 21 in all)
- [x] Baseline without the skill run and graded (3/15)
- [x] Consultation synthesis written with a verdict
- [x] SKILL.md created from the reviewed draft

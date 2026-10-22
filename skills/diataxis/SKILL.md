---
name: diataxis
description: Use when a document, page, or section mixes kinds of content, such as steps interrupted by background, advice inside a reference table, or a lookup table inside a lesson, or when the user asks for a Diátaxis review, audit, type map, or split, or which documentation type a section is.
allowed-tools: Read
routing:
  category: content-creation
  triggers:
    - "tutorial or how-to"
    - "mixed documentation"
    - "doc mixes steps and explanation"
    - "mixing procedural and conceptual content"
    - "which documentation quadrant"
    - "diataxis review"
---

# Diátaxis

Diátaxis sorts documentation by what the reader needs at that moment. A section that serves two needs serves neither well: the reader who is doing a task has to wade through why it works, and the reader looking up a fact finds advice. This skill types each section and moves out the passages that belong to another type. It does not rewrite them.

## Two jobs

**Review (default).** The user shares text and asks which type it is, or for a review, an audit, or a type map, or asks you not to change the text. Change nothing, and return no revised version of the text, not even as a suggestion. Report in the review format below. A request not to change the text overrides every rewrite trigger.

**Rewrite.** The user asks you to split, separate, or restructure the text by type. Split it in place (below), return the whole text, then list each move.

If no section has a seam, say so and name each section's type; in a rewrite, also return the text unchanged.

**Use only the facts you were given.** Do not add a fact, name, number, date, owner, source, or claim that is not in the input or supplied by the user. When a rule calls for a detail the input lacks, write `[needs: <detail>]` in its place, for example `[needs: owner]` or `[needs: source for "Eight of twelve labs have the new analysers"]`, and list every gap under **Gaps** at the end of your response. Leave any `[needs: …]` already in the input where it is.

This covers headings and link lines too: build them from the input's own words. A `[needs: …]` inside a passage that moves goes with the passage (see "Split in place"). That is the one case where a marker changes section.

**Leave verbatim text as written.** Quotations, code and field names, UI labels, and the official names of forms, programs, and laws stay exactly as they are.

## The types

Ask two questions of each section and each passage. Does it tell the reader what to do (action), or state what is so (cognition)? Does it serve someone learning (study), or someone doing their job (work)?

| | Study | Work |
|---|---|---|
| **Action** | **Tutorial**: a lesson with practice steps | **How-to**: steps or advice for a real task |
| **Cognition** | **Explanation**: reasons, history, trade-offs | **Reference**: facts and rules to look up |

- Advice is How-to. A sentence that tells someone what to do, as a command or with "should" or "we recommend", is action even when it has no steps. A recommendation addressed to a third party in a report and stated with its reasons is part of the argument: it is Explanation and stays where it is. How-to is for instructions to the reader.
- A rule stated as a fact (a policy, standard, limit, or definition) is Reference, even when it says "must": the reader looks it up. An obligation placed on a named party is such a rule.
- A sentence that says what the reader sees or has after a step is part of that step, and takes that step's type.
- **Record** is not a Diátaxis type. Tag a register, log, approval table, or status tracker that records what was decided, approved, changed, or reported as Record. Never split or move it, and never call its rationale a seam.
- A summary (executive summary, key messages, conclusion) stays as written, reasons and all. Tag it by its opening sentence and mark it "summary, stays put". Argument order belongs to `pyramid-editor`.

## Seams

A section's type is the type its heading and its opening sentence or table serve. A seam is a whole sentence, run of sentences, list, or table of another type inside it. A clause is not a seam: a sentence takes the type of its main clause, so a reason inside a step stays. One exception: a sentence outside a step that states a fact with its reason or its result ("because", "so", "which is why") is Explanation, whichever clause holds the fact, because the reader gets a reason and not a fact to look up. A link line is not a seam.

Every seam moves, however short. A section of one sentence is fine.

## Split in place

For each seam, in document order:

1. Move the passage word for word. Do not reword it, turn it into steps, or join or split its sentences, even when it reads less smoothly on its own: its heading and link carry the context. A `[needs: …]` inside the passage travels with it and keeps its position in the passage. A marker that directly follows the passage's last sentence, in the same paragraph, is inside the passage.
2. If the document already has a section of the passage's type on the same topic, put the passage at the end of that section. Otherwise give it a new section directly after the one it left, at the same heading level, titled from the input's own words, preferring the passage's or that section's: "How to <task>", "About <topic>", "<topic> reference", or "Lesson: <task>".
3. In the passage's place, write one link line that names the target heading: `Why: see "<heading>".` for Explanation, `Steps: see "<heading>".` for How-to, `Details: see "<heading>".` for Reference, or `Lesson: see "<heading>".` for Tutorial. Put it exactly where the passage was, even between numbered steps.

Change nothing else: no new sentences, no edits to the text that stays or to the target section's own text, and no reordering of sections.

Never create, propose, or offer a section for a type the content does not have, even when the user asks for all four types. Say that a type's section exists only when there is content of that type to put in it.

## Output format

```
**Type map**
- <heading>: <Type>
- <heading>: <Type>, with <Type> seam
- <heading>: Record
- <heading>: <Type>, summary, stays put

**Seams**
[Seam] "<quoted span>" is <Type> inside <Type> → move to <new or existing "heading">, leave `<link line>`

**Priority**
1. Up to three splits: seams inside a How-to or Tutorial first, in document order, then the rest in document order

**Gaps**
- [needs: …], one per line; leave the heading out when there are none
```

That is the review. A rewrite returns the whole text after the splits, then **What moved**, one line per move (`"<opening words…>" (<Type>) from "<source heading>" to "<target heading>"`), then **Gaps**. Quote a long span by its first and last words joined with "…".

## Example

**Input** (review requested):

> ## Issue a warehouse radio
>
> Issue one radio to each team lead at the start of the shift.
>
> - Channel 1: yard operations
> - Channel 2: first aid
> - Channel 3: transport
>
> 1. Sign the radio out in the equipment log.
> 2. Set it to the channel for the team lead's team.
> 3. Test it with the control room before the team lead leaves the desk.

**Output:**

> **Type map**
> - Issue a warehouse radio: How-to, with Reference seam
>
> **Seams**
> [Seam] "Channel 1: yard operations … Channel 3: transport" is Reference inside How-to → move to new "Radio channel reference", leave `Details: see "Radio channel reference".`
>
> **Priority**
> 1. The Reference list in "Issue a warehouse radio"

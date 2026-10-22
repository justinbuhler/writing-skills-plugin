---
name: writing-workflow
description: Use when drafting a full document, white paper, memo, or structured argument from a brief, or taking an existing draft through a full cleanup before delivery. Sequences scqa-framework or scr-narrative, pyramid-editor, recommendations-and-actions, plain-language or ste100-writer, optional humanizer and no-ai-slop, then document-qa. Each step's output feeds the next.
allowed-tools: Read
---

# Writing Workflow

Five steps (plus two optional) applied in sequence. Each step's output is the next step's input. Run all steps in the same session so context carries through.

This rule binds every step, including each sub-skill the workflow loads:

> **Use only the facts you were given.** Do not add a fact, name, number, date, owner, source, or claim that is not in the input or supplied by the user. When a rule calls for a detail the input lacks, write `[needs: <detail>]` in its place, for example `[needs: owner]` or `[needs: source for "Eight of twelve warehouses use the new scanners"]`, and list every gap under **Gaps** at the end of your response. Leave any `[needs: …]` already in the input where it is.

A `[needs: …]` marker written by any step passes untouched through every later step. No later step fills, rewords, or drops it; only the user can, by supplying the detail. Step 5 reports every marker still open.

## How each step runs

The workflow says which sub-skill to load, which of its jobs to run, and what to pass. The sub-skill's `SKILL.md` owns its rules; do not substitute a summary of them.

- **Before Step 1**, settle the document type, audience, and purpose, from the input or with one question to the user. A type that fits neither Step 4 list is not unclear: it takes the Step 4 default without a question. Pass all three to every sub-skill so none re-asks.
- **Input.** If the user supplied a draft, every step works on that draft and keeps the author's content unless a sub-skill rule requires the change. If the user supplied only a brief, Step 2 writes the body prose.
- **Handoff.** From Step 2 on, run each sub-skill in its rewriting job (named at each step). Return the full document in the form the step received it (prose stays prose, an outline stays an outline) with the changes in place, then the sub-skill's What changed list. `humanizer` has no such list when another task calls it, so in Step 4.5 the What changed list comes from the `plain-language` re-run that follows `humanizer`, covering the passages it touched. A sub-skill's standalone output shape (a findings list, a table, changed sections only) is not a handoff: the next step needs the whole document.
- **Step 1 is the exception.** It sets the opening and the governing thought, not the whole document. It returns its sub-skill's output, as 1A and 1B each say. With a draft, a new opening replaces only the draft's opening, and Step 2 receives the full draft with that opening in place. From a brief, Step 2 receives the Step 1 output and the brief.
- **Structure is set by Steps 1 and 2.** The Step 1 opening and the answer-first order from Step 2 are deliberate. No later step moves the opening, the governing thought, or the recommendation. Tell each later sub-skill this when you load it.
- **Findings only.** If the user wants findings and no rewrite, run each applicable sub-skill in its review job on the user's document as given, and return the findings grouped by step. Nothing is chained.

## Sequence

```
1. narrative framing            →  scqa-framework  (opening hook only — most documents)
                                   scr-narrative   (SCR spine — long strategic documents)
2. pyramid-editor               →  body structure and logical flow
3. recommendations-and-actions  →  recommendations, decisions, actions
                                   (skip if document has none)
4. language review              →  plain-language  (reports, memos, policy, stakeholder comms)
                                   ste100-writer   (technical procedures, manuals, work instructions)
4.5 humanizer (optional)        →  remove AI writing patterns
4.6 no-ai-slop (optional)       →  sharpen voice, cut editorial slop (any draft that feels flat)
5. document-qa                  →  final pre-delivery quality gate
```

**Procedure route.** When the document is a technical procedure, maintenance manual, work instruction, or safety notice, run Step 4B and Step 5 only. Steps 1–3 build an argument, and a procedure has none; its numbered steps are instructions, not action items.

**STE text is final at Step 4.** Steps 4.5 and 4.6 never run on text that Step 4B wrote, on the procedure route or in a mixed document. In a mixed document they run on the 4A sections only and pass the 4B sections through unchanged.

**Step 1 fork — scqa-framework vs. scr-narrative:**
- Use `scqa-framework` when only the opening needs narrative tension. The SCQA Answer (under SCQ, the governing thought for body) becomes Level 1 of the pyramid.
- Use `scr-narrative` when the full document needs a narrative spine — a long white paper, board paper, or strategic recommendation where S→C→R must hold across every section, not just the introduction. `scr-narrative` writes the short SCR block; Step 2 carries it through the body, because every pillar must support the Resolution. The SCR Resolution becomes Level 1 of the pyramid.

**If you are not sure which language skill to use at Step 4:** default to `plain-language`. Use `ste100-writer` only when the document is a technical procedure, maintenance manual, work instruction, safety notice, or any content that must be read accurately by non-native English speakers or processed by machine translation.

---

### Step 1 — narrative framing (fork: choose one)

#### 1A — scqa-framework (most documents)

Use when only the opening needs narrative tension — the document body is organized as a pyramid and the narrative hook is confined to the introduction.

Load the `scqa-framework` skill and run its Build job on the user's topic, audience, and supplied material; a figure or fact the material lacks becomes `[needs: …]`. With a draft, build from the draft's own opening and content, and replace only the opening. The Answer (under SCQ, the governing thought for body) becomes Level 1 of the pyramid at Step 2.

Deliver: what `scqa-framework` returns when this workflow calls it: the labeled block, then the prose opening. With a draft, also the full draft with that opening in place of its own (the Step 1 exception under How each step runs).

#### 1B — scr-narrative (long strategic documents)

Use when the full document needs a narrative spine — a long white paper, board paper, or strategic recommendation where the S→C→R logic must carry through every major section, not just the introduction. The SCR framework is tighter than SCQA (three elements vs. four) and is calibrated for documents where the audience must be convinced, not just informed.

Load the `scr-narrative` skill. From a brief, run its Build job; from a draft, run its Critique job on the draft. A figure or fact the material lacks becomes `[needs: …]`. The Resolution becomes Level 1 of the pyramid at Step 2.

With a draft, replace only the opening. If the Critique gives a corrected SCR, write it as the draft's opening in prose, in place of the draft's own opening. If it finds **SCR passes**, the draft's opening stays as it is, and the Resolution sentence the Critique quotes becomes Level 1.

Deliver: what `scr-narrative` returns (the labeled SCR block with its diagnostics, or from a draft its findings and the corrected block, or **SCR passes**). With a draft, also the full draft with its opening as set above. Its invitation to refine does not stop the run: go on to Step 2 unless a trigger under When to pause between steps applies.

**When unsure:** default to `scqa-framework` (1A). Use `scr-narrative` only when the document is long enough that the narrative logic needs to hold across multiple sections — not just the opening paragraphs.

---

### Step 2 — pyramid-editor: body structure

Load the `pyramid-editor` skill and run its Rewrite job, with the Step 1 Answer (or Resolution) as the governing thought. Pass the draft, or the brief's material when there is no draft.

Deliver: the full document, passing `pyramid-editor`'s blink test. From a brief, write the body prose from the pyramid outline, using only the brief's facts.

---

### Step 3 — recommendations-and-actions: recommendation quality

**Skip this step** if the document contains no recommendations, decisions required, or action items (e.g., a purely analytical briefing or a narrative report). Findings alone do not trigger it.

Load the `recommendations-and-actions` skill and run its Rewrite job on the full document from Step 2.

Deliver: the full document with every recommendation, decision, and action rewritten in place, owners from the draft or `[needs: owner]`.

---

### Step 4 — language review (fork: choose one)

Apply one language skill based on document type. Do not apply both, except in a document whose sections differ in type: 4B for procedure sections, 4A for the rest.

#### 4A — plain-language (reports, memos, policy, stakeholder communications)

Load the `plain-language` skill and run its Rewrite job on the full document. Tell it two things. The Step 1 opening stays where it is: its Answer already puts the bottom line up front. Owners named in the document stay named and are not replaced with "we". In a mixed document, pass it the sections that are not procedures.

Deliver: the full document with plain-language violations resolved.

#### 4B — ste100-writer (technical procedures, manuals, work instructions, safety notices)

Load the `ste100-writer` skill and run its Rewrite job, as its `SKILL.md` directs. Give it the command to show the changes, so that it makes its table of initial text and new text. In a mixed document, pass it the procedure sections only.

Deliver: the full document with the procedure text in STE, then `ste100-writer`'s change table, which serves as its What changed list.

### Step 4.5 — humanizer: remove AI writing patterns (optional)

**When to use:** Judge the text reaching this step, not who wrote the original. Apply this step when that text shows the patterns `humanizer` catalogues. An AI-drafted source, or a document Steps 1–3 wrote from a brief, usually does.

**Skip this step** if the text shows none of those patterns, or on the procedure route. In a mixed document, judge and run it on the 4A sections only.

Load the `humanizer` skill and run its rewrite on the full draft from Step 4, or on its 4A sections in a mixed document. Then run `plain-language` (4A) again on the passages it changed, so the language rules have the last word. This step never touches STE text, so 4A is always the skill to re-run.

Deliver: the full document as `humanizer` returns it when embedded (final text only, no What changed list), with the `plain-language` re-run's What changed list after it. The draft reads as the writer, not a chatbot.

---

### Step 4.6 — no-ai-slop: sharpen voice and remove editorial slop (optional)

**When to use:** Apply this step when the draft feels flat, generic, or over-polished — even if it was human-authored. Use after Step 4.5 if both steps apply, or on its own when the draft has a voice problem rather than an AI-pattern problem.

**Skip this step** if the draft already reads with a clear, natural human voice and the tone is right for the audience, or on the procedure route. In a mixed document, judge and run it on the 4A sections only.

Load the `no-ai-slop` skill and run its Edit job on the full draft from the previous step, or on its 4A sections in a mixed document. Then run `plain-language` (4A) again on the passages it changed.

Deliver: the full document as `no-ai-slop` returns it, with its What changed list, then the What changed list from this step's `plain-language` re-run. The draft now sounds like the writer, not polished consulting prose.

---

### Step 5 — `document-qa`: final pre-delivery gate

Load the `document-qa` skill and run its Fix job on the complete document, applying its QA areas as written. Tell it the document type and that the answer-first order is deliberate: the governing thought and recommendation lead, and the sequence check applies within the body.

Deliver: the Fix job's output with one override from the handoff rule: the full revised document with the corrected sections in place, not the corrected sections alone. Then its What changed summary by QA area, then **Gaps**. As `document-qa` directs for a fix, every `[needs: …]` marker still in the document is listed under **Gaps**, and those markers are the author's punch list; none is resolved by inventing the missing detail. A punch list in tier order belongs to the Review job, which this step does not run.

---

## When to pause between steps

Pause and show the user the output after each step when:
- The document is long (over 10 pages, about 5,000 words) or the structure is complex
- The user asked for review checkpoints
- The step produces a significant structural change the user should approve before continuing

Otherwise run all steps without pausing, as for a short memo (under 3 pages) where the answer is already clear and the audience is known.

---

## Quick reference

| Step | Skill | Input | Output | Skip when |
|---|---|---|---|---|
| 1A | scqa-framework | Topic + audience + supplied facts, or the draft | Opening + governing thought (with a draft, the draft with only its opening replaced) | Needs full narrative spine → use 1B; procedure route |
| 1B | scr-narrative | Topic + audience + supplied facts, or the draft | SCR block + governing thought (Resolution) (with a draft, the draft with only its opening replaced, if the SCR failed) | Opening hook is sufficient → use 1A; procedure route |
| 2 | pyramid-editor | Governing thought (from 1A or 1B) + draft or brief | Full structured document | Procedure route |
| 3 | recommendations-and-actions | Full document | Owned, traceable recommendations in place | No recommendations, decisions, or actions; procedure route |
| 4A | plain-language | Full document | Reader-ready language | Document is a technical procedure → use 4B instead |
| 4B | ste100-writer | Full document (procedure sections only, if mixed) | STE100-compliant text + change table | Document is a report/memo/policy → use 4A instead |
| 4.5 | humanizer | Draft from Step 4 (4A sections only, if mixed) | Draft without AI writing patterns | Text shows no humanizer patterns; procedure route; STE sections |
| 4.6 | no-ai-slop | Draft from Step 4 or 4.5 (4A sections only, if mixed) | Draft with sharpened voice and editorial slop removed | Draft already has a clear, natural human voice; procedure route; STE sections |
| 5 | `document-qa` | Full document | Final document + What changed + Gaps (open `[needs: …]` markers, the author's punch list) | Never |

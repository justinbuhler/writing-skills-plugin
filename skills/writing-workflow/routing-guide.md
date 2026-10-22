# Writing Skills Routing Guide

Use this guide to pick the right skill for a writing task.

## By task

| Task | Skill |
|---|---|
| Draft a full document from a brief or outline, or take an existing draft through every step before delivery | `writing-workflow` |
| Write an opening hook | `scqa-framework` |
| Restructure a draft for logical flow | `pyramid-editor` |
| Audit findings, recommendations, decisions, actions | `recommendations-and-actions` |
| Edit for plain English (reports, memos, stakeholder communications) | `plain-language` |
| Edit for controlled language (procedures, manuals) | `ste100-writer` |
| Remove AI writing patterns from a draft | `humanizer` |
| Sharpen voice and remove editorial slop from any draft | `no-ai-slop` |
| Final quality gate before delivery | `document-qa` |
| Full narrative spine for a long document | `scr-narrative` |

## By document type

| Document type | Recommended sequence |
|---|---|
| Executive memo or board paper where only the opening needs narrative tension | `writing-workflow` with `scqa-framework` at Step 1 |
| Long white paper, board paper, or strategic recommendation that must convince across every section | `writing-workflow` with `scr-narrative` at Step 1 |
| Technical procedure or maintenance manual | `writing-workflow` procedure route: `ste100-writer` (Step 4B), then `document-qa` |
| Audit or risk report | `writing-workflow` (Steps 1–5) |
| Policy or regulation | `writing-workflow` with `plain-language` at Step 4 |
| Slide deck | `pyramid-editor` then `plain-language` (skip `scqa-framework` unless adding speaker notes) |
| Short email or one-pager | `plain-language` or `humanizer` alone |
| Text showing the AI writing patterns `humanizer` catalogues | `humanizer` first, then `plain-language` (the language rules have the last word, as in `writing-workflow`) |
| Human-authored text that feels flat or generic | `no-ai-slop` alone |
| Text still flat after `humanizer` removed its AI patterns | `humanizer` then `no-ai-slop` |

## Step 4 language fork decision

Apply one language review skill at Step 4 of `writing-workflow`. Do not apply both, except in a document whose sections differ in type: `ste100-writer` for procedure sections, `plain-language` for the rest.

Is the document a technical procedure, maintenance manual, work instruction, safety notice, or content that must be easy for non-native speakers or machine translation?

- Yes: use `ste100-writer` (ASD-STE100 Issue 9)
- No: use `plain-language`

Default to `plain-language` when unsure.

STE text is final at Step 4. `humanizer` and `no-ai-slop` never run on it: they are skipped on the procedure route, and in a mixed document they run on the `plain-language` sections only.

## When to use humanizer vs. no-ai-slop

Both skills remove AI-sounding patterns. Choose based on what the text shows, not who wrote it.

| Signal | Use |
|---|---|
| Text reaching Step 4.5 shows the patterns `humanizer` catalogues | `humanizer` (Step 4.5) |
| Text has filler phrases ("in conclusion", "it is important to note", "at the end of the day") | `no-ai-slop` |
| Writing sounds smooth but completely voiceless | `no-ai-slop`; run `humanizer` first only if the text also shows its patterns |
| Human-authored draft that reads as flat, generic consulting prose | `no-ai-slop` (Step 4.6) |
| Draft needs voice sharpened and editorial slop removed | `no-ai-slop` |
| Want to audit patterns without rewriting | `no-ai-slop` (Detect job) |

**`humanizer`** is exhaustive — 25 specific AI patterns drawn from Wikipedia's "Signs of AI writing." Use it for high-AI-density drafts.

**`no-ai-slop`** is sharper — stronger voice preservation, editorial judgment, and a Detect job. Use it for any draft where the writing feels flat, even human-authored ones.

Skip both when the draft already has a clear, natural voice.

## scqa-framework compared with scr-narrative

| When | Use |
|---|---|
| Only the opening needs narrative tension | `scqa-framework` |
| The whole document needs a narrative spine from start to finish | `scr-narrative` |

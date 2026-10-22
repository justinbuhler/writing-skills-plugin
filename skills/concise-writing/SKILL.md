---
name: concise-writing
description: Detect and correct wordy, verbose, padded, or inflated writing. Diagnoses the specific flaw (pleonasm, circumlocution, prolixity, sesquipedalianism, legalese, bureauspeak, purple prose, logorrhea/word salad) and rewrites for concision without losing meaning. Use this whenever the user asks to tighten, trim, shorten, simplify, de-jargon, "make it punchier," cut fluff, or reduce the word count of any prose — emails, reports, essays, documentation, marketing copy, legal or policy text, academic writing — or asks why a passage feels bloated, rambling, or hard to read. Also use when reviewing or editing a draft where verbosity is one of the problems, even if the user didn't name it.
allowed-tools: Read
routing:
  category: content-creation
  triggers:
    - "tighten this"
    - "cut the word count"
    - "too wordy"
    - "trim this draft"
    - "remove padding"
---

# Concise Writing: Detect and Correct Verbosity

Wordiness isn't one problem — it's several, and each has a different fix. "Burning fire" (pleonasm) is cut by deleting a word; "at this point in time" (circumlocution) is cut by substituting a shorter phrase; a 60-word legalese sentence is cut by restructuring; purple prose is cut by removing ornament, not words per se. Naming the flaw tells you which operation to apply, so diagnose before rewriting.

## Two jobs

**Rewrite (default).** The user shares text to tighten, trim, shorten, simplify, de-jargon, cut, or make punchier, asks you to reduce its word count, or asks why it feels bloated; or you are editing a draft where verbosity is one of the problems. Follow the workflow below and report in the output format.

**Review.** The user asks for a review or an audit, or asks you not to change the text. Change nothing. For each distinct verbose span, quote it, name its category, and give the fix; one line can cover every repeat of the same phrase (×N). A repeated noun that names the same subject is not a verbose span, and a review does not list a finding you would call minor. State a word count or a saving only when you have counted the words. Then give a priority list of up to three changes, with **Gaps** last. A request not to change the text overrides every rewrite trigger.

If nothing is verbose, say so and return the text unchanged.

**Use only the facts you were given.** Do not add a fact, name, number, date, owner, source, or claim that is not in the input or supplied by the user. When a rule calls for a detail the input lacks, write `[needs: <detail>]` in its place, for example `[needs: owner]` or `[needs: source for "Eight of twelve schools have new boilers"]`, and list every gap under **Gaps** at the end of your response. Leave any `[needs: …]` already in the input where it is.

This applies to the suggested fix in every review finding, not only to a full rewrite.

**Leave verbatim text as written.** Quotations, code and field names, UI labels, and the official names of forms, programs, and laws stay exactly as they are, even when they contain a pattern from the taxonomy.

## Workflow

1. **Read the whole passage once for meaning.** Note what the writer is actually trying to say and to whom. Concision serves the reader; a cut that drops meaning or tone the audience needs is a failure, not a win.
2. **Diagnose.** Mark each verbose span and label it with the category from the taxonomy below. A span that fits two categories may take either label: a light verb with a noun ("making a determination", "conducting a review") is both circumlocution and bureauspeak, and the fix is the same. Most passages have two or three dominant patterns; identify them rather than listing every instance.
3. **Rewrite.** Apply the fix pattern for each category. Preserve the author's voice, register, and all substantive content. Don't flatten deliberate emphasis or a legitimately technical term.
4. **Report.** Give the rewrite first, then a short diagnosis (what the dominant patterns were, with one or two examples each), then the word-count change. Keep the diagnosis proportional — a one-paragraph email gets two sentences of diagnosis, not a lecture.

If the user only asked for a rewrite, lead with it and keep the diagnosis to a line. If they asked *why* their writing feels bloated, lead with the diagnosis.

## Taxonomy (quick reference)

| Category | What it looks like | Fix |
|---|---|---|
| **Pleonasm** | Redundant pairs: "advance reservations," "end result," "past history," "each and every" | Delete the redundant word |
| **Circumlocution / periphrasis** | Talking around the point: "at this point in time," "in the event that," "has the ability to" | Substitute the direct word: now, if, can |
| **Prolixity** | Tedious overall length — too many sentences, qualifications, and restatements | Cut whole sentences; keep one statement of each idea |
| **Sesquipedalianism** | Inflated vocabulary: "utilize," "ameliorate," "endeavor," "facilitate" | Replace with the plain word: use, improve, try, help |
| **Logorrhea / word salad** | Flow of words with little propositional content; filler that reads fluently but says nothing | Identify the actual claim; rewrite from scratch around it. If the text states no claim, write `[needs: the claim and its evidence]` and tell the user the passage needs content, not editing |
| **Legalese** | Doublets ("null and void"), nested conditions, "said," "hereinafter," "pursuant to" | One term per concept, but a requirement that says both when something must happen and what depends on it is two requirements, not a doublet, and both stay; split conditions into separate sentences, and make each split-off condition restate what it is a condition of; replace a clause that only gives a defined term its name with the term itself; keep the clause that names the source of a rule ("pursuant to X" becomes "under X"), do not delete it |
| **Bureauspeak / officialese** | Passive voice hiding agents, nominalizations ("the implementation of"), empty corporate filler ("going forward," "leverage synergies") | In a passive clause, make the actor the subject when the text names who did or will do the action (the input may name that actor in another sentence); a party named only as owner or as accountable is not the actor. If the text names none, write `[needs: actor]` when the actor matters and the text does not say the actor is unknown; otherwise the passive may stay (the text says the actor is unknown, or the actor is unimportant or the law itself). A passive inside a reported decision or plan stays unless the text names who will carry it out. Leave a participle that describes a noun ("forms received last week"). Turn nouns back into verbs; delete filler |
| **Purple prose** | Stacked adjectives and adverbs, elaborate metaphors, ornament for its own sake | Keep one strong image; cut modifiers that don't change meaning |

For fuller lists of trigger phrases, substitutions, and worked examples per category, read `references/taxonomy.md`.

## Judgment calls

- **Don't over-correct.** A target of "shorter" is not "shortest possible." Rhythm, transitions, and occasional repetition for emphasis are legitimate. A rewrite that reads like a telegram has failed.
- **Register matters.** Legal and regulatory text sometimes needs a doublet or defined term for precision; academic writing needs hedges that signal the strength of evidence. Cut what's empty, not what's doing work: "may suggest" is a claim about certainty, "it is perhaps possible that it may" is three hedges doing the job of one. When unsure, keep it and flag it.
- **Technical terms are not sesquipedalianism.** "Idempotent" is the right word in an API doc. Only replace jargon when a plain word carries the same meaning for the intended reader.
- **Controlled language is out of scope.** Do not apply this skill to text written to ASD-STE100 or another controlled vocabulary: return it unchanged and point the user to `ste100-writer`, whose approved words these substitution tables would undo.
- **A vague reason is not an empty one.** Keep a phrase that gives a reason or names a checkable property, however loosely: a cause ("for security reasons"), a tier or grade ("a premium model"), a date or recency, or a quantity a reader could confirm. When the sentence promises or requires the thing the phrase describes without saying which, add `[needs: …]` after it, never in its place; a reason needs none. Praise that names no such property ("world-class", "game-changing") is not a claim: cut it under the next rule or, for a whole sentence, the logorrhea fix.
- **Never invent specifics.** When cutting an empty superlative leaves a gap ("the finest fabrics" with no fabric named), write `[needs: material]` rather than guessing, and list it under **Gaps**. Fabricated details are worse than fluff.
- **Cap the diagnosis.** In a rewrite, report the three most consequential patterns at most, each with one or two examples. For long documents, note "also present, less often: ..." in a single line rather than adding bullets.
- **Ask when the audience is unclear** and the right level of formality depends on it — but make a best-guess rewrite first rather than stalling.

## Output format

```
## Rewrite
[revised text]

## What was happening
- **[Category]** — one-line explanation; e.g. "in order to" → "to" (×4)
- **[Category]** — ...

Word count: 312 → 178 (−43%)

**Gaps**
- [needs: …], one per line; leave the heading out when there are none
```

For a review, give one line per finding, `[Category] "quoted span" → fix`, then a **Priority** list of up to three changes, then **Gaps**. For an item you keep and flag, write `→ keep; flag: <why>` as its fix. In a rewrite, list kept-and-flagged items under **What was happening**.

Drop the headers for very short passages (a sentence or two) and just show before/after with a one-line note; keep **Gaps** when there is a gap.

## Example

**Input:** "At this point in time, we are in the process of conducting a review of each and every one of the proposals that were submitted to us, with a view to making a determination as to which proposal is the most optimal."

**Output:** "We are reviewing every submitted proposal to decide which is best."

Diagnosis: circumlocution ("at this point in time," "in the process of," "with a view to making a determination as to"), pleonasm ("each and every," "most optimal"), bureauspeak nominalization ("conducting a review" → "reviewing"). 42 words → 11.

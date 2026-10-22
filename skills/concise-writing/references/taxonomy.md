# Verbosity Taxonomy: Detection Cues and Fixes

Read this when a passage has heavy or mixed verbosity and the quick table in SKILL.md isn't enough to work from.

## 1. Pleonasm (redundancy)

Words that repeat meaning already present. Grammatical and fluent, so easy to miss.

**Common pairs to cut:**
advance planning · added bonus · basic fundamentals · close proximity · completely finished · consensus of opinion · each and every · end result · exact same · false pretense · final outcome · free gift · future plans · join together · merge together · new innovation · past history · personal opinion · plan ahead · revert back · still remains · sum total · true fact · unexpected surprise · very unique · most optimal

**Fix:** delete the redundant modifier. "End result" → "result."

**Watch for:** intensifying pleonasm that *is* idiomatic emphasis ("I saw it with my own eyes"). Keep if deliberate and the register is informal.

## 2. Circumlocution / periphrasis

Multi-word phrases standing in for a single word. The writer is "going around" the direct term.

**Substitution table:**

| Wordy | Direct |
|---|---|
| at this point in time | now |
| at the present moment | now |
| in the event that | if |
| in the near future | soon |
| due to the fact that | because |
| in light of the fact that | because |
| for the purpose of | to / for |
| in order to | to |
| with regard to / in relation to | about |
| has the ability to / is able to | can |
| is in a position to | can |
| make a decision | decide |
| conduct an investigation | investigate |
| reach an agreement | agree |
| give consideration to | consider |
| a large number of | many |
| the majority of | most |
| prior to | before |
| subsequent to | after |
| in spite of the fact that | although |
| it is important to note that | (delete) |
| it should be pointed out that | (delete) |
| there is / there are ... that | (restructure around the real subject) |

**Fix:** substitute. Then reread — substituted sentences often reveal a second layer of padding.

## 3. Prolixity (overall tedious length)

Not a phrase-level problem but a document-level one: restated ideas, excessive qualification, throat-clearing introductions, summaries that repeat the body.

**Cues:**
- A point made, then "in other words," then made again
- Paragraphs that open by announcing what they will say
- Three examples where one would convince
- Hedges stacked: "it seems that it may perhaps be possible that"
- Conclusion that restates every section

**Fix:** work at sentence and paragraph level. Keep the clearest statement of each idea; delete the others. Cut announcing sentences ("In this section I will discuss..."). Collapse hedges to one. When the repeats sit in different sections, keep the defining statement, usually the first or the one other sections cite, point the other copies to it, and check every cross-reference to a copy you cut. An executive summary or conclusion that restates the body's key points is doing its job; leave it. Apply this only to body sections and appendices. If a copy adds anything, move the addition into the kept statement, then replace the copy with a pointer.

## 4. Sesquipedalianism (inflated vocabulary)

Long or Latinate words chosen for weight rather than precision.

**Substitution table:**

| Inflated | Plain |
|---|---|
| utilize | use |
| facilitate | help / enable |
| ameliorate | improve |
| endeavor | try |
| commence / initiate | start / begin |
| terminate | end |
| implement | do / carry out / set up |
| demonstrate | show |
| ascertain | find out |
| sufficient | enough |
| numerous | many |
| subsequently | later / then |
| additionally | also |
| methodology | method |
| functionality | features / function |
| optimal | best |
| expeditiously | quickly |
| remuneration | pay |
| in excess of | more than |

**Fix:** replace unless the long word carries a distinction the short one lacks. "Methodology" genuinely means the study of methods in some academic contexts — but almost never in a business memo.

**Not sesquipedalianism:** domain terms the audience expects (idempotent, fiduciary, heteroscedasticity). Don't dumb down technical writing for experts.

## 5. Logorrhea / word salad

Text that flows but has nearly no propositional content. Often produced under pressure to hit a length, or by stringing buzzwords.

**Cues:**
- You can't state the paragraph's claim in one sentence after reading it
- Abstract nouns chained with "of": "the optimization of the alignment of the framework of..."
- Sentences that would be equally true of any topic
- Heavy use of "various," "aspects," "factors," "elements," "considerations" without naming them

**Fix:** don't edit — reconstruct. Ask: what is the one thing this is trying to say? If the text states it, write that sentence. Then add only the specifics (names, numbers, concrete nouns) the text gives that support it. If there are no specifics, say so to the user — the passage may need research, not editing. If the text states no claim at all, do not write one: mark `[needs: the claim and its evidence]` and tell the user the passage needs content, not editing.

## 6. Legalese

Dense legal register leaking into text that doesn't need it, or genuine legal text that is more convoluted than precision requires.

**Cues:**
- Synonym doublets and triplets: "null and void," "cease and desist," "give, devise, and bequeath," "any and all"
- Archaic deictics: hereinafter, aforesaid, said (as a determiner), herewith, thereof
- "pursuant to," "notwithstanding," "in accordance with"
- Sentences over 50 words with nested conditions and multiple "provided that" clauses
- Passive constructions concealing who is obligated

**Fix:** one term per concept (keep a doublet only if each word has distinct legal force and the reader is a lawyer). A requirement that says both when something must happen and what depends on it is two requirements, not a doublet: keep both. Replace archaic words with "this," "that," "under." Keep the clause that names the source of a rule ("pursuant to X" becomes "under X"); do not delete it. Split long conditional sentences; one condition per sentence. A condition split off into its own sentence restates what it is a condition of. Replace a clause that only gives a defined term its name with the term itself. Name the party who must act, taken from the text, or write `[needs: party]`.

**Caution:** in a real contract, defined terms and some doublets are load-bearing. Flag rather than cut when the text is actually operative law.

## 7. Bureauspeak / officialese

Administrative prose that hides agency and action.

**Cues:**
- Passive voice without an agent: "mistakes were made," "it has been decided"
- Nominalizations: "the implementation of," "the provision of," "the utilization of," "a review was undertaken"
- Empty connectives and filler: "going forward," "at the end of the day," "in terms of," "as per," "on a daily basis," "leverage," "synergy," "stakeholder alignment," "circle back," "touch base"
- Institutional subject in place of a person: "The department is of the view that"

**Fix:**
- Restore the actor of a passive clause when the text names who did or will do the action: "The plan was approved by the board" → "The board approved the plan." The input may name that actor in another sentence; a party named only as owner or as accountable is not the actor. If the text names no actor, write `[needs: actor]` when the actor matters and the text does not say the actor is unknown ("Mistakes were made" → "[needs: actor] made mistakes"); never supply "we". Otherwise the passive may stay: the text says the actor is unknown, or the actor is unimportant or the law itself ("Penalties are assessed under § 101"). A passive inside a reported decision or plan stays unless the text names who will carry it out. Leave a participle that describes a noun ("forms received last week").
- Un-nominalize: "undertook an assessment of" → "assessed."
- Delete filler outright. "Going forward" almost never changes meaning.
- Replace "on a daily basis" → "daily"; "in terms of X" → usually just "X" or restructure.

## 8. Purple prose

Ornamental literary writing — more adjectives, adverbs, metaphors, and rhythm than the content supports.

**Cues:**
- Two or more adjectives on most nouns
- Adverbs on most verbs, especially -ly on strong verbs ("sprinted quickly")
- Mixed or stacked metaphors in one sentence
- Abstract emotional intensifiers: "utterly," "profoundly," "exquisitely," "breathtakingly"
- Sentences you notice the sound of before the sense

**Fix:** choose. One image per sentence, one modifier per noun unless the second changes meaning. Cut adverbs that merely repeat the verb. Replace adjective-plus-weak-noun with a precise noun only when the noun means exactly what the pair said ("young dog" → "puppy"); otherwise cut the weak modifier ("very large house" → "large house"). Preserve the author's style — this is the category where over-correction does the most damage. The goal is prose with *earned* ornament, not none.

## Mixed diagnoses

Real passages blend categories. Typical combinations:

- **Corporate memo:** bureauspeak + circumlocution + sesquipedalianism
- **Student essay:** prolixity + circumlocution ("it is important to note that")
- **Contract or policy:** legalese + pleonasm (doublets) + prolixity
- **Marketing copy:** purple prose + pleonasm ("free gift," "new innovation")
- **Rushed report:** logorrhea + bureauspeak

Lead the diagnosis with the dominant pattern; mention secondary ones briefly.

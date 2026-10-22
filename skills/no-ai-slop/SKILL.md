---
name: no-ai-slop
description: Edit drafts into sharper, more human writing while preserving the writer's personal voice, or detect AI-slop patterns without rewriting. Use when the user wants a draft clearer, more direct, more opinionated, or less AI-sounding, or asks whether writing reads as AI.
allowed-tools: Read
routing:
  category: content-creation
  triggers:
    - "ai slop"
    - "less AI-sounding"
    - "sharper draft"
    - "does this read as AI"
    - "slop check"
---

# No AI slop

You are a sharp human editor. Preserve the user's point and personal voice while making the writing clearer and more alive. Remove AI patterns without turning distinctive writing into generic polished prose.

## Two jobs

**Edit (default).** The user shares a draft to fix. Make the minimum effective edit with the rules below and return the edited draft plus a What changed section, and a **Gaps** section when the draft carries any `[needs: …]` marker.

**Detect.** The user asks whether a piece is AI slop, or asks to audit, scan, or flag a draft without rewriting. Name each pattern from this skill that appears, quote the phrase and say which sentence holds it, and give the fix in a few words. A pattern is an entry under Words to cut or Patterns to cut; do not report a sentence that only fails an Editing principle, such as the portability test or a result with no figure. When a fix needs a detail the draft lacks, say what the writer must supply; do not supply it. Do not rewrite, score the draft, or guess whether AI wrote it. AI detectors guess. Named patterns are evidence the user can check. Offer to edit the draft after. If no pattern appears, say so, name any near-miss you kept on purpose, and do not offer an edit.

## What to ask for

If the user has not provided a draft, ask them to paste it.

If the audience or format is unclear, ask one question: Who is this for and where will it be published?

If the goal is unclear, ask what the reader should think, feel, or do after reading it.

## Editing principles

- **Preserve the writer's real voice.** First notice the draft's vocabulary, cadence, bluntness, humor, uncertainty, digressions, and level of polish. Keep the traits that feel personal to the writer. Do not make every paragraph equally tidy or rewrite distinctive lines merely for consistency.
- **Make the minimum effective edit.** Fix AI patterns, errors, repetition, and unclear passages. Leave strong human sentences alone. A rough draft with a real voice should still sound like the same person after editing.
- **Lead with the point when the setup adds nothing.** Cut generic throat-clearing. Keep a personal aside, story, or admission when it creates context, tension, or character.
- **Front-load only when it improves clarity.** Put conclusions early when that helps the reader. Do not force every section and paragraph into the same point-detail-background shape.
- **Use only the facts you were given.** Do not add a fact, name, number, date, owner, source, or claim that is not in the input or supplied by the user. When a rule calls for a detail the input lacks, write `[needs: <detail>]` in its place, for example `[needs: owner]` or `[needs: source for "Eight of twelve clinics use the new booking system"]`, and list every gap under **Gaps** at the end of your response. Leave any `[needs: …]` already in the input where it is.
- **Open it up, don't dumb it down.** Keep the substance, nuance, and precision. Strip out only what makes it hard to read: jargon, long sentences, abstract nouns, and tangled structure.
- **Use active voice when the draft names the actor.** "The team shipped it Tuesday" beats "It was shipped Tuesday by the team." Keep a passive when the draft does not say who acted; do not pick an actor. Do not give inanimate things verbs of thought, feeling, or intent ("the data believes," "the report wants"). A tool or system may do what it mechanically does: "The integration cut deploy time" and "The agent reviews the draft" are fine.
- **Make every sentence earn its place.** Cut empty qualifiers and throat-clearing. Keep phrases such as "I think," "maybe," or "to be honest" when they express real uncertainty, self-awareness, or the writer's spoken rhythm.
- **Untangle sentences without flattening the cadence.** Split sentences and paragraphs when they are genuinely hard to follow. Keep longer spoken sentences, fragments, and changes in pace when they are clear and characteristic of the writer.
- **Be concrete and specific.** Prefer the specific detail the draft already has over an abstract summary of it. "The integration improved efficiency: deploy time went from 40 minutes to 4" becomes "The integration cut deploy time from 40 minutes to 4." Names, numbers, dates, mechanisms, and examples beat abstractions. Use the ones the draft gives. When a claimed result has no figure in the draft, keep the claim and write `[needs: figure for <result>]` after it.
- **Use the portability test.** If a sentence could move unchanged to another person, company, country, or product, it is probably filler. Cut it if it is filler, or replace it with a fact, example, mechanism, consequence, or judgment specific to this subject that the draft already gives. Keep it if it is the writer's own point. Structured text named under Patterns to cut is exempt.
- **Always show, don't tell the reader what to think.** Make facts, actions, examples, and consequences carry the emphasis. Cut commentary that labels a point important, surprising, subtle, or obvious instead of demonstrating why. If the surrounding prose already shows the point, trust the reader and delete the commentary.
- **Protect the specific fact.** Don't smooth a useful detail into generic importance. Do not turn "The tool cut review time from 30 minutes to 8" into "The tool significantly improves engineering productivity."
- **Make verbs do the work.** Replace weak verb phrases with direct verbs. "Made a decision" becomes "decided." "Has the ability to" becomes "can."
- **Know the job.** Before structure or word choice, know what the piece is trying to do and who it is for.
- **Preserve useful edge and character.** Keep strong opinions, blunt language, humor, profanity, self-interruptions, and honest admissions when they belong to the writer. Don't replace them with safer or more professional wording.
- **Keep structure unless it's hurting the piece.** Preserve the writer's progression and detours when they carry personality. If you reorganize, say why in the What changed section.

## Words to cut

Banned outright: delve, foster, leverage, utilize, facilitate, empower, streamline, robust, cutting-edge, paradigm shift, game changer, this is huge, this changes everything, tapestry, realm, beacon, multifaceted, meticulous, intricate, paramount, transformative, elevate, embark, supercharge, harness, ever-evolving.

Often-empty adverbs: just, literally, honestly, simply, actually, truly, fundamentally, importantly, crucially, inherently, inevitably. Cut them when they add nothing. Keep them when they carry emphasis, uncertainty, contrast, a time or quantity meaning ("just confirmed" meaning recently, "just 3 of 40" meaning only), or the writer's natural spoken rhythm.

Often-empty phrases: it's worth noting, it's important to note, at the end of the day, when it comes to, at its core, in today's world, in the age of, in the world of, the reality is, the truth is, in terms of, with regard to, in order to, going forward, in this article, let's dive in. Cut them when they delay the point. Keep an occasional phrase when it is part of the writer's recognizable voice and the sentence still earns its place.

Apply these three lists only to the writer's own prose. Leave quotations, code, proper nouns such as product names, and established technical terms (a Kerberos realm, a test harness) as written.

## Patterns to cut

Structured text is exempt from the portability test, robotic rhythm, rhetorical setups, and formatting slop: FAQ question-and-answer pairs, deliberately parallel entries such as status rows, numbered procedures, safety warnings, compliance text, and bold UI labels. Their structure is the content.

**Binary contrasts.** "This is not X. It's Y." / "The question isn't X, it's Y." / "It's not just X but Y." State Y directly. Leave a contrast that carries the writer's own voice in a first-person draft — the voice principles above take precedence. Keep the contrast when the negated item is a real alternative the reader might assume, such as a ruled-out cause or a scope exclusion. The negated item is a real alternative when cutting it removes a fact the reader can check or act on; but when Y only states a value or praise, the contrast rules nothing out even if the negated item is a fact, so cut it. "The question isn't the model. It's the eval." becomes "The eval matters more than the model."

**Throat-clearing openers.** "Here's the thing," "Here's what I mean," "Let me be clear," "I'll be honest," "The uncomfortable truth is." Cut them and state the point. Keep "I'll be honest" when it introduces a genuine admission, as the voice principle above keeps "to be honest."

**Faux-insight setups.** "This is the part most people skip," "What most people get wrong," "Here's what nobody tells you," "The part everyone misses." These flatter the writer as the lone expert. Cut the setup and make the claim stand on its own. "The part everyone misses: distribution is the real moat" becomes "Distribution is the moat."

**Colon reveals.** A teaser phrase that withholds the subject, a colon, then the reveal, in either case: "The detail that makes it work: a separate agent grades it." "The best part: it learns." Rewrite as a plain sentence ("It works because a separate agent grades it"). Use colons for lists, labels, and quotes, not fake drama. Field labels in reports and forms ("Root cause:", "Risk:", "Owner:") are not reveals. Prefer lower case after a colon inside a sentence unless grammar, a proper noun, a title, or code requires otherwise; leave the case after a field label or a signal word as written ("Owner: Finance team", "CAUTION: Hot surface").

**Superficial analysis.** Cut trailing `-ing` clauses that pretend to explain meaning: "highlighting," "underscoring," "reflecting," "showcasing." "The launch adds file search, highlighting the team's commitment to better workflows" becomes "The launch adds file search." State what the feature does for users only when the draft says so.

**Importance puffery.** "Stands as a testament," "marks a pivotal moment," "plays a vital role," "solidifies its position," "underscores its significance." State the fact and let the reader judge whether it matters. "The launch marks a pivotal moment for the company" becomes "The launch is the company's first paid product" — but only when the source says so. If the source gives no such fact, cut the puffery and keep what is left.

**Interpretive metadiscourse.** Cut lines that step outside the subject to tell the reader what to notice, how much weight to give it, or how to interpret the prose: "That last part matters more than it sounds," "The key point is," "As you can see," "This distinction matters," and redundant "In other words." If the point is clear, delete the aside. Otherwise, replace it with support or facts already in the content. Keep a pointer to a table, figure, or section as a plain reference: "As you can see in the chart, X" becomes "The chart shows X."

**Weasel attribution.** "Experts agree," "industry reports suggest," "many argue," "widely regarded as," "studies show." Name the source when the draft or user gives one. A claim that carries a citation or footnote already has its source: leave it as written, and name that source inline only when the user asks. Otherwise remove the weasel phrase, keep the claim and any hedge it carried, and write `[needs: source for "<claim>"]` after it, as the facts rule above requires. A hedge is the doubt in the weasel verb: "suggest" or "argue" stays in the claim as "likely" or "may", and a phrase that claims agreement or proof ("experts agree," "studies show") carries none. Quote the claim in the marker without the hedge. Cut the claim only when the user says to. Never invent a source.

**Fake-strong verbs.** "Serves as," "functions as," "acts as," and similar stand in for "is," "has," or a direct verb. Prefer "is" and "has" when they are clearer. Keep "acts as" or "serves as" when it marks an acting or interim role. "The app serves as a centralized hub for supplier contracts" becomes "The app centralizes supplier contracts." Name the specific things it tracks only when the source lists them.

**Synonym cycling.** If the clear word is right, repeat it. Don't rotate terms for style. "The agent reviews the draft. The assistant scores the piece. The tool suggests fixes" becomes "The agent reviews the draft, scores it, and suggests fixes."

**Negative listing.** "Not a X. Not a Y. A Z." Just say Z. Keep a negation that rules out something the reader might assume, as with binary contrasts.

**Dramatic fragmentation.** Two or more fragments or short beats in a row used for rhythm: "X. And Y. And Z." or "That's it. That's the whole thing." Use complete sentences. A single fragment the writer uses for emphasis stays.

**Robotic rhythm.** Avoid repeated sentence shapes, identical paragraph structures, and stacked punchy fragments. Vary the shape only when it helps the point.

**Rhetorical setups.** "What if I told you...", "Think about it:", "Plot twist:", and self-answered "Question? Answer." pairs. Drop them and make the point.

**Fake-profound kickers.** Cut the final "deep" line when it turns the point into a cute metaphor, aphorism, or mic-drop sentence. Do not rewrite it into a better metaphor. Do not preserve the rhythm. Delete it, then end on the clearest concrete sentence already in the draft. If the ending needs more closure, use a takeaway or next action the draft already states; do not write a new one.

**Summary-recap endings.** A final sentence or paragraph that restates the piece, often opened by "In conclusion," "Ultimately," or "Overall." The opener alone is not the pattern: a closing sentence that adds a figure, date, decision, or action stays. The reader was just there. End on the last concrete point, takeaway, or next action already in the draft instead.

**Formatting slop.** Emoji in headings, bold sprinkled mid-sentence for emphasis, bullet lists where two sentences of prose would read better, and headers over two-sentence sections. Format should follow the content, not decorate it.

**Em dashes.** Not this skill's remit. `humanizer` §8 owns dash policy — it is the single source, and its rule is stricter than a voice-editing pass should apply on its own. Do not add or remove dashes here.

## Workflow

1. Read the full draft before editing.
2. Identify the core point and the voice traits to preserve: vocabulary, cadence, bluntness, humor, uncertainty, digressions. If you cannot identify the core point, ask the user.
3. For a detect request, return the findings report described in Two jobs and stop.
4. For an edit, make the minimum effective changes, then check the edited draft against `eval.md` yourself.
5. If any check fails, fix the draft and run the checks again.
6. Output the full edited draft, a short **What changed** section, and a **Gaps** section if the draft carries any `[needs: …]` marker.

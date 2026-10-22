# No AI slop eval

Use this after the rewrite. Answer each check with pass or fail. If any check fails, fix the draft before returning it.

For detect requests, make sure the response names each pattern found (Words to cut and Patterns to cut only, not editing principles) with a quoted line and a short fix, without rewriting the draft. If none was found, it says so, names any near-miss kept on purpose, and offers no edit.

## Editing principles

1. Does the edit preserve the user's point without adding any fact, name, number, date, owner, source, quote, or claim the draft or user did not supply, with each missing detail a rule calls for written as `[needs: <detail>]`?
2. Does it preserve the writer's distinctive vocabulary, cadence, bluntness, humor, uncertainty, digressions, and level of polish?
3. Does it leave strong human sentences alone instead of rewriting them for consistency or making every paragraph equally tidy?
4. Is the amount of cutting proportional to the actual slop, with no aggressive compression that strips out character?
5. Does the draft lead with what the reader needs while keeping personal setup that adds context, tension, or character?
6. Are points front-loaded where that improves clarity without forcing every unit into the same structure?
7. Do sentences earn their place, with concrete facts, protected details, and direct verbs where the draft supports them?
8. Was each sentence that fails the portability test judged: cut if it is filler, made specific with detail the draft already gives, or kept if it is the writer's point? Structured text SKILL.md exempts (FAQs, parallel entries, procedures, warnings, compliance text, UI labels) passes as written.
9. Does the draft use active voice where the draft names the actor, keep a passive where it does not, and give no inanimate thing a verb of thought, feeling, or intent?
10. Does the edit keep useful edge and preserve structure unless the structure was hurting the piece?
11. Are genuinely tangled sentences fixed while clear spoken cadence, fragments, and changes in pace remain intact?

## Words to cut

1. In the writer's own prose, are banned words removed, and are often-empty adverbs and filler phrases removed unless they carry emphasis, uncertainty, contrast, a time or quantity meaning, or the writer's rhythm? Quotations, code, proper nouns, and technical terms stay as written.

## Patterns to cut

1. Are binary contrasts, negative listings, rhetorical setups, and throat-clearing openers removed, except a contrast that carries the writer's own voice in a first-person draft, a negation that rules out a real alternative, an "I'll be honest" that introduces a genuine admission, and FAQ question-and-answer pairs?
2. Are faux-insight setups, colon reveals, superficial analysis, fake-strong verbs, synonym cycling, runs of dramatic fragments, and robotic rhythm fixed, leaving field labels, acting or interim roles, single emphatic fragments, and deliberately parallel structure alone?
3. Is importance puffery replaced with plain facts from the draft or cut, and is each weasel phrase replaced with a source the draft or user named, or removed with its claim and any hedge kept and `[needs: source for "…"]` written after it, the claim cut only when the user said to, and the claim left as written when it already carries a citation or footnote?
4. Is interpretive metadiscourse removed, including authorial metacommentary, reader guidance, emphasis markers, and redundant glossing, with any pointer to a table, figure, or section kept as a plain reference?
5. Are fake-profound kicker lines deleted instead of rewritten into better metaphors?
6. Are endings that restate the piece cut so it ends on a concrete point, takeaway, or next action already in the draft, while a closing sentence that adds a figure, date, decision, or action stays?
7. Is formatting slop removed: Emoji headings, decorative bold, bullets that should be prose, headers over tiny sections? Bold UI labels, FAQ questions, numbered procedures, status rows, and other deliberately parallel entries stay.
8. Is text after a colon inside a sentence in lower case where that reads naturally (a preference, not a hard fail), unless grammar, a proper noun, a title, or code requires otherwise, and is the case after a field label or a signal word left as written ("Owner: Finance team", "CAUTION: Hot surface")?

## Final read

1. Outside structured text SKILL.md exempts, does the draft avoid robotic symmetry, repeated sentence shapes, and stacked punchy fragments?
2. Would the writer recognize the edited draft as their own voice?
3. Would the edited draft sound natural if read to a sharp colleague?
4. Does the final output include the full edited draft, a short **What changed** section, and a **Gaps** section listing every `[needs: …]` marker, if any?
5. For detect requests, does the response name each pattern with a quoted line and a short fix, without rewriting, scoring, claiming AI authorship, or supplying a missing detail in a fix, and, when no pattern appears, say so, name any near-miss kept on purpose, and offer no edit?

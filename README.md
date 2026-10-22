# writing-skills

A Claude Code plugin with 12 writing skills for consulting documents, technical procedures, and strategic communications. The skills cover the whole cycle: framing the argument, structuring the body, reviewing the language, and a final quality check before delivery.

## Install

In Claude Code:

```
/plugin marketplace add justinbuhler/writing-skills-plugin
/plugin install writing-skills@writing-skills
```

Or from the shell:

```
claude plugin marketplace add https://github.com/justinbuhler/writing-skills-plugin
claude plugin install writing-skills@writing-skills
```

## Using the skills

Claude loads a skill when your request matches its description, so "review this memo for plain language" or "rewrite this procedure in STE" is usually enough. To pick one yourself, name it: `/writing-skills:pyramid-editor`.

Most skills do two jobs:

- **Review**: report findings and change nothing. Ask to "review", "audit", "check", or "flag".
- **Rewrite**: return the revised text and a short list of what changed. Ask to "rewrite", "fix", or "edit".

The skills never edit your files. They return findings or revised text in the reply, and you decide what to keep.

The skills use only the facts in your text. When a fix needs a detail the text does not give, such as an owner, a date, or a figure, the skill writes a `[needs: …]` marker and lists it under **Gaps** instead of inventing a value.

## Skills

### Orchestrator

| Skill | When to use |
|---|---|
| `writing-workflow` | A full document from a brief, or a full cleanup of an existing draft. Runs the other skills in order |

### Structure

| Skill | When to use |
|---|---|
| `scqa-framework` | Opening hook and governing thought (Situation → Complication → Question → Answer) |
| `scr-narrative` | Narrative spine for a strategic recommendation or business case (Situation → Complication → Resolution) |
| `pyramid-editor` | Answer-first structure: buried recommendations, headings that don't tell the story, evidence mixed with conclusions |
| `recommendations-and-actions` | Findings, recommendations, decisions required, and action items with owners and dates |
| `diataxis` | Pages that mix steps, background, lookup facts, and lessons: type each section and split it by documentation type |

### Language

| Skill | When to use |
|---|---|
| `plain-language` | Reports, memos, letters, policy documents, and web content for a general or public audience |
| `concise-writing` | Wordy, padded or inflated prose that needs tightening without losing meaning |
| `ste100-writer` | Procedures, maintenance manuals, work instructions, and safety notices in Simplified Technical English |
| `humanizer` | Text with AI writing tells: not-X-but-Y contrasts, forced triads, inflated claims, stock AI words |
| `no-ai-slop` | Any draft that reads flat, generic, or over-polished, including human-written ones |

### Quality gate

| Skill | When to use |
|---|---|
| `document-qa` | Final check before delivery: headings, structure, repetition, and whether every claim is supported in the document |

---

## Writing workflow

For full documents, use `writing-workflow` instead of calling skills one by one. Each step hands the whole document to the next.

```
1. narrative framing   →  scqa-framework  (most documents)
                          scr-narrative   (long strategic documents)
2. pyramid-editor      →  body structure and logical flow
3. recommendations-and-actions  →  skip if the document has no findings
4. language review     →  plain-language  (reports, memos, comms)
                          ste100-writer   (procedures, manuals)
4.5 humanizer (optional)   →  text that shows AI writing patterns
4.6 no-ai-slop (optional)  →  any draft that feels flat
5. document-qa         →  final pre-delivery gate
```

Steps 4.5 and 4.6 never touch STE text. For which skill to use at each step, see [`skills/writing-workflow/routing-guide.md`](skills/writing-workflow/routing-guide.md).

---

## Standards

- `plain-language` follows the Plain Writing Act of 2010 and the federal guidelines at [plainlanguage.gov](https://www.plainlanguage.gov).
- `pyramid-editor` applies Barbara Minto's Pyramid Principle.
- `scqa-framework` and `scr-narrative` apply the Situation–Complication structures that come from the same tradition.
- `diataxis` applies Daniele Procida's [Diátaxis](https://diataxis.fr) framework for documentation types (tutorial, how-to, reference, explanation).
- `humanizer` is based on Wikipedia's [Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing).

### ste100-writer and ASD-STE100

`ste100-writer` implements ASD-STE100 Issue 9 (January 2025) from summaries written for this repository, including the rule titles. The standard is © ASD and is not included. Where the skill and the standard disagree, the standard is correct. You can request a free copy at [asd-ste100.org](https://asd-ste100.org). ASD-STE100 is a trademark of ASD; this project is not affiliated with or endorsed by ASD.

Know its limits before you rely on it:

- **The rules are close to the standard.** An audit against the full text found 47 of 53 writing rules summarised faithfully and none wrong. The other six were fixed.
- **The dictionary is not.** The standard's dictionary rules out about 1,300 words. The skill's word list covers the common ones in maintenance and safety text, not all of them. When a rewrite uses a word the list does not cover, the skill names it as one to check in the Issue 9 dictionary.
- **Measured result.** In a trial on 10 new procedures, descriptions, and safety notices, judged against the full standard, the rewrites had no major defects, and about 84% of sentences complied fully. Nearly all the misses were word choices. That trial ran before the word list grew to its current size.

Check STE output against the standard before you publish it.

---

## Tests

Each skill has a `TESTS.md` of RED/GREEN cases. RED is text that breaks the skill's rules, GREEN is the corrected version, and the Expected finding states what the skill should flag. Cases marked "must stay unflagged" check that the skill leaves good text alone.

| Skill | Tests |
|---|---|
| concise-writing | 20 |
| diataxis | 21 |
| document-qa | 28 |
| humanizer | 33 |
| no-ai-slop | 28 |
| plain-language | 36 |
| pyramid-editor | 21 |
| recommendations-and-actions | 27 |
| scqa-framework | 21 |
| scr-narrative | 23 |
| ste100-writer | 41 |
| writing-workflow | 25 |

The tests are run by a model, not a script. To run one skill's suite, start a Claude Code session in this repo and give it this prompt:

> Read `skills/<name>/SKILL.md` and `skills/<name>/TESTS.md`. For each test, apply the skill's rules to the RED text and compare your finding to the Expected finding. Report Total X/Y passed and list any FAILs.

A suite counts as passing only at X/X with no discrepancies noted. The Verification Log at the end of each `TESTS.md` records the last clean run, with hashes of the files it graded. If the hashes no longer match, that log is out of date.

## Contributing

`.githooks/pre-push` is the only gate. It checks that `plugin.json` lists exactly the skill folders, that every RED has a GREEN and an Expected finding, that cross-references resolve, that the humanizer package is valid, and that `claude plugin validate .` passes. Turn it on once per clone:

```
git config core.hooksPath .githooks
```

Claude Code sessions in this repo turn it on for you. `CLAUDE.md` has the conventions, including how the humanizer fork is maintained.

## License

MIT. See [LICENSE](LICENSE). Three skills are forks of other MIT-licensed projects and keep their own licenses:

- `skills/humanizer/` is a fork of [blader/humanizer](https://github.com/blader/humanizer). See its [LICENSE](skills/humanizer/LICENSE).
- `skills/no-ai-slop/` is a fork of [petergyang/no-ai-slop](https://github.com/petergyang/no-ai-slop). See its [LICENSE](skills/no-ai-slop/LICENSE).
- `skills/ste100-writer/` began as a fork of [blagoySimandov/asd-ste100-writer-skill](https://github.com/blagoySimandov/asd-ste100-writer-skill), which declares the MIT license in its `package.json`. It has since been rewritten. See its [LICENSE](skills/ste100-writer/LICENSE).

The other nine skills were written for this repository.

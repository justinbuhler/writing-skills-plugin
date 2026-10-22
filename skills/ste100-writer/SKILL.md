---
name: ste100-writer
description: Write and rewrite technical documents in ASD-STE100 Simplified Technical English. Use this skill when the user asks for STE, ASD-STE100, Simplified Technical English, simplified English, controlled language, or plain technical English. Also use it for aircraft, defense, machine, or industrial maintenance procedures, work instructions, warnings, cautions, safety notices, and manuals that must be easy to translate or easy to read for non-native readers.
allowed-tools: Read
---

# ASD-STE100 Writer

## What this skill does

This skill helps you to write technical documents in ASD-STE100 Simplified
Technical English (STE). STE is a controlled language. It makes technical text
easy to read for persons whose first language is not English. It also makes
machine translation more accurate.

This skill is based on ASD-STE100 Issue 9, January 2025. Issue 9 fully
replaces all previous issues and revisions.

STE has two parts:

- A set of writing rules (Part 1: 9 sections, 53 rules).
- A dictionary of approved words (Part 2).

## Source of truth

This skill applies ASD-STE100 Issue 9 from its own summaries:

- `references/rules.md`: each writing rule, with its number, title, page,
  and a summary.
- `references/word-choices.md`: the dictionary entries that the skill uses.
- `references/checklist.md`: the final check.
- `references/house-style.md`: house-style rules that are not STE.

The summaries and examples are in this skill's own words. They are not the
text of the standard. The official standard is the authority. ASD supplies it
free of charge on request from https://asd-ste100.org. A user who has the
standard should use it where it and this skill do not agree. If the user
shows you such a difference, follow the standard and tell the user.

A page ("p.N") is a page of the published standard:

| Part | Pages |
|---|---|
| Front matter (general introduction p.35) | 1-42 |
| Part 1 Writing rules | 43-128 |
| Section 1 Words | 45 |
| Section 2 Multi-word nouns | 63 |
| Section 3 Verbs | 67 |
| Section 4 Sentences | 77 |
| Section 5 Procedural writing | 87 |
| Section 6 Descriptive writing | 95 |
| Section 7 Safety instructions | 103 |
| Section 8 Punctuation and word count | 107 |
| Section 9 Writing practices (and GR-1 to GR-8) | 115 |
| Part 2 Dictionary (introduction p.131, recurring errors p.145) | 129-434 |

Dictionary letters: A 149, B 173, C 183, D 207, E 227, F 245, G 259, H 267,
I 275, J 291, K 293, L 295, M 305, N 315, O 319, P 329, Q 347, R 349, S 367,
T 399, U 413, V 421, W 425, Y 433, Z 433.

How the dictionary shows approval: a headword in UPPERCASE is approved, for
one part of speech and one meaning. A headword in lowercase is not approved,
and the entry gives approved alternatives. A word that is not in the
dictionary is not approved, unless it is a technical noun (Rule 1.5) or a
technical verb (Rule 1.12).

Before you tell the user that a word is or is not approved, find it in
`references/word-choices.md`. If it is not there, give your best judgment
and say that the word needs a check in the Issue 9 dictionary. Do not state
its approval as a fact.

The standard is ASD copyright. Do not quote long parts of it to the user.
Cite the rule number and page.

## Scope and exceptions

STE is for technical documentation that must be easy to translate or easy to
read for non-native readers: maintenance procedures, work instructions, safety
notices, and manuals.

Do not apply STE rules strictly to:

- **Creative writing** (fiction, memoir, poetry, lyrical prose): apply STE as
  a clarity filter only. Preserve intentional voice, cadence, and imagery.
  Do not restrict vocabulary or enforce sentence-count limits on creative text.
- **Marketing or persuasive writing**: these have different audience goals.
- **Quoted or extracted text**: do not rewrite text the user cannot change.
  STE treats quoted text as a technical noun (Rule 1.5, category 10) and
  counts it as one word (Rule 8.6).

When the input is creative or narrative, tell the user which STE principles
apply (usually clarity and sentence length) and which do not (vocabulary
restrictions, technical noun rules).

## What STE does not regulate

The general introduction (p.36) says that STE gives no rules for
abbreviations, text formatting (typeface, numbering, lettering), or units of
measurement. Those come from the applicable specifications for technical
publications, style guides, and official directives. Do not report a finding
against STE for these. Section 8 (p.107) also says that STE does not give
rules about general punctuation. Apply only the punctuation that Rules 4.3,
5.4, and 8.1 to 8.3 state. The house style (the House style section of this
file) adds rules for some of these subjects. Report those findings as house
style, not as STE.

STE is not used alone (p.36). Technical nouns and technical verbs come from
the company glossary or terminology database (Rule 1.1, p.46). Without that
glossary, you cannot confirm every technical noun and verb. Do not claim that
a document fully conforms to STE; say which words need a glossary check.

## Two jobs

**Review.** The user asks you to review or check text, or not to change it.
Report each finding as `[<rule number>] "<source text>": <problem>. <correction>.`
and change nothing. Give the findings in the sequence that the House style
section gives.

**Rewrite (default).** The user asks you to write, rewrite, or convert text.
Do the procedure below and give the new text.

## Procedure

1. Read the source text. Find the text type of each part. Procedural text
   gives instructions. Descriptive text gives information: a description of
   an item, a text of general information, or a note in a procedure (p.95).
   Thus, a description in a procedure is descriptive.
2. Apply the writing rules below. For each word that you are not sure of,
   find it in `references/word-choices.md` (see Source of truth).
3. In a rewrite, write the new text.
4. Apply the house style (the House style section of this file), unless the user
   asked for STE only.
5. Do a quality check. Work through `references/checklist.md` line by line.
6. If the user gives you a command to show the changes, make a table with two
   columns: the initial text and the new text.

**Use only the facts you were given.** Do not add a fact, name, number, date, owner, source, or claim that is not in the input or supplied by the user. When a rule calls for a detail the input lacks, write `[needs: <detail>]` in its place, for example `[needs: owner]` or `[needs: source for "Eight of twelve pump stations have standby power"]`, and list every gap under **Gaps** at the end of your response. Leave any `[needs: …]` already in the input where it is.

The rules below say where a `[needs: …]` applies. Use one only where an
Issue 9 rule or a house-style rule needs the element. Do not use one for a
tool list, or a condition that neither asks for. With STE only, do not use
one for a unit or a full term.

## Part 1: Writing rules

This is an index of the Issue 9 rules: number, title, and page. Before you
apply a rule, read its summary and examples in `references/rules.md`. The
paragraphs under a section heading below are instructions of this skill.
Obey them as well.

### Section 1: Words (p.45)

- **Rule 1.1** Use words that are: approved in the dictionary, technical nouns, technical verbs. (p.46)
- **Rule 1.2** Use approved words from the dictionary only as the specified part of speech. (p.46)
- **Rule 1.3** Use approved words only with their approved meanings. (p.48)
- **Rule 1.4** Use only the approved forms of verbs and adjectives. (p.48)
- **Rule 1.5** You can use words that you can include in a technical noun category. (p.49)
- **Rule 1.6** Use a word that is not approved in the dictionary, only when it is a technical noun or part of a technical noun. (p.53)
- **Rule 1.7** Do not use words that are technical nouns as verbs. (p.55)
- **Rule 1.8** Use technical nouns that are approved in your company, industry, or subject field. (p.55)
- **Rule 1.9** When you must select a technical noun, use one which is short and easy to understand. (p.56)
- **Rule 1.10** Do not use regional, slang, or jargon words as technical nouns. (p.56)
- **Rule 1.11** Do not use different technical nouns for the same item. (p.57)
- **Rule 1.12** You can use verbs that you can include in a technical verb category. (p.57)
- **Rule 1.13** Do not use technical verbs as nouns. (p.60)
- **Rule 1.14** Use American English spelling unless other official directives tell you differently. (p.61)

### Section 2: Multi-word nouns (p.63)

- **Rule 2.1** Write multi-word nouns of no more than three words. (p.63)
- **Rule 2.2** When a technical noun has more than three words, write it in full. Then, you can use one of these methods to make the technical noun clear: … (p.64)

To break up a multi-word noun, you must know how its words connect. If the
source does not show this, and a split can give different meanings (Rule 4.1),
keep the noun and write `[needs: meaning of "<noun>"]` after it.

### Section 3: Verbs (p.67)

- **Rule 3.1** Use only the verb forms that are given in the dictionary. (p.67)
- **Rule 3.2** Use only these verb forms and tenses of verbs: … (p.68)
- **Rule 3.3** Use the past participle form as an adjective. (p.68)
- **Rule 3.4** Do not use auxiliary verbs to make complex verb constructions. (p.69)
- **Rule 3.5** Use the "-ing" form of a verb only as a technical noun or as a modifier in a technical noun. (p.70)
- **Rule 3.6** Use the active voice. In descriptive writing, you can use the passive voice only if the agent is unknown. (p.71)
- **Rule 3.7** Use an approved verb to describe an action, not a noun or other parts of speech. (p.75)

Do not invent an agent to make a sentence active. In procedural text, use the
imperative (Rule 5.3). In descriptive text, keep the passive when the agent is
unknown (Rule 3.6), or use "you" when the agent is the reader (Rule 3.6,
Method 4, p.74). When the source implies a specific agent that it does not
name and none of these applies, write `[needs: actor]` in the agent's place.

Modal verbs: Issue 9 has no modal-verb rule. Use the dictionary. MUST shows
obligation. CAN means possible, able, or permitted. "Shall" is not approved:
use MUST (p.375). "Should" is not approved: use MUST, or IF for a condition
("Should a failure occur" becomes "If a failure occurs", p.377). "Have to" is
not approved: use a verb in the imperative (p.269). "May" is not approved:
use CAN (p.145-146).

In an instruction, "you should", "you shall", "you must", or "you have to"
before the verb is not the imperative (Rule 5.3, p.89). Delete it and start
with the verb: "You should clean the filter" becomes "Clean the filter", not
"You must clean the filter". Keep "must" before an imperative only if the
instruction is very important for safety or gives an important condition
(Rule 5.3, p.89-90). In descriptive text, "should" becomes MUST.

### Section 4: Sentences (p.77)

- **Rule 4.1** Write short and clear sentences. (p.77)
- **Rule 4.2** Do not omit words or use contractions to make your sentences shorter. (p.79)
- **Rule 4.3** Use a vertical list for complex text. (p.80)
- **Rule 4.4** Use connecting words and connecting phrases to connect sentences that contain related topics. (p.83)
- **Rule 4.5** When applicable, use an article (the, a, an) or a demonstrative adjective (this, these) before a noun or a multi-word noun. (p.84)

### Section 5: Procedural writing (p.87)

- **Rule 5.1** Write short sentences. Use a maximum of 20 words in each sentence. (p.87)
- **Rule 5.2** Write only one instruction in each sentence unless two or more actions occur at the same time. (p.88)
- **Rule 5.3** Write instructions in the imperative (command) form. (p.89)
- **Rule 5.4** When there is a condition that the reader must know about first, start the instruction with a descriptive statement. Then, divide that descriptive statement from the command with a comma. (p.90)
- **Rule 5.5** Write notes only to give information, not instructions. (p.91)

### Section 6: Descriptive writing (p.95)

- **Rule 6.1** Give information gradually. (p.95)
- **Rule 6.2** Use key words and key phrases to give your text a logical structure. (p.96)
- **Rule 6.3** Write short sentences. Use a maximum of 25 words in each sentence. (p.98)
- **Rule 6.4** Use paragraphs to show related information. (p.99)
- **Rule 6.5** Make sure that each paragraph has only one topic. (p.100)
- **Rule 6.6** Make sure that no paragraph has more than six sentences. (p.101)

### Section 7: Safety instructions (p.103)

- **Rule 7.1** Use an applicable word (for example, "warning" or "caution") to identify the level of risk. (p.104)
- **Rule 7.2** Start a safety instruction with a clear and accurate command or condition. (p.105)
- **Rule 7.3** Give an explanation to show the risk or possible result. (p.106)

STE does not give rules for formatting (p.104). The standard's examples are in
uppercase, but uppercase is not an STE rule. ANSI Z535 is a reference
document (p.103), not an STE format. Uppercase, a fixed format, and the
position before the step are house style (HS-6 to HS-8).

Take each part of a safety instruction from the source only:

- Do not write a hazard, a command, or a consequence yourself.
- When the source gives a risk but no action that prevents it, write
  `[needs: command]` (Rule 7.2).
- When the source gives no risk or possible result, write
  `[needs: risk or result]` (Rule 7.3).
- When the reader must know a condition first and the source does not give
  it, write `[needs: condition]` (Rule 7.2).
- When neither the signal word nor the text shows if the risk is to persons
  or to objects, keep the signal word and write `[needs: level of risk]`
  (Rule 7.1). A source WARNING already shows a risk to persons, and a source
  CAUTION a risk to objects, so neither needs the marker.

Make sure that each command agrees with the work steps that it applies to.

### Section 8: Punctuation and word count (p.107)

- **Rule 8.1** You can use all standard English punctuation marks but not the semicolon (;). (p.108)
- **Rule 8.2** Use hyphens (-) to connect words that are directly related. (p.108)
- **Rule 8.3** You can use parentheses: … (p.109)
- **Rule 8.4** In a vertical list, a colon (:) has the same effect on word count as a period and shows the end of a sentence. (p.110)
- **Rule 8.5** When you put text in parentheses, it counts as one word in that sentence. (p.111)
- **Rule 8.6** Count each of these elements as one word: … (p.111)
- **Rule 8.7** Hyphenated words count as one word. (p.114)

### Section 9: Writing practices (p.115)

- **Rule 9.1** Use a different sentence construction to write a sentence when a word-for-word replacement is not sufficient. (p.115)
- **Rule 9.2** Use each approved word correctly. (p.119)
- **Rule 9.3** When you use two words together, do not make phrasal verbs. (p.121)
- **Rule 9.4** When you select terminology or wording, always use a consistent style. (p.122)

### General recommendations (p.123)

These are not STE rules. GR-1 The conjunction "that" (p.123), GR-2 The
preposition "with" (p.124), GR-3 How to use pronouns (p.125), GR-4 The pronoun
"this" (p.125), GR-5 False friends (p.126), GR-6 Latin abbreviations (p.126),
GR-7 Inclusive language (p.127), GR-8 Possessive form (p.127).

## Common changes

`references/word-choices.md` gives the common words that Issue 9 does not
approve, the approved words to use in their place, and the dictionary page of
each. It includes each word in the standard's list of recurring errors
(dictionary p.145-146). For a word that is not in that file, see Source of
truth.

APPROXIMATELY, SUFFICIENT, ADJACENT, INITIAL, PREVIOUS, SUBSEQUENT (adj),
INSPECTION, MALFUNCTION, and PERSONNEL are approved. Do not replace them.

## House style

After the Issue 9 check, apply `references/house-style.md` (HS-1 to HS-8):
dashes, slashes, figures, units, abbreviations, and the case, format, and
position of warnings and cautions. These rules are house style, not
ASD-STE100.

- Tag each finding `[House style HS-n]`. Never give it an Issue 9 rule number
  and never call it an STE finding.
- Where house style and Issue 9 disagree, Issue 9 wins. Tell the user.
- When the user says "STE only", or tells you not to use house style, do not
  apply it.

Give the findings in this sequence: the Issue 9 findings (`[5.1] …`), then
the house-style findings (`[House style HS-4] …`), then **Gaps**.

## Quality check

Work through `references/checklist.md` line by line before you give the text
to the user, then do the checks below as well. Where the two differ, follow
`references/rules.md`.

- Count the words in each sentence with the counting rules of Section 8.
  Procedural: maximum 20 (Rule 5.1). Descriptive and notes: maximum 25
  (Rule 6.3, Rule 5.5).
- Find each passive verb. Change it to the active voice (Rule 3.6), without
  an invented agent.
- Find each complex verb construction (Rules 3.2, 3.4).
- Find each "-ing" word. Keep it only if it is a technical noun, a modifier in
  a technical noun, or an approved "-ing" word (Rule 3.5).
- Find each word that `references/word-choices.md` lists, in the part of
  speech that it gives. Do not change it in a technical noun (Rule 1.6) or in
  quoted text, such as a placard or a marking (Rule 1.5, category 10). For
  each other word that you are not sure of, see Source of truth.
- Find each semicolon. Write two sentences (Rule 8.1).
- Make sure that each technical noun is the same in all of the text
  (Rules 1.11, 9.4).
- Make sure that the technical data did not change (Rules 4.1, 9.1).
- Make sure that no note gives an instruction, a requirement, or a limit
  (Rule 5.5).
- Unless the user asked for STE only, do the house-style checks HS-1 to HS-8
  in `references/house-style.md`. Tag each finding `[House style HS-n]`.
- Make sure that the new text has no fact, value, name, tool, or actor that is
  not in the source. Each gap is a `[needs: …]` and is listed under **Gaps**.

Never change the technical content to obey a rule. If a rule and the technical
accuracy have a conflict, tell the user.

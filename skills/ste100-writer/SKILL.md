---
name: ste100-writer
description: Write and rewrite technical documents in ASD-STE100 Simplified Technical English. Use this skill when the user asks for STE, ASD-STE100, Simplified Technical English, simplified English, controlled language, or plain technical English. Also use it for aircraft, defense, machine, or industrial maintenance procedures, work instructions, warnings, cautions, safety notices, and manuals that must be easy to translate or easy to read for non-native readers.
allowed-tools: Read
routing:
  category: content-creation
  triggers:
    - "ste100"
    - "simplified technical english"
    - "asd-ste100"
    - "controlled language"
    - "write a procedure in STE"
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

- `references/rules.md`: each writing rule, with its number, a paraphrased
  title, its page, and a summary.
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

Put these words in one list, "Words to check in the Issue 9 dictionary", at
the end of your response. Before you make the list, read "The Words to check
list" in `references/word-choices.md`: it says which words go on the list,
and the line to give for each. A word that `references/word-choices.md`
gives as not approved is never on the list: replace it.

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
Do the procedure below. Give the new text first. Then give these sections
in this sequence, and omit a section that is empty:

1. **Notes**: each decision that the user must confirm.
2. **Changes**: one line for each finding, tagged, in the sequence that the
   House style section gives. When the user asks to see the changes, the
   table of step 6 replaces this list.
3. **Gaps**: each `[needs: …]` in the new text.
4. **Words to check in the Issue 9 dictionary** (see Source of truth).

If the user asks for the new text only, give the new text, then **Gaps** and
**Words to check**.

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

This is an index of the Issue 9 rules: number, title (paraphrased), and
page. Before you apply a rule, read its summary and examples in
`references/rules.md`. The paragraphs under a section heading below are instructions of this skill.
Obey them as well.

### Section 1: Words (p.45)

- **Rule 1.1** Restrict the vocabulary to dictionary-approved words, technical nouns, and technical verbs. (p.46)
- **Rule 1.2** Give each approved word only the part of speech that the dictionary lists for it. (p.46)
- **Rule 1.3** Give each approved word only the meaning that the dictionary assigns to it. (p.48)
- **Rule 1.4** Inflect verbs and adjectives only in the forms that the dictionary permits. (p.48)
- **Rule 1.5** A word that fits a technical-noun category is permitted. (p.49)
- **Rule 1.6** An unapproved word is permitted only as a technical noun or inside one. (p.53)
- **Rule 1.7** Never turn a technical noun into a verb. (p.55)
- **Rule 1.8** Prefer the technical nouns that your organization or field has already sanctioned. (p.55)
- **Rule 1.9** Choose the shortest, clearest technical noun available. (p.56)
- **Rule 1.10** Keep regional terms, slang, and jargon out of technical nouns. (p.56)
- **Rule 1.11** Call each item by a single technical noun throughout. (p.57)
- **Rule 1.12** A word that fits a technical-verb category is permitted. (p.57)
- **Rule 1.13** Never turn a technical verb into a noun. (p.60)
- **Rule 1.14** Spell in American English unless an official directive says otherwise. (p.61)

The Rule 1.12 test: if an approved verb is accurate in the sentence, the word
is not a technical verb there, so use the approved verb ("reset" becomes SET,
"trip" becomes OPEN, "prime" becomes FILL). Use a technical verb only when no
approved verb gives the same information. When an approved verb fits the
action exactly (BYPASS, ENGAGE, RELEASE), use it, not a longer paraphrase
with other approved words.

Approved does not mean safe in all uses. Some approved words have a narrow
meaning (GET, COME, LOOK, CHARGE, AIRBORNE, GO, LIVE, CONTACT) or one part
of speech only (RELEASE, CHECK, TEST, LEAK, HEAT, SINCE, CONTACT), or not
in every part of speech (FLUSH is not a noun).
`references/word-choices.md` lists them. Look at each one when it is in the
text. Two are easy to miss because the general meaning sounds correct:

- GO is for movement only. An area that "goes to 30 m" or a crack that
  "goes to the edge" does not move: use BE ("there is a crack from the hole
  to the edge").
- LIVE is for explosive material only. Electrical equipment is ENERGIZED or
  DE-ENERGIZED (Rule 3.3).

Rule 1.1 applies to headings and titles too: "Preparation" (→ PREPARE) and
"Quarterly" (→ INTERVAL) are not approved.

When an approved word has a meaning in the text that the dictionary does not
give, and its entry gives no alternative for that meaning (CHARGE for a
spring), do these steps in sequence:

1. Read all of the entry. Some words have two approved meanings: APPLY
   includes a force or a pressure, so "apply the brakes" is correct.
2. Find a different approved word or a technical verb that gives the action,
   for example COMPRESS (v), if the source shows that the spring compresses.
3. Write the sentence again with approved words that keep the meaning
   (Rule 9.1). For "serious injury", use DANGEROUS in a different
   construction (serious (adj), p.373).
4. If no construction keeps the meaning, keep the source word, put it in
   Words to check, and tell the user. Do not drop a part of the meaning, such
   as a degree or a limit, to get an approved word.

### Section 2: Multi-word nouns (p.63)

- **Rule 2.1** Limit a noun cluster to three words. (p.63)
- **Rule 2.2** A technical noun of four or more words may be made clearer with a shorter form or with hyphens. (p.64)

The three-word limit applies to the groups that you make. Keep an approved
technical noun of four or more words whole, and apply Rule 2.2 to it: write
it in full the first time. After that, prefer a shorter form or an
abbreviation that is approved; repeating the full noun is allowed.

To break up a multi-word noun, you must know how its words connect. If the
source does not show this, and a split can give different meanings (Rule 4.1),
keep the noun and write `[needs: meaning of "<noun>"]` after it.

### Section 3: Verbs (p.67)

- **Rule 3.1** Restrict verbs to the forms that the dictionary lists. (p.67)
- **Rule 3.2** Limit verbs to six permitted forms and tenses. (p.68)
- **Rule 3.3** A past participle may serve as an adjective. (p.68)
- **Rule 3.4** Avoid chains of auxiliary verbs that build complex verb phrases. (p.69)
- **Rule 3.5** Limit "-ing" words to technical nouns and their modifiers. (p.70)
- **Rule 3.6** Prefer the active voice. Descriptive text may use the passive only when the actor is unknown. (p.71)
- **Rule 3.7** Express an action with an approved verb, not with a noun or another word class. (p.75)

An "-ing" process name such as "cleaning" or "handling" is a technical noun
only if it names a defined process, in the glossary or in a heading
(Rule 3.5). In a sentence about the work, use the verb.

Complex verbs: "has/have/had" with a past participle, "is to be", and a modal
with "be" and a past participle ("must be removed") are not permitted
(Rules 3.2, 3.4). A modal with an infinitive ("can remove") is permitted. A
plain "is" or "was" with a past participle is an adjective that gives a
condition (Rule 3.3) or a simple passive that Rule 3.6 decides.

Do not invent an agent to make a sentence active. In procedural text, use the
imperative (Rule 5.3). In descriptive text, keep the passive when the agent is
unknown (Rule 3.6), or use "you" when the agent is the reader (Rule 3.6,
Method 4, p.74). When the source implies a specific agent that it does not
name and none of these applies, write `[needs: actor]` in the agent's place.

One "by" phrase can follow two passive verbs ("the line has been tested and
the grounding devices have been installed by the nominated person"). Then the
source does not show who did the first action. Give the agent only to the
verb that it is nearest to. For the other action, use a construction that
needs no agent ("make sure that a test showed that the line is
de-energized"). If the text must say who did it, write `[needs: actor]`.
Tell the user in Notes.

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

- **Rule 4.1** Keep sentences brief and unambiguous. (p.77)
- **Rule 4.2** Never drop words or contract them to save length. (p.79)
- **Rule 4.3** Break complex text into a vertical list. (p.80)
- **Rule 4.4** Link sentences on related topics with connectors. (p.83)
- **Rule 4.5** Where it fits, put an article (the, a, an) or "this"/"these" before a noun or noun cluster. (p.84)

### Section 5: Procedural writing (p.87)

- **Rule 5.1** Procedural sentences: 20 words at most. (p.87)
- **Rule 5.2** One instruction per sentence, except for simultaneous actions. (p.88)
- **Rule 5.3** Phrase each instruction as an imperative. (p.89)
- **Rule 5.4** Put a condition the reader needs first at the start, as a descriptive clause set off from the command by a comma. (p.90)
- **Rule 5.5** Notes carry information only, never instructions. (p.91)

Before you divide a step (Rule 5.2) or change a note (Rule 5.5), read the
notes "Divided steps" and "Notes with a safety meaning" in
`references/rules.md`.

### Section 6: Descriptive writing (p.95)

- **Rule 6.1** Release information in stages. (p.95)
- **Rule 6.2** Structure the text with key words and phrases. (p.96)
- **Rule 6.3** Descriptive sentences: 25 words at most. (p.98)
- **Rule 6.4** Group related information into paragraphs. (p.99)
- **Rule 6.5** Limit each paragraph to a single topic. (p.100)
- **Rule 6.6** Six sentences at most per paragraph. (p.101)

### Section 7: Safety instructions (p.103)

- **Rule 7.1** Mark the risk level with a signal word such as "warning" or "caution". (p.104)
- **Rule 7.2** Open a safety instruction with a precise command or condition. (p.105)
- **Rule 7.3** Explain the risk or the likely consequence. (p.106)

STE does not give rules for formatting (p.104). The standard's examples are in
uppercase, but uppercase is not an STE rule. ANSI Z535 is a reference
document (p.103), not an STE format. Uppercase, a fixed format, and the
position before the step are house style (HS-6 to HS-8).

Take each part of a safety instruction from the source only. Do not write a
hazard, a command, or a consequence yourself, with one exception: where the
source gives a risk and names the act of a person that causes it, write the
command that forbids that act. For a part that the source does not give,
write only the `[needs: …]` marker that Section 7 of `references/rules.md`
gives. Keep all of the meaning of a safety instruction: an exception stays,
and a prohibition does not become narrower. A safety command that is valid
STE but not precise stays. Make sure that each command agrees with the work
steps that it applies to.

Before you write, change, or review a safety instruction, read the notes
"Missing parts of a safety instruction", "No signal word", "One risk for a
group of instructions", and "Keep all of the meaning" under Section 7 in
`references/rules.md`.

### Section 8: Punctuation and word count (p.107)

- **Rule 8.1** Any standard English punctuation mark is permitted except the semicolon (;). (p.108)
- **Rule 8.2** Hyphenate (-) words that belong closely together. (p.108)
- **Rule 8.3** Parentheses have seven permitted uses. (p.109)
- **Rule 8.4** For the word count, a colon (:) that introduces list items ends a sentence, as a period does. (p.110)
- **Rule 8.5** Parenthesized text counts as a single word of its sentence. (p.111)
- **Rule 8.6** Certain elements count as one word each. (p.111)
- **Rule 8.7** A hyphenated compound counts once. (p.114)

### Section 9: Writing practices (p.115)

- **Rule 9.1** Restructure the sentence when a one-for-one word swap does not work. (p.115)
- **Rule 9.2** Use every approved word as the dictionary intends. (p.119)
- **Rule 9.3** Do not form phrasal verbs from word pairs. (p.121)
- **Rule 9.4** Keep terminology and wording consistent. (p.122)

### General recommendations (p.123)

These are not STE rules. GR-1 The conjunction "that" (p.123), GR-2 The
preposition "with" (p.124), GR-3 How to use pronouns (p.125), GR-4 The pronoun
"this" (p.125), GR-5 False friends (p.126), GR-6 Latin abbreviations (p.126),
GR-7 Inclusive language (p.127), GR-8 Possessive form (p.127).

## Common changes

`references/word-choices.md` gives the common words that Issue 9 does not
approve, the approved words to use in their place, and the dictionary page of
each. It includes each word in the standard's list of recurring errors
(dictionary p.145-146), the common verbs and modifiers of maintenance and
safety text, the approved words with a narrow meaning, and the approved words
that have one part of speech only. For a word that is not in that file, see
Source of truth.

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
- Find each passive verb (Rule 3.6). In procedural text, make it active,
  usually with the imperative. In descriptive text, keep it if the agent is
  unknown. If the source gives the agent, make that agent the subject, use
  "you" or "we", or use a verb that needs no agent ("The valve opens").
  Never invent an agent.
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

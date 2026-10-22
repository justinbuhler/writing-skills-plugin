# House style

These rules are house style. They are **not** ASD-STE100.
Issue 9 does not contain them, so never cite them as STE rules or report them as STE findings.

- Apply them after the Issue 9 check, to text that already obeys Issue 9.
- Tag each finding `[House style HS-n]`, never with an Issue 9 rule number.
- Where a house-style rule and Issue 9 disagree, Issue 9 wins (`references/rules.md`). Each rule below records what Issue 9 says, with the page of the published standard.
- House style only narrows choices that Issue 9 leaves open. The general introduction (p.36) says that STE gives no rules for abbreviations, formatting, or units, and Section 8 (p.107) says that STE gives no rules about general punctuation.
- The no-invention rule in `SKILL.md` applies here too. Write `[needs: …]` only where a rule below says so.
- When the user says "STE only", or tells you not to use house style, skip this file.

Each example obeys Issue 9 as well as the house-style rule.

## HS-1 No em dash or en dash

Do not use an em dash (—) or an en dash (–). Write a separate sentence, or connect the ideas with an approved word. For a range, use BETWEEN … AND. Do not replace a dash with a semicolon (Rule 8.1).

*Why:* a dash can divide ideas, show a range, or show a pause, so the reader must guess which.

*Example:* "The pressure is between 30 psi and 35 psi.", not "The pressure is 30–35 psi."

*Issue 9:* permits it. Rule 8.1 permits all standard punctuation marks except the semicolon (p.108), and p.108 describes the dash without a restriction. House style narrows the choice: applies.

## HS-2 No slash for "and" or "or"

Do not use a slash ("/") to mean "and" or "or". Write "and" or "or". The combination "and/or", a unit of measurement (km/h), and quoted text keep their slash. A slash in an established technical noun (a name from the parts data or the glossary, for example "load/unload valve") also stays: Rule 1.8 tells you to use the approved term, and Issue 9 wins over house style. If the source does not show which word it means, keep the slash and write `[needs: "and" or "or" in "<text>"]`.

*Why:* "cloth/tissue" can mean the two items or one of them, and the reader cannot tell which.

*Example:* "Clean the lens with a soft cloth or a lens tissue.", not "Clean the lens with a soft cloth/lens tissue."

*Issue 9:* permits it. Rule 8.1 permits all standard punctuation marks except the semicolon (p.108). Rule 8.3 also lets you give an alternative in parentheses (p.109). House style narrows the choice: applies.

## HS-3 Numbers as figures for quantities

Write a quantity as a figure (6 screws), not as a word (six screws). Do not change a number in quoted text (Rule 1.5, category 10, p.51) or in an approved technical noun (Rule 2.2, p.64).

*Why:* figures are faster to find and read, and they do not change in translation.

*Example:* "Attach the bracket with 6 screws."

*Issue 9:* permits the two forms. Rule 8.2 hyphenates two-word numbers ("forty-seven", p.108), and the Rule 8.6 examples use number words and figures ("twenty-one ribs", "steps 13 thru 16", p.111). House style narrows the choice: applies.

## HS-4 Units with the number

Give each measured value its unit of measurement. Put a space between the number and the unit symbol (25 Nm, 80 °C). The symbols for plane angle take no space (90°). A unit in a table column heading gives the unit of each value in that column. If the source gives no unit, do not select one: write `[needs: unit]` after the number.

*Why:* a value with no unit is not a specification, and "12Nm" is easy to misread.

*Example:* "Set the pressure regulator to 350 kPa."

*Issue 9:* says nothing. STE does not regulate units of measurement (p.36). The Rule 8.6 examples put a unit after its number with a space ("10 °C", "20 kg", p.112), and they also permit a unit written in full ("10 degrees Celsius"). House style narrows the choice: applies.

## HS-5 Standard abbreviations only

Use only standard abbreviations: unit symbols, abbreviations that the applicable specification or company glossary lists, and abbreviations in wide general technical use whose full term is not in doubt (DC, AC, PVC, LED). Write each other term in full. If the source does not give the full term of such an other abbreviation, keep the abbreviation and write `[needs: full term for "<abbreviation>"]`. A widely used abbreviation does not get this marker. Without the glossary, say which project or company abbreviations need a glossary check.

*Why:* an abbreviation helps only a reader who knows it, and the same letters can have two or more meanings.

*Example:* "Disconnect the fuel quantity sensor.", not "Disconnect the FQS."

*Issue 9:* permits abbreviations. STE gives no rules for abbreviations (p.36). It lets you use abbreviations from official company documentation, but tells you to be careful (p.65), and says that they help only if the reader knows their meanings (p.112). Rule 8.3 permits an abbreviation in parentheses (p.109). House style narrows the choice: applies. Latin abbreviations are already GR-6 (p.126).

## HS-6 Uppercase warnings and cautions

Write the full text of each warning and caution in uppercase letters, including the signal word. A unit symbol keeps its case (5 Nm, not 5 NM), because a changed symbol changes the value (Rule 4.1). A `[needs: …]` marker keeps its form.

*Why:* uppercase makes a safety instruction different from the procedure text around it.

*Example:* "CAUTION: DO NOT APPLY MORE THAN 3 Nm OF TORQUE TO THE LAMP HOLDER. TOO MUCH TORQUE CAN BREAK THE LAMP HOLDER."

*Issue 9:* says nothing. The Section 7 examples are in uppercase, but STE does not give rules for formatting (p.104, p.36). House style narrows the choice: applies.

## HS-7 Fixed format for warnings and cautions

Write each warning and caution in this sequence:

```
SIGNAL WORD: [CONDITION,] COMMAND. [MORE COMMANDS.] EXPLANATION.
```

- **Signal word** (Rule 7.1), then a colon.
- **Condition**, only if the source gives one. Write it as a clause before the first command, and divide it from the command with a comma, as in Rule 5.4. If the source gives no condition, start with the command. Write `[needs: condition]` only where Rule 7.2 needs one: the reader must know it before the work step, and the source does not give it.
- **Commands**, all before the explanation. They can be a vertical list (p.81).
- **Explanation** of the risk or possible result, last (Rule 7.3). If the source does not give one, write `[needs: risk or result]`.

Each sentence obeys Rule 5.1 (20 words, p.87). Take each part from the source only.

*Why:* the reader finds the same part in the same position in each safety instruction.

*Example:* "WARNING: WHEN THE CHARGER OPERATES, DO NOT DISCONNECT THE BATTERY CLAMPS. A SPARK CAN CAUSE A FIRE."

*Issue 9:* conflicts in part; Issue 9 wins.

- The old ANSI Z535-style sequence, CONDITION. COMMAND. CONSEQUENCE., started with a hazard statement ("THE FUEL IS FLAMMABLE."). Rule 7.2 tells you to start with a command or a condition (p.105), so a hazard statement goes in the explanation, after the commands. ANSI Z535 is only a reference in Issue 9 (p.103).
- Rule 7.2 permits a start with the command, and puts a condition first only when the reader must know it first (p.105). Thus the condition slot is optional, and house style never makes you write a condition that the source does not give.
- The explanation last, after all the commands, narrows what Rules 7.2 and 7.3 permit (p.105-106): applies.

## HS-8 Warnings and cautions before their step

Put each warning and caution immediately before the first work step that it applies to. Make sure that its command agrees with the sequence of the work steps.

*Why:* a reader who obeys the steps in sequence must read the risk before doing the work.

*Example:* a CAUTION that applies to step 3 goes after step 2 and before step 3, not after step 3.

*Issue 9:* says nothing. No rule tells you where a safety instruction goes (Rules 7.1 to 7.3, p.103-106; Rule 5.5, p.91-92). Rule 7.2 orders the condition inside the instruction, not the position of the instruction in the procedure (p.105). House style fills the gap: applies.

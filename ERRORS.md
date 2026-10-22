# ERRORS.md

Approaches that failed more than once. Check before repeating similar work.

## Changing a rule without re-checking what cites it

**What did not work.** Editing a rule in `SKILL.md`, verifying the change itself, and stopping.
Every time, something else cited the old rule. Amending `ste100` Rule 8.6 to require unit
spacing made `80°C` a breach in the same file. Making `plain-language`'s substitution table
strict took four rounds — delete one row, then 26 GREENs, then 4 worked examples, then 6
Expected-finding remedies — because each round fixed the places checked and not the class.
Adding a Resolution owner-and-timing rule to `scr-narrative` failed three of its own GREENs.

**What worked instead.** Grep every citation of the rule before editing, then re-grade the
whole suite rather than the changed test. The grading caught all of it; self-review caught none.

**Note for next time.** A rule edit is a fan-out, not a point change. Budget for the fan-out.

## Claiming a mechanical verification whose scope was narrower than the wording

**What did not work.** Reporting "zero hits, verified mechanically" after scanning GREENs only,
then remedies matching `→ "…"` only, while the claim as worded implied the whole file. A remedy
using `Rewrite: "…"` survived two of those scans. Separately, a longest-shared-word-run scan
reported lifted test content cut from 45 words to 16; a skeleton comparison then scored
unrelated skills *higher* than related ones, so neither measured what the wording claimed.

**What worked instead.** State the scope in the same sentence as the number. Run a control
before trusting a similarity metric — an unrelated-skill baseline invalidated one outright.

**Note for next time.** Agents reading the files found every defect the scans missed, including
template reuse that no word-level measure can see.

## ste100 test 5.3 took four attempts

**What did not work.** Writing a plausible warning and checking it against the rule under test.
Attempt 1 was consequence-only, breaking the ANSI format. Attempt 2 commanded
"disconnect the power before you remove the battery", contradicting the procedure's step 1.
Attempt 3 forbade touching the cable that step 2 disconnects.

**What worked instead.** Reading the numbered steps first and writing a command that endorses
their order: battery out, then cable.

**Note for next time.** A safety warning is checked against the procedure it sits above, not
only against the rule being tested.

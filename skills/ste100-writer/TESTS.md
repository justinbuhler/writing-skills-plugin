# ASD-STE100 Issue 9 — Skill Evaluation Tests

Each test has:

- **RED:** text that violates the rule (should be flagged)
- **GREEN:** text that complies with the rule (should pass)
- **Expected finding:** what the skill should flag in the RED case

Rule numbers are ASD-STE100 Issue 9's own, the same numbers that `SKILL.md`,
`references/rules.md`, and `references/checklist.md` use. Rule titles are this skill's
paraphrases, the same ones that `references/rules.md` uses.
A page ("p.N") is a page of the published standard.
Where a finding says a word is or is not approved, the page is that word's dictionary entry.
Each such entry, and each rule detail that a finding depends on, is in `references/rules.md` or
`references/word-choices.md`: grade every test from `SKILL.md` and `references/` alone.
Every word in every GREEN was checked against the published dictionary when the test was written:
it is approved in the part of speech and meaning used, or is a technical noun (Rule 1.5) or
technical verb (Rule 1.12). A GREEN word that the references do not list is not a failure,
unless the references say that it is not approved in that use.
Word counts follow Section 8 (Rules 8.4 to 8.7): a number with its unit counts as one word,
and so does a hyphenated word.
Tests exist for Sections 1 to 8; the tests that the realignment to Issue 9 removed are listed
under "Tests dropped" at the end.
Grade the Section 1 to 8 tests with house style off ("STE only"): they test Issue 9 alone.
The House style tests apply `references/house-style.md` after the Issue 9 check.
Each of their REDs obeys Issue 9 and breaks only its house-style rule, and each GREEN obeys Issue 9 and all of house style.

---

## Section 1 — Words

### Rule 1.1 — Restrict the vocabulary to dictionary-approved words, technical nouns, and technical verbs

**RED:**

> Commence the inspection by verifying that the apparatus is secured.

**GREEN:**

> When you start the inspection, make sure that the apparatus is correctly attached.

**Expected finding:** `[1.1] "Commence" is not approved: use START (p.194). "Verifying" is not approved: use MAKE SURE (p.422); as an "-ing" form it also breaks Rule 3.5. "By" is approved only as a mathematical function word (BY (prep), p.182), so "by verifying" also goes. "Secured" is not approved: for this condition, secure (adj) → CORRECTLY (adv), as in "correctly attached" (p.370). "Inspection" is approved (INSPECTION (n), p.285): keep it. "Apparatus" is not in the dictionary: keep it only if it is a technical noun in the company glossary (Rules 1.5, 1.8), and say that it needs a glossary check.`

---

### Rule 1.1 — Restrict the vocabulary to dictionary-approved words, technical nouns, and technical verbs ("shall")

**RED:**

> You shall torque the fasteners to 25 Nm.

**GREEN:**

> Torque the fasteners to 25 Nm.

**Expected finding:** `[1.1] "shall" is not approved: use MUST (shall (v), p.375; list of recurring errors, p.146). In a procedure, write the instruction in the imperative instead (Rule 5.3): "Torque the fasteners to 25 Nm." TORQUE (v) is approved (p.406).`

---

### Rule 1.1 — Restrict the vocabulary to dictionary-approved words, technical nouns, and technical verbs ("should")

**RED (descriptive text):**

> The operator should keep the guard closed while the saw operates.

**GREEN:**

> The operator must keep the guard closed while the saw operates.

**Expected finding:** `[1.1] "should" is not approved: use MUST (should (v), p.377; list of recurring errors, p.146). "The operator must keep the guard closed while the saw operates."`

---

### Rule 1.2 — Give each approved word only the part of speech that the dictionary lists for it

**RED:**

> Before you install the pump, test it.
> (Using "test" as a verb — "test" is approved only as a noun in the dictionary.)

**GREEN:**

> Before you install the pump, do a test of it.

**Expected finding:** `[1.2] "test" is approved as a noun only (TEST (n), p.401). Use "do a test of it" instead of "test it".`

---

### Rule 1.2 — Give each approved word only the part of speech that the dictionary lists for it ("light")

**RED:**

> The amber lamp lights if there is a blockage in the filter.

**GREEN:**

> The amber lamp comes on if there is a blockage in the filter.

**Expected finding:** `[1.2] "lights" uses "light" as a verb. LIGHT is approved as an adjective only (LIGHT (adj), p.299). For light (v), use COME ON: "The amber lamp comes on if there is a blockage in the filter."`

---

### Rule 1.3 — Give each approved word only the meaning that the dictionary assigns to it

**RED:**

> Follow the safety procedures at all times.
> (Using "follow" to mean "obey" — the approved meaning is "to come after, to go after".)

**GREEN:**

> Obey the safety procedures at all times.

**Expected finding:** `[1.3] "follow" is approved to mean "come after, go after", not "obey" (FOLLOW (v), p.254). Use "obey".`

---

### Rule 1.5 — A word that fits a technical-noun category is permitted (quoted text)

**RED (rewrite that changes placard text):**

> Original: Make sure that the placard "DO NOT OPERATE PRIOR TO INSPECTION" is on the control panel.
> Rewritten: Make sure that the placard "DO NOT OPERATE BEFORE INSPECTION" is on the control panel.

**GREEN:**

> Make sure that the placard "DO NOT OPERATE PRIOR TO INSPECTION" is on the control panel.

**Expected finding:** `[1.5] The rewrite changed the text on a placard. Text on placards is quoted text, a technical noun category (Rule 1.5, category 10, p.51), because you cannot change it. Keep "DO NOT OPERATE PRIOR TO INSPECTION" as the source writes it, although prior to (prep) is not approved elsewhere (→ BEFORE, p.340). Do not flag the GREEN. The quoted text counts as one word (Rule 8.6).`

---

### Rule 1.11 — Call each item by a single technical noun throughout

**RED:**

> Remove the cover. Clean the lid with a dry cloth. Replace the panel after you finish.
> ("cover", "lid", and "panel" refer to the same component.)

**GREEN:**

> Remove the cover. Clean the cover with a dry cloth. Install the cover again after you clean the cover.

**Expected finding:** `[1.11] Three different terms ("cover", "lid", "panel") refer to the same component. Use one term throughout. Also: "finish" (v) is not approved (→ COMPLETE, p.250); here it ends the cleaning step, so name that action ("after you clean the cover") rather than drop the clause. The clause only gives the sequence of two actions, so it can stay after the command, as in the source: it is not a Rule 5.4 condition; and REPLACE means "remove an item and install a new or serviceable item" (p.359), so to put the same cover back, use "install … again" (Rule 1.3).`

---

### Rule 1.12 — A word that fits a technical-verb category is permitted

**RED:**

> The motor rotates the drive shaft.

**GREEN:**

> The motor turns the drive shaft.

**Expected finding:** `[1.12] "rotates" cannot stay as a technical verb. Do not use a technical verb if you can write the same sentence with approved words (p.59), and an approved verb gives the same information: rotate (v) → TURN (v) (p.364; list of recurring errors, p.145). "The motor turns the drive shaft." The word is thus also not approved (Rule 1.1): a finding with the tag [1.1] and this basis is the same finding.`

---

### Rule 1.14 — Spell in American English unless an official directive says otherwise

**RED:**

> Torque the centre bolt to twenty-five newton-meters.

**GREEN:**

> Torque the center bolt to twenty-five newton-meters.

**Expected finding:** `[1.14] "centre" is British English spelling. Use American English spelling, "center" (p.61; CENTER (TN), p.187), unless an official directive gives a different spelling. Do not change "twenty-five" to a figure: STE has no rule that numbers are figures, and its own examples use number words (p.108, p.111). STE gives no rules for units of measurement (p.36).`

---

## Section 2 — Multi-word nouns

### Rule 2.1 — Limit a noun cluster to three words

**RED:**

> Refer to the fuel system pressure relief valve assembly installation procedure.
> ("fuel system pressure relief valve assembly" is the technical noun in the parts catalog.)

**GREEN:**

> Refer to the installation procedure for the fuel system pressure relief valve assembly.

**Expected finding:** `[2.1] The multi-word noun "fuel system pressure relief valve assembly installation procedure" has 8 words. The maximum is 3. Use a preposition to break it up: "the installation procedure for …". [2.2] "fuel system pressure relief valve assembly" is an approved technical noun of more than three words: keep it whole and write it in full, as the source writes it. If it occurs again, a shorter form, an abbreviation that is approved, or hyphens make it clearer; these are options, not duties (p.64-66).`

---

## Section 3 — Verbs

### Rule 3.5 — Limit "-ing" words to technical nouns and their modifiers

**RED:**

> Before starting the engine, check the oil level.

**GREEN:**

> Before you start the engine, do a check of the oil level.

**Expected finding:** `[3.5] "starting" is an "-ing" form used as a noun (object of "before"), not a technical noun. Rewrite: "Before you start the engine, …". Also [1.2]: "check" is approved as a noun only (CHECK (n), p.188; check (v), p.189): "do a check of the oil level".`

---

### Rule 3.6 — Prefer the active voice. Descriptive text may use the passive only when the actor is unknown

**RED (procedural):**

> The valve must be closed before the pump is started.
> (The source gives an instruction: the reader closes the valve and starts the pump. It does not describe the condition of the valve or of the pump.)

**GREEN:**

> Before you start the pump, close the valve.

**Expected finding:** `[3.6] Passive voice in a procedure ("must be closed", "is started"). Use the active voice: the imperative for the command (Method 3, p.73), and "you" as the subject of "start", because the sentence does not give the agent and the agent is the reader (Method 4, p.74): "Before you start the pump, close the valve." The "before" clause only gives the sequence of two actions, so it is not a Rule 5.4 condition: it can come first, as here, or stay after the command. "must be closed" is also a complex verb construction (Rule 3.4).`

---

### Rule 3.7 — Express an action with an approved verb, not with a noun or another word class

**RED (procedural; the reader completes the check):**

> The completion of the check is required before flight.

**GREEN:**

> Complete the check before flight.

**Expected finding:** `[3.7] "completion" describes the action with a noun. Use the approved verb: "Complete the check before flight." Also [1.1]: completion (n) is not approved (→ COMPLETE (v), END (n), p.196), and "is required" uses require (v), which is not approved (→ NECESSARY, p.360). Also [3.6]: "is required" is a passive. The imperative "Complete" removes it.`

---

## Section 4 — Sentences

### Rule 4.1 — Keep sentences brief and unambiguous (be accurate)

**RED (rewrite that changes a value):**

> Original: "Apply a torque of 25 ±2 Nm."
> Rewritten: "Apply a torque of approximately 25 Nm."

**GREEN:**

> Apply a torque of 25 ±2 Nm.

**Expected finding:** `[4.1] "approximately" removes the tolerance. Be accurate: do not change a measurement or tolerance to obey a writing rule (Rules 4.1, 9.1). Keep "25 ±2 Nm" exactly. APPROXIMATELY is an approved word (p.166); the defect is the lost tolerance.`

---

### Rule 4.2 — Never drop words or contract them to save length

Context: the parts data names this kit, so "kit" is a technical noun here.

**RED:**

> The kit contains the following items. A wrench, a gasket, and two bolts.

**GREEN:**

> The kit contains a wrench, a gasket, and two bolts.

**Expected finding:** `[4.2] "A wrench, a gasket, and two bolts." has no subject and no verb. Do not omit words to make a sentence shorter. Also [1.1]: "following" (adj) is not approved (→ THESE, or "that follow", p.254). Rewrite: "The kit contains a wrench, a gasket, and two bolts." Not flagged: "kit" is the name in the parts data, a technical noun (Rule 1.5, category 1), not the general word that Rule 1.10 replaces.`

---

### Rule 4.5 — Where it fits, put an article (the, a, an) or "this"/"these" before a noun or noun cluster

**RED:**

> Before you remove pump, close isolation valve.

**GREEN:**

> Before you remove the pump, close the isolation valve.

**Expected finding:** `[4.5] Missing articles ("the") before "pump" and "isolation valve". Use an article where applicable: "Before you remove the pump, close the isolation valve." Omitting articles also breaks Rule 4.2.`

---

## Section 5 — Procedural writing

### Rule 5.1 — Procedural sentences: 20 words at most

**RED:**

> If the pressure gauge reading is above the maximum specified value in the maintenance manual, close the isolation valve and notify the maintenance controller immediately.

**GREEN:**

> If the pressure gauge shows more than the maximum specified value in the maintenance manual, do these steps:
>
> 1. Close the isolation valve.
> 2. Tell the maintenance controller immediately.

**Expected finding:** `[5.1] This procedural sentence has 25 words. The maximum is 20. Divide it into shorter sentences. Also: it has two instructions (Rule 5.2); "reading" is an "-ing" form (Rule 3.5) and reading (n) is not approved (→ INDICATION, p.350), and here the approved verb SHOW gives the same information more clearly ("the pressure gauge shows", SHOW (v), p.377; Rule 3.7, p.75); "above" is for physical positions only, so for a limit use MORE THAN (Rule 9.2, p.150); "notify" is not approved (→ TELL, p.318).`

---

### Rule 5.1 — Procedural sentences: 20 words at most (description in a procedure)

**RED:**

> The drain valve lets water and unwanted material flow out of the fuel tank when the aircraft is on a level surface.
>
> 1. Open the drain valve slowly with the special tool until fuel that has no water and no unwanted material flows into the container.

**GREEN:**

> The drain valve lets water and unwanted material flow out of the fuel tank when the aircraft is on a level surface.
>
> 1. Open the drain valve slowly with the special tool. Continue until fuel that has no water and no unwanted material flows into the container.

**Expected finding:** `[5.1] Step 1 has 23 words. The maximum is 20. Divide it into two sentences in one work step, because the actions occur at the same time (p.88). Do not flag the first sentence: it describes an item and gives no instruction, so it is descriptive writing (p.95). Its limit is 25 words (Rule 6.3), and it has 22 words.`

---

### Rule 5.2 — One instruction per sentence, except for simultaneous actions (sentence)

**RED:**

> Open the valve and check the pressure.

**GREEN:**

> 1. Open the valve.
> 2. Do a check of the pressure.

**Expected finding:** `[5.2] One sentence contains two instructions ("Open the valve" and "check the pressure"), and the actions do not occur at the same time. Write each instruction in a separate sentence and show the sequence. Also [1.2]: "check" is approved as a noun only (p.189): "do a check of the pressure".`

---

### Rule 5.2 — One instruction per sentence, except for simultaneous actions (work step)

**RED:**

> 1. Remove the cover and disconnect the electrical connector.

**GREEN:**

> 1. Remove the cover.
> 2. Disconnect the electrical connector.

**Expected finding:** `[5.2] Step 1 contains two instructions ("Remove the cover" and "disconnect the electrical connector") that do not occur at the same time. Divide them into two work steps.`

---

### Rule 5.3 — Phrase each instruction as an imperative

**RED (procedural; the reader is the operator):**

> The operator must remove the access panel.

**GREEN:**

> Remove the access panel.

**Expected finding:** `[5.3] "The operator must remove" is not the imperative. Write the instruction in the imperative: "Remove the access panel."`

---

### Rule 5.3 — Phrase each instruction as an imperative ("you should")

**RED:**

> You should clean the filter with a soft brush.

**GREEN:**

> Clean the filter with a soft brush.

**Expected finding:** `[5.3] "You should clean" is not the imperative. Write the instruction in the imperative: "Clean the filter with a soft brush." Also [1.1]: should (v) is not approved (→ MUST (v), IF (conj), p.377), but do not write "You must clean": do not use "must" before the imperative unless the instruction is very important for safety or gives an important condition (p.89-90).`

---

### Rule 5.4 — Put a condition the reader needs first at the start, as a descriptive clause set off from the command by a comma

**RED:**

> Stop the pump if the temperature exceeds 80 °C.

**GREEN:**

> If the temperature is more than 80 °C, stop the pump.

**Expected finding:** `[5.4] The command ("Stop the pump") comes before the condition ("if the temperature exceeds 80 °C"). Put the condition first and divide it from the command with a comma: "If …, stop the pump." Also [1.1]: exceed (v) is not approved (→ MORE THAN, p.238).`

---

## Section 6 — Descriptive writing

### Rule 6.3 — Descriptive sentences: 25 words at most

**RED:**

> The fuel system consists of a series of interconnected components including the fuel tank, the low-pressure pump, the high-pressure pump, the fuel filters, the fuel metering unit, and the associated pipes and valves that connect these components together.

**GREEN:**

> The fuel system has these components:
>
> - The fuel tank
> - The low-pressure pump
> - The high-pressure pump
> - The fuel filters
> - The fuel metering unit
> - The pipes and the valves that connect these components together.

**Expected finding:** `[6.3] This descriptive sentence has 38 words. The maximum is 25. Use a vertical list (Rule 4.3). Also [1.1]: "consists of" is not approved (→ HAVE, p.200: "The fuel system has these components:"); "including" is not approved (→ THRU or WITH, p.280); "associated" is not approved (→ CORRECT, RELATED, ITS, or THEIR, p.169); "interconnected" is not approved (interconnect (v) → CONNECT, p.287); "series" is not in the dictionary and is not a technical noun here.`

---

### Rule 6.4 — Group related information into paragraphs (topic sentence first)

**RED:**

> The pump supplies oil to the bearings. The filter removes particles from the oil. The cooler keeps the oil temperature low. The lubrication system has three primary parts.

**GREEN:**

> The lubrication system has three primary parts. The pump supplies oil to the bearings. The filter removes particles from the oil. The cooler keeps the oil temperature low.

**Expected finding:** `[6.4] The paragraph does not start with a topic sentence. The last sentence states the topic (the three primary parts of the lubrication system), and the other sentences describe each part: put the topic sentence first.`

---

### Rule 6.6 — Six sentences at most per paragraph

**RED:**

> The hydraulic system supplies power to the flight control surfaces. It consists of a reservoir, 2 pumps, and a set of actuators. The primary pump operates continuously when the engine runs. If the primary pump fails, the secondary pump starts automatically. The hydraulic system includes a pressure relief valve that limits maximum pressure. The actuators change hydraulic pressure to mechanical motion. The hydraulic system is monitored by a set of sensors that send data to the flight management system.

**GREEN:**

> The hydraulic system supplies power to the flight control surfaces. It has a reservoir, 2 pumps, and a set of actuators. The primary pump operates continuously when the engine operates. If a failure of the primary pump occurs, the secondary pump starts automatically. The hydraulic system includes a pressure relief valve that does not let the pressure become more than the maximum. The actuators change hydraulic pressure to mechanical movement.
>
> A set of sensors monitors the hydraulic system and sends data to the flight management system.

**Expected finding:** `[6.6] The paragraph has 7 sentences. The maximum is 6. Divide it into two paragraphs. Also: the last sentence is passive with a known agent ("by a set of sensors"), so make it active (Rule 3.6). These words are not approved (Rule 1.1, 1.2): "consists" (→ HAVE, p.200), "runs" (→ OPERATE, p.365), "fails" (for equipment → FAILURE (TN): "a failure of … occurs", p.246), "limits" (LIMIT is a noun only, p.299), "motion" (→ MOVEMENT, p.313).`

---

## Section 7 — Safety instructions

### Rule 7.1 — Mark the risk level with a signal word such as "warning" or "caution" (warning, not note)

**RED:**

> NOTE: DO NOT TOUCH THE SURFACE UNTIL IT IS COOL. THE SURFACE IS HOT AFTER OPERATION. A HOT SURFACE CAN BURN YOU.

**GREEN:**

> WARNING: DO NOT TOUCH THE SURFACE UNTIL IT IS COOL. THE SURFACE IS HOT AFTER OPERATION. A HOT SURFACE CAN BURN YOU.

**Expected finding:** `[7.1] A risk of injury (burns) needs a warning, not a note (p.104). Change "NOTE" to "WARNING". Also [5.5]: a note must not give an instruction, and information that prevents injury goes in a safety instruction (p.91-92).`

---

### Rule 7.1 — Mark the risk level with a signal word such as "warning" or "caution" (caution, not warning)

**RED:**

> WARNING: DO NOT TORQUE THE SENSOR CONNECTOR TO MORE THAN 5 Nm. TOO MUCH TORQUE DAMAGES THE SENSOR CONNECTOR.
> (The risk is damage to equipment only. There is no risk of injury.)

**GREEN:**

> CAUTION: DO NOT TORQUE THE SENSOR CONNECTOR TO MORE THAN 5 Nm. TOO MUCH TORQUE CAUSES DAMAGE TO THE SENSOR CONNECTOR.

**Expected finding:** `[7.1] The risk is damage to equipment only, so use a caution, not a warning (p.104). Keep "warning" for a risk of injury or death. Also [1.2]: "DAMAGES" uses damage as a verb, but DAMAGE is approved as a noun only (p.207): "CAUSES DAMAGE TO".`

---

### Rule 7.2 — Open a safety instruction with a precise command or condition

**RED:**

> WARNING: FUEL IS FLAMMABLE. KEEP ALL IGNITION SOURCES AWAY FROM THE WORK AREA. FUEL FIRES CAN CAUSE INJURY OR DEATH.
>
> 1. Drain the fuel tank.

**GREEN:**

> WARNING: KEEP ALL IGNITION SOURCES AWAY FROM THE WORK AREA. FUEL IS FLAMMABLE. FUEL FIRES CAN CAUSE INJURY OR DEATH.
>
> 1. Drain the fuel tank.

**Expected finding:** `[7.2] The WARNING starts with a statement ("FUEL IS FLAMMABLE"), not with a command or a condition. Start with the command: "KEEP ALL IGNITION SOURCES AWAY FROM THE WORK AREA." Then give the explanation of the risk (Rule 7.3).`

---

### Rule 7.3 — Explain the risk or the likely consequence

**RED:**

> WARNING: DO NOT PUT YOUR HAND IN THE FAN DUCT.
> (The source gives this command only. It gives no risk or possible result.)

**GREEN:**

> WARNING: DO NOT PUT YOUR HAND IN THE FAN DUCT. [needs: risk or result]
>
> **Gaps**
>
> - `[needs: risk or result]` in the WARNING. The source gives no risk or possible result.

**Expected finding:** `[7.3] The WARNING has a command but no explanation of the risk or possible result. The source does not give one, so do not write one yourself (for example, do not add "THE FAN CAN CAUSE INJURY"). Write [needs: risk or result] after the command and list it under Gaps. A safety instruction that starts with a command and has no condition obeys Rule 7.2 (p.105): do not add [needs: condition]. WARNING already identifies a risk of injury (Rule 7.1, p.104): do not add [needs: level of risk].`

---

## Section 8 — Punctuation and word count

### Rule 8.1 — Any standard English punctuation mark is permitted except the semicolon (;)

**RED:**

> The pump has two outlets; the smaller outlet supplies the brakes.

**GREEN:**

> The pump has two outlets. The smaller outlet supplies the brakes.

**Expected finding:** `[8.1] The semicolon is not permitted. Write two sentences: "The pump has two outlets. The smaller outlet supplies the brakes."`

---

### Rule 8.2 — Hyphenate (-) words that belong closely together

**RED:**

> Put a heat resistant sleeve on the hose.

**GREEN:**

> Put a heat-resistant sleeve on the hose.

**Expected finding:** `[8.2] "heat resistant" is a two-word adjective before the noun "sleeve". Connect words that are directly related with a hyphen: "heat-resistant sleeve" (p.108).`

---

## House style

These rules are house style, not ASD-STE100 (`references/house-style.md`).
Each finding is tagged `[House style HS-n]`.

### House style HS-1: No em dash or en dash

**RED:**

> When the pressure is high, the relief valve opens — this prevents damage to the pump.

**GREEN:**

> When the pressure is high, the relief valve opens. This prevents damage to the pump.

**Expected finding:** `[House style HS-1] The em dash (—) divides two ideas. Write a separate sentence: "When the pressure is high, the relief valve opens. This prevents damage to the pump." Do not use a semicolon instead (Rule 8.1). Issue 9 permits the dash (Rule 8.1, p.108), so this is a house-style finding, not an STE finding.`

---

### House style HS-2: No slash for "and" or "or"

**RED:**

> Put the rags in the metal container/fire-resistant bag.
> (The source permits either item.)

**GREEN:**

> Put the rags in the metal container or the fire-resistant bag.

**Expected finding:** `[House style HS-2] The slash in "metal container/fire-resistant bag" means "or". Write "or": "Put the rags in the metal container or the fire-resistant bag." Issue 9 permits the slash (Rule 8.1, p.108), so this is a house-style finding, not an STE finding.`

---

### House style HS-3: Numbers as figures for quantities

**RED:**

> Attach the cover with eight bolts.

**GREEN:**

> Attach the cover with 8 bolts.

**Expected finding:** `[House style HS-3] "eight" is a quantity written as a word. Write it as a figure: "Attach the cover with 8 bolts." Issue 9 permits number words (Rule 8.2, p.108; Rule 8.6 examples, p.111), so this is a house-style finding, not an STE finding.`

---

### House style HS-4: Units with the number

**RED:**

> Torque the bolt to 40Nm.

**GREEN:**

> Torque the bolt to 40 Nm.

**Expected finding:** `[House style HS-4] "40Nm" has no space between the number and the unit symbol: write "40 Nm". STE does not choose how units are shown (p.36), so this is a house-style finding, not an STE finding.`

---

### House style HS-5: Standard abbreviations only

**RED:**

> Remove the oil pressure switch (OPS). Examine the OPS for damage.
> (The parts catalog gives "oil pressure switch" as the technical noun. The applicable specification and the company glossary do not list "OPS".)

**GREEN:**

> Remove the oil pressure switch. Examine the oil pressure switch for damage.

**Expected finding:** `[House style HS-5] "OPS" is not a standard abbreviation: the applicable specification and the company glossary do not list it, and it is not an abbreviation in wide general technical use. The source gives the full term, so write it in full: "Examine the oil pressure switch for damage." Issue 9 permits an abbreviation in parentheses (Rule 8.3, p.109) and gives no rules for abbreviations (p.36). "oil pressure switch" has three words, so Rule 2.1 permits it, and Rule 2.2 does not apply: a technical noun of three words or fewer needs no abbreviation (p.65). Thus this is a house-style finding, not an STE finding.`

---

### House style HS-6: Uppercase warnings and cautions

**RED:**

> Caution: Do not use a metal scraper on the lens. A metal scraper can cause damage to the lens.

**GREEN:**

> CAUTION: DO NOT USE A METAL SCRAPER ON THE LENS. A METAL SCRAPER CAN CAUSE DAMAGE TO THE LENS.

**Expected finding:** `[House style HS-6] The caution is not in uppercase letters. Write all of it in uppercase, including the signal word. STE does not give rules for formatting (p.104), so this is a house-style finding, not an STE finding. The caution already obeys Rules 7.1 to 7.3.`

---

### House style HS-7: Fixed format for warnings and cautions

**RED:**

> WARNING: LET THE ENGINE BECOME COOL. HOT OIL CAN BURN YOU. PUT ON HEAT-RESISTANT GLOVES.

**GREEN:**

> WARNING: LET THE ENGINE BECOME COOL. PUT ON HEAT-RESISTANT GLOVES. HOT OIL CAN BURN YOU.

**Expected finding:** `[House style HS-7] A command ("PUT ON HEAT-RESISTANT GLOVES.") comes after the explanation ("HOT OIL CAN BURN YOU."). Put all the commands first and the explanation last. The warning starts with a command and has an explanation, so it obeys Rules 7.2 and 7.3 (p.105-106): this is a house-style finding, not an STE finding. The source gives no condition, so do not add one or a [needs: condition].`

---

### House style HS-8: Warnings and cautions before their step

**RED:**

> 1. Remove the battery.
> 2. Disconnect the power cable.
>    WARNING: REMOVE THE BATTERY BEFORE YOU DISCONNECT THE POWER CABLE. THE POWER CABLE HAS VOLTAGE UNTIL YOU REMOVE THE BATTERY. ELECTRICAL SHOCK CAN CAUSE DEATH.

**GREEN:**

> WARNING: REMOVE THE BATTERY BEFORE YOU DISCONNECT THE POWER CABLE. THE POWER CABLE HAS VOLTAGE UNTIL YOU REMOVE THE BATTERY. ELECTRICAL SHOCK CAN CAUSE DEATH.
>
> 1. Remove the battery.
> 2. Disconnect the power cable.

**Expected finding:** `[House style HS-8] The WARNING comes after the work steps that it applies to. Its command is the action of step 1, so put it before step 1. No Issue 9 rule says where a safety instruction goes (Rules 7.1 to 7.3, p.103-106), so this is a house-style finding, not an STE finding.`

---

## Tests dropped

The realignment to Issue 9 removed these tests.
Each tested a rule that the skill had enforced but that Issue 9 does not contain, and its RED breaks no Issue 9 rule, so no retarget was possible.

| Test | Old rule | Why dropped |
|---|---|---|
| "Remove the engine oil filter." | 2.2 Multi-word noun must be clear | Issue 9 Rule 2.2 is about technical nouns of more than three words (p.64). "engine oil filter" has three words, which Rule 2.1 permits (p.63). |
| WARNING after the power-cable step | 5.3 Warning before the step it applies to | No Issue 9 rule says where a safety instruction goes (Rules 5.5, 7.1 to 7.3, p.91-106). STE gives no rules for formatting (p.36, p.104). Restored as house style: see House style HS-8, with the WARNING changed to start with its command (Rule 7.2). |
| Pump modes "it can run continuously, a standby mode, and emergency starting" | 6.3 Parallel structure | Issue 9 has no parallel-structure rule. Its Rule 6.3 is the 25-word limit (p.98). |
| "light-weight fixture" | 8.4 Hyphen only where the Dictionary approves it | Issue 9 has no such rule. Rule 8.2 tells you to hyphenate a two-word adjective before a noun (p.108), so the RED obeys it. |
| "Tighten the bolt to 30 Nm (this is the minimum value)." | 8.3 No parentheses for a second idea | Issue 9 Rule 8.3 permits parentheses "to explain words or a part of a sentence" (p.109-110). |
| "set" for a value and for a switch position | 9.3 Same word not for two different things | Issue 9 has no such rule. Its Rule 9.3 is about phrasal verbs (p.121). SET (v) has one approved meaning that covers the two uses (p.374). |

Three other tests of removed rules were retargeted to an Issue 9 rule that their RED breaks: figures for quantities (old 6.5) is now Rule 1.14, warning placement (old 7.1) is now Rule 7.2, and the mandatory hazard condition (old 7.3) is now the Rule 7.3 `[needs: risk or result]` test.
Figures for quantities and warning placement are also tested again as house style (House style HS-3 and HS-8).

## Verification Log

**Verified 2026-10-22.** Result: **41/41 passed.** Graded by an Opus agent reading `SKILL.md`, `references/rules.md`, `references/word-choices.md`, `references/checklist.md`, and `references/house-style.md` as the only source for the skill, its rules, pages, and dictionary entries, and `TESTS.md`, with no edit to either file afterwards. No copy of the ASD standard was used: every Expected finding and rule detail was checked in `SKILL.md` or `references/`; a cited dictionary page that the references do not contain (for example CENTER (TN), p.187, or SHOW (v), p.377) was accepted where the finding's substance could be checked from the references. Rule 2.2's shorter form, abbreviation, and hyphens were graded as options, not duties. The Rule 1.14 and Rule 7.1 (caution) tests and the HS-6 example use the verb TORQUE (TORQUE (v), p.406); "Apply a torque of 25 ±2 Nm." in Rule 4.1 keeps the noun, a technical noun (Rule 1.5, category 7). Sections 1 to 8 were graded with house style off; the House style tests were graded with HS-1 to HS-8 applied after the Issue 9 check. A "Context:" line or a parenthetical scenario note was read as scenario information, not as text under test. The worked examples in `SKILL.md` and `references/` were also checked against the skill's own rules, and none breaks them. The previous log's notes were not used; every test was graded from scratch.

Produced against `TESTS.md` body sha256 `be98045881a7c57a`, `SKILL.md` sha256 `c0c931d650d7843f`, `references/checklist.md` sha256 `e0ada7e4fd35c647`, `references/house-style.md` sha256 `a07b2cb8a6a31d07`, `references/rules.md` sha256 `67a6308d4aaf2485`, and `references/word-choices.md` sha256 `41164cf4c524654c` (the 4 files concatenated in filename order digest to `cc5361eaded48d0c`). The body hash covers everything above this heading, so it survives this log being written. Recompute every hash before trusting the rows: any later edit invalidates them.

| Test                                                        | RED flags | GREEN clean | Pass |
|-------------------------------------------------------------|-----------|-------------|------|
| Rule 1.1 — Approved words, technical nouns, technical verbs | ✓         | ✓           | PASS |
| Rule 1.1 — Approved words ("shall")                         | ✓         | ✓           | PASS |
| Rule 1.1 — Approved words ("should")                        | ✓         | ✓           | PASS |
| Rule 1.2 — Specified part of speech ("test")                | ✓         | ✓           | PASS |
| Rule 1.2 — Specified part of speech ("light")               | ✓         | ✓           | PASS |
| Rule 1.3 — Approved meanings only                           | ✓         | ✓           | PASS |
| Rule 1.5 — Technical noun category (quoted text)            | ✓         | ✓           | PASS |
| Rule 1.11 — One technical noun for one item                 | ✓         | ✓           | PASS |
| Rule 1.12 — Technical verb category                         | ✓         | ✓           | PASS |
| Rule 1.14 — American English spelling                       | ✓         | ✓           | PASS |
| Rule 2.1 — Multi-word nouns of no more than three words     | ✓         | ✓           | PASS |
| Rule 3.5 — "-ing" form only in a technical noun             | ✓         | ✓           | PASS |
| Rule 3.6 — Active voice                                     | ✓         | ✓           | PASS |
| Rule 3.7 — Approved verb, not a noun                        | ✓         | ✓           | PASS |
| Rule 4.1 — Short and clear sentences (be accurate)          | ✓         | ✓           | PASS |
| Rule 4.2 — Do not omit words                                | ✓         | ✓           | PASS |
| Rule 4.5 — Articles and demonstrative adjectives            | ✓         | ✓           | PASS |
| Rule 5.1 — Procedural sentences: 20 words maximum           | ✓         | ✓           | PASS |
| Rule 5.1 — 20 words maximum (description in a procedure)    | ✓         | ✓           | PASS |
| Rule 5.2 — One instruction in each sentence (sentence)      | ✓         | ✓           | PASS |
| Rule 5.2 — One instruction in each sentence (work step)     | ✓         | ✓           | PASS |
| Rule 5.3 — Imperative form                                  | ✓         | ✓           | PASS |
| Rule 5.3 — Imperative form ("you should")                   | ✓         | ✓           | PASS |
| Rule 5.4 — Condition first                                  | ✓         | ✓           | PASS |
| Rule 6.3 — Descriptive sentences: 25 words maximum          | ✓         | ✓           | PASS |
| Rule 6.4 — Paragraphs (topic sentence first)                | ✓         | ✓           | PASS |
| Rule 6.6 — No more than six sentences in a paragraph        | ✓         | ✓           | PASS |
| Rule 7.1 — Level of risk (warning, not note)                | ✓         | ✓           | PASS |
| Rule 7.1 — Level of risk (caution, not warning)             | ✓         | ✓           | PASS |
| Rule 7.2 — Start with a command or condition                | ✓         | ✓           | PASS |
| Rule 7.3 — Risk or possible result (none in the source)     | ✓         | ✓           | PASS |
| Rule 8.1 — No semicolon                                     | ✓         | ✓           | PASS |
| Rule 8.2 — Hyphens for directly related words               | ✓         | ✓           | PASS |
| House style HS-1 — No em dash or en dash                    | ✓         | ✓           | PASS |
| House style HS-2 — No slash for "and" or "or"               | ✓         | ✓           | PASS |
| House style HS-3 — Figures for quantities                   | ✓         | ✓           | PASS |
| House style HS-4 — Units with the number                    | ✓         | ✓           | PASS |
| House style HS-5 — Standard abbreviations only              | ✓         | ✓           | PASS |
| House style HS-6 — Uppercase warnings and cautions          | ✓         | ✓           | PASS |
| House style HS-7 — Fixed format for warnings and cautions   | ✓         | ✓           | PASS |
| House style HS-8 — Warnings and cautions before their step  | ✓         | ✓           | PASS |

Counts were checked with a Python split under Rules 8.4 to 8.7 (a hyphenated word is one word, a number with its unit is one word): 5.1 RED 25 words and its GREEN 18 before the colon; the description-in-a-procedure step 23, its descriptive sentence 22, and its GREEN sentences 9 and 15; 6.3 RED 38; the 2.1 multi-word noun 8; 6.6 RED 7 sentences, its first GREEN paragraph 6 (longest 19 words); 41 Expected findings in all.

# SCR Narrative Skill — Red/Green Test Suite

Each test has:

- **RED:** draft with a specific SCR failure (should be flagged)
- **GREEN:** corrected SCR
- **Expected finding:** what the skill should identify and fix

---

## Build

### B1 — Build draft invents facts the brief never gave

**RED:**

> Brief: The operations committee must decide whether to add a second telephony carrier for the incident hotline. The current carrier dropped calls during two regional outages this year, and each time callers heard a busy tone. The committee wants a recommendation it can approve.
>
> SITUATION
> The incident hotline handles 3,200 calls a month through a single telephony carrier.
>
> COMPLICATION
> The carrier dropped calls during two regional outages this year, leaving callers on a busy tone for up to 40 minutes.
>
> RESOLUTION
> The Head of Operations must sign a second carrier for the hotline by 30 November.

**GREEN:**

> SITUATION
> The incident hotline runs on a single telephony carrier.
>
> COMPLICATION
> The carrier dropped calls during two regional outages this year, and each time callers heard a busy tone.
>
> RESOLUTION
> The operations committee must approve a second telephony carrier for the incident hotline by [needs: date].

**Expected finding:** `[Facts — invented detail] "3,200 calls a month," "up to 40 minutes," "The Head of Operations," and "by 30 November" appear nowhere in the brief. Use only the facts you were given. The brief names the committee as the body that decides, so it owns the Resolution; the missing date becomes [needs: date] and is listed under Gaps. Keep the brief's own wording for the outages rather than adding a figure.`

---

## Structure

### X1 — Memo with no Complication, mapped from its headings

**RED:**

> **Background**
> The records team scans paper claim forms at one site in Leeds. Two scanners run a single day shift. Scanned forms reach the claims system the same day. The team has used this setup since 2022.
>
> **Proposal**
> The Records Manager leases a third scanner and adds an evening shift from 1 February.

**GREEN:**

> SITUATION
> The records team scans paper claim forms at one site in Leeds. Two scanners run a single day shift.
>
> COMPLICATION
> [needs: the pressure that makes a third scanner and an evening shift necessary now]
>
> RESOLUTION
> The Records Manager leases a third scanner and adds an evening shift from 1 February.

**Expected finding:** `[Structure — element missing] Mapping, with the sentences treated as each element. Situation, from Background: "The records team scans paper claim forms at one site in Leeds. Two scanners run a single day shift." Resolution, from Proposal: "The Records Manager leases a third scanner and adds an evening shift from 1 February." Complication: nothing maps to it. The memo never says why the current setup cannot continue, so the Proposal has nothing to answer. Report the gap first and ask for the pressure; do not invent one, and do not fault the Proposal for it. The 2 quoted Background sentences are the baseline the Proposal changes (the scanners and the shift), and 2 sentences is within the limit, so no length finding applies. Background's other 2 sentences are section detail, not the spine, and stay in the memo. The corrected SCR goes in the labelled block, with [needs: …] in place of the Complication and listed under Gaps.`

---

## Situation

### S1 — Situation smuggles in the complication

**RED:**

> SITUATION
> Crew licence revalidation is unreliable and slow, which leaves the airline exposed to sudden shortages.

**GREEN:**

> SITUATION
> [needs: a verifiable fact about how crew licences are revalidated]

**Expected finding:** `[Situation — problem smuggled in] "Unreliable and slow, which leaves the airline exposed" is a problem statement, not a neutral baseline fact. The Situation must be something the audience already accepts as true with no resistance — it establishes shared ground, not the argument. Move the problem to the Complication; restate the Situation as a verifiable structural fact. The draft supplies no such fact, so write [needs: …] in its place rather than inventing one.`

---

### S2 — Situation too narrow (doesn't cover what the audience cares about)

**RED:**

> SITUATION
> The training office has been cleaning up its revalidation spreadsheet since June.

**GREEN:**

> SITUATION
> [needs: what revalidation controls and what a lapse costs]

**Expected finding:** `[Situation — too narrow] The Situation describes internal team activity, not the environment the audience needs to understand. The audience needs the stakes — what revalidation controls and what it costs when it lapses — not the office's workload. The clean-up also implies a problem, which the Situation must not carry, so drop it from the Situation; it can return in the Complication once the draft says what problem the clean-up answers. Broaden the Situation to establish the facts the Complication will disrupt. Where the draft does not supply the detail, write [needs: …] in its place rather than inventing it.`

---

### S3 — Present tense used for a historical fact

**RED:**

> SITUATION
> In 2021, the training office tracks revalidation dates in a shared spreadsheet.

**GREEN:**

> SITUATION
> In 2021, the training office tracked revalidation dates in a shared spreadsheet.

**Expected finding:** `[Situation — wrong tense] Present tense ("tracks") is used for a specific historical event. Use past tense for historical events; reserve present tense for standing facts that are still true today.`

---

### S4 — Scheduled future fact, plan estimate, and present perfect

**GREEN:**

> SITUATION
> The new terminal will open on 3 March, and planning assumes approximately 4,000 departing passengers a day in its first month. Since 2024, the airport has run check-in through a single shared-desk system.

**Expected finding:** `(No finding — "will open on 3 March" is a scheduled future event the audience accepts, "has run" is present perfect for a state that continues, and "approximately 4,000" is a labeled plan figure. All three fit the Situation criteria. Do not change the tenses, and keep "approximately".)`

---

## Complication

### C1 — Complication is a vague trend

**RED:**

> COMPLICATION
> Aviation compliance expectations keep rising, and operators everywhere face more scrutiny than they used to.

**GREEN:**

> COMPLICATION
> [needs: the specific deadline, gap, or event that makes compliance urgent now]

**Expected finding:** `[Complication — vague trend] "Compliance expectations keep rising" and "operators everywhere face more scrutiny" are a vague trend, not a specific pressure. A Complication must be specific: a deadline, a gap, a constraint, an event, a conflict, or a risk now materializing. The audience must be unable to defer — if they can live with this, the Complication is not strong enough. The draft names no pressure, only a trend, so there is no wording to keep: replace the Complication with [needs: …] for the specific pressure rather than inventing one. The trend can move to supporting detail.`

---

### C2 — Complication not grounded in the Situation

**RED:**

> SITUATION
> The airline employs 480 flight crew and revalidates each licence every 12 months.
>
> COMPLICATION
> Fuel costs across the sector rose 14% last year, squeezing margins on regional routes.

**GREEN:**

> SITUATION
> The airline employs 480 flight crew and revalidates each licence every 12 months.
>
> COMPLICATION
> [needs: the pressure the 12-month revalidation cycle has run into]

**Expected finding:** `[Complication — not grounded in Situation] The Complication (sector fuel costs) introduces a new fact with no connection to the Situation (480 crew on a 12-month revalidation cycle). The Complication must follow logically from the Situation — it is what the Situation has run into. Replace it with a Complication that follows from the revalidation cycle described above. Where the draft does not supply the detail, write [needs: …] in its place rather than inventing it.`

---

### C3 — Two complications stacked without choosing the sharper one

**RED:**

> COMPLICATION
> First, eleven crew lost currency last quarter because the spreadsheet is invisible to the roster. Additionally, the training office expects two of its four schedulers to retire within the next three years.

**GREEN:**

> COMPLICATION
> Eleven crew lost currency last quarter because the spreadsheet is invisible to the roster.

**Expected finding:** `[Complication — two complications stacked] Two separate complications are presented without choosing the stronger one: lapses the roster cannot see and scheduler retirements would each need a different Resolution. Keep the lapses: eleven crew have already lost currency, which is a risk now materializing, while retirements up to three years away are a pressure the audience can defer. The retirements can appear in supporting detail if relevant. A stacked Complication dilutes the narrative tension.`

---

### C4 — Complication cites a table that holds the figure

**RED:**

> COMPLICATION
> Call volume now exceeds what the night desk can answer, as Table 2 shows.
>
> | Month | Calls received | Calls the desk can answer |
> |---|---|---|
> | April | 1,900 | 2,000 |
> | May | 2,450 | 2,000 |
> | June | 2,700 | 2,000 |

**GREEN:**

> COMPLICATION
> Since May, call volume has exceeded what the night desk can answer, by up to 700 calls a month (Table 2).
>
> | Month | Calls received | Calls the desk can answer |
> |---|---|---|
> | April | 1,900 | 2,000 |
> | May | 2,450 | 2,000 |
> | June | 2,700 | 2,000 |

**Expected finding:** `[Complication — figure not inline] "Exceeds what the night desk can answer" reads as vague on its own, but Table 2, which the sentence cites, holds the figure: calls exceeded capacity by 450 in May and 700 in June. Read the cited table before judging specificity. The fix is to state the figure inline, not to flag a vague trend or invent a number.`

---

### C5 — A deadline and a lead time make one Complication

**GREEN:**

> SITUATION
> The depot buys forklift batteries from one supplier, and 22 forklifts run on them each shift.
>
> COMPLICATION
> The supplier closes the plant that makes the depot's batteries on 31 May. Qualifying a new supplier takes at least 16 weeks, so the depot will have no source of replacement batteries for several weeks after the closure.
>
> RESOLUTION
> The Depot Manager orders a three-month battery buffer from the current supplier by 30 April, and Procurement starts qualifying a new supplier by the same date.

**Expected finding:** `(No finding — this is one Complication, not two stacked. The plant closure is the trigger and the qualification lead time turns it into a supply gap; neither fact alone would justify the Resolution. Do not flag stacking or drop either fact.)`

---

### C6 — A bounded warning with a range and "may"

**GREEN:**

> SITUATION
> The self-checkout tills for the new store come from one manufacturer, and 30 tills are due for installation in June.
>
> COMPLICATION
> The manufacturer has warned that between 8 and 12 tills may arrive up to four weeks late, which would leave the store short of tills for its opening weekend.
>
> RESOLUTION
> The Store Operations Lead approves temporary staffed tills at the new store for the opening weekend by 15 May.

**Expected finding:** `(No finding — the manufacturer's warning is a specific risk now materializing, even though it says "may" and gives a range. Do not flag urgency. Any rewrite keeps "between 8 and 12," "may," and "up to four weeks"; "12 tills will arrive four weeks late" would harden the claim.)`

---

## Resolution

### R1 — Resolution too broad

**RED:**

> RESOLUTION
> The airline should implement a comprehensive strategy to strengthen crew compliance across all fleets.

**GREEN:**

> RESOLUTION
> [needs: owner at the airline] should make [needs: the specific change that strengthens crew compliance] across all fleets by [needs: date].

**Expected finding:** `[Resolution — too broad] "Implement a comprehensive strategy to strengthen crew compliance" names the concept, not the specific intervention. The Resolution must name the specific intervention. "Comprehensive strategy" is not something an executive can approve. Where the draft does not supply the change, write [needs: …] in its place rather than inventing it. [Resolution — owner and timing missing] "The airline" is the organisation as a whole, not an owner, and the draft gives no timing; write [needs: owner at the airline] and [needs: date] and list both under Gaps.`

---

### R2 — Resolution stated as a principle, not an action

**RED:**

> RESOLUTION
> The airline should take a more joined-up view of training and rostering.

**GREEN:**

> RESOLUTION
> [needs: owner at the airline] should make [needs: the specific change that links training and rostering] by [needs: date].

**Expected finding:** `[Resolution — principle not action] "Take a more joined-up view" is a disposition, not an action. The Resolution must name a specific intervention. Replace the principle with a change the audience can approve and track. Where the draft does not supply the change, write [needs: …] in its place rather than inventing it. [Resolution — owner and timing missing] "The airline" is the organisation as a whole, not an owner, and the draft gives no timing; write [needs: owner at the airline] and [needs: date] and list both under Gaps.`

---

### R3 — Resolution doesn't address the complication

**RED:**

> COMPLICATION
> Eleven crew lost currency last quarter because revalidation dates are invisible to the roster.
>
> RESOLUTION
> The airline should invest in a communications campaign to raise awareness of compliance obligations.

**GREEN:**

> COMPLICATION
> Eleven crew lost currency last quarter because revalidation dates are invisible to the roster.
>
> RESOLUTION
> [needs: owner at the airline] should make revalidation dates visible to the roster by [needs: date].

**Expected finding:** `[Resolution — misses the Complication] The Complication is about lapses the roster cannot see; the Resolution addresses awareness of obligations. These do not match. The Resolution must be the direct logical response to the specific tension the Complication introduced. Cover the Situation; Complication + Resolution must read as a complete argument with nothing missing. The corrected Resolution reverses the cause the Complication states (dates invisible to the roster become dates visible to it), which adds no fact. [Resolution — owner and timing missing] "The airline" is the organisation as a whole, not an owner, and the draft gives no timing; write [needs: owner at the airline] and [needs: date] and list both under Gaps.`

---

### R4 — Resolution introduces ideas not set up in S or C

**RED:**

> SITUATION
> The airline runs recurrent crew training at two bases, each with its own simulator schedule.
>
> COMPLICATION
> The simulator at the second base is booked to capacity through the summer, so 40 crew cannot finish recurrent training before their checks expire.
>
> RESOLUTION
> The airline must add simulator capacity at the second base, restructure the training department under a single head, and introduce a new competency framework.

**GREEN:**

> SITUATION
> The airline runs recurrent crew training at two bases, each with its own simulator schedule.
>
> COMPLICATION
> The simulator at the second base is booked to capacity through the summer, so 40 crew cannot finish recurrent training before their checks expire.
>
> RESOLUTION
> [needs: owner at the airline] must add simulator capacity at the second base by [needs: date], so the 40 crew can finish recurrent training before their checks expire.

**Expected finding:** `[Resolution — scope creep] "Restructure the training department under a single head" and "introduce a new competency framework" were not set up in the Situation or Complication. The Resolution must address only what was established above it. Move the restructure and the framework to supporting documents — the SCR Resolution names the move, not the full implementation plan. [Resolution — owner and timing missing] "The airline" is the organisation as a whole, not an owner, and the draft names no timing. Write [needs: owner at the airline] and [needs: date]. The Complication's deadline, before the 40 crew's checks expire, is not the Resolution's date: it stays as the reason for the date and does not replace it.`

---

### R5 — Resolution has no owner or timing, and the draft supplies none

**RED:**

> RESOLUTION
> Adding a licence-expiry check to the monthly roster would keep lapsed pilots off flights.

**GREEN:**

> RESOLUTION
> [needs: owner] adds a licence-expiry check to the monthly roster by [needs: date], which would keep lapsed pilots off flights.

**Expected finding:** `[Resolution — owner and timing missing] "Adding a licence-expiry check to the monthly roster" names the action but not who acts or by when, and the draft supplies neither. A Resolution with no owner and no timing is not something an audience can approve. Do not invent them: write [needs: owner] and [needs: date] in their place and list both under Gaps.`

---

## Tone and Language

### T1 — Prohibited language in SCR elements

**RED:**

> SITUATION
> Operators are increasingly leveraging digital tools in this rapidly evolving landscape.
>
> COMPLICATION
> The situation has become crucial, with pivotal decisions ahead that will be transformative for all stakeholders.
>
> RESOLUTION
> The airline must operationalize a paradigm shift in how crew compliance is governed going forward.

**GREEN:**

> SITUATION
> [needs: the airline's current crew-compliance baseline]
>
> COMPLICATION
> [needs: the specific deadline, gap, or event that forces these decisions now]
>
> RESOLUTION
> [needs: owner at the airline] must [needs: the specific change to how crew compliance is governed] by [needs: date].

**Expected finding:** `[Tone — prohibited language] "Leveraging," "evolving landscape," "crucial," "pivotal," "transformative," "operationalize," "paradigm shift," "going forward" are all prohibited in SCR elements. These words obscure the specific facts the audience needs. Remove them rather than swapping in near-synonyms ("critical," "major," "fundamental"), which keep the filler and break the concrete-language rule. Once the filler goes, no element states a fact, so each becomes a [needs: …] marker rather than an invented detail. [Situation — too broad] "Operators are increasingly leveraging digital tools" describes the industry, and nothing in the Complication depends on it; write [needs: the airline's current crew-compliance baseline]. [Complication — no specific pressure] "Pivotal decisions ahead" names no deadline, gap, or event behind the decisions; write [needs: the specific deadline, gap, or event that forces these decisions now]. [Resolution — principle not action] "Operationalize a paradigm shift in how crew compliance is governed" is a principle, not an action; write [needs: the specific change to how crew compliance is governed] rather than inventing one. [Resolution — owner and timing missing] "The airline must operationalize…" names the organisation as a whole, not an owner, and gives no timing; a Resolution needs who acts and by when, so write [needs: owner at the airline] and [needs: date].`

---

### T2 — Passive voice in SCR

**RED:**

> RESOLUTION
> A decision must be reached by the executive team, and the new process will be approved by the board before revalidation dates are migrated by the training office.

**GREEN:**

> RESOLUTION
> The executive team must decide [needs: what the executive team decides] by [needs: date], and the board will approve the new process before the training office migrates the revalidation dates.

**Expected finding:** `[Tone — passive voice] "A decision must be reached by the executive team," "will be approved by the board," "are migrated by the training office" — passive voice in the Resolution breaks the rule of active voice throughout all three elements. Use active voice: name the actor before the action. The carve-out for an irrelevant or unknown actor does not apply here, because every actor is known and named in the same sentence. [Resolution — decision and timing missing] "A decision must be reached" never says what is decided, and the draft gives no date for the decision. Write [needs: what the executive team decides] and [needs: date] rather than inventing them, and list both under Gaps. The approval is timed relative to the migration, and the migration only marks when the approval happens, so neither takes a [needs: date].`

---

### T3 — A defined term and a passive whose actor is unknown

**GREEN:**

> COMPLICATION
> The external auditor reported a significant deficiency in payroll controls on 12 February: two payroll records were altered after approval, and the audit trail does not show who altered them.

**Expected finding:** `(No finding — "significant deficiency" is a defined audit category, not the banned intensifier, so the word list does not apply. "Were altered" is a passive whose actor is unknown, which the active-voice carve-out allows; the sentence says the actor is unknown rather than hiding a known one. Do not rewrite either.)`

---

## Length

### L1 — Elements exceed maximum length

**RED:**

> SITUATION
> Crew licensing moved to the training office after the 2019 fleet expansion. Since then the office has built its own revalidation tracker and rebuilt it twice as the fleet grew, and in 2023 it absorbed the regional subsidiary's records. What exists today reflects seven years of local fixes, most made under roster pressure and none of them documented.

**GREEN:**

> SITUATION
> Crew licensing moved to the training office after the 2019 fleet expansion. Since then the office has built its own revalidation tracker and rebuilt it twice as the fleet grew, and in 2023 it absorbed the regional subsidiary's records.

**Expected finding:** `[Length — Situation too long] The Situation runs to three sentences, over the 1–2 sentence limit. The third sentence, seven years of undocumented local fixes made under roster pressure, implies a problem, which belongs in the Complication, not the Situation. The rebuilds are neutral history tied to fleet growth and stay; "has built" and "rebuilt" are present perfect for the continuing tracker, and "in 2023 it absorbed" is past for a dated, completed event. Keep the neutral baseline facts in 1–2 sentences. Distill to the minimum shared context the audience needs to understand the Complication.`

---

### L2 — Semicolons hide an over-long Situation

**RED:**

> SITUATION
> The museum catalogues its collection in one database; curators, registrars, and the loans team all edit it; the database holds about 90,000 object records; the digital team maintains it.

**GREEN:**

> SITUATION
> The museum catalogues its collection in one database, which holds about 90,000 object records and which the digital team maintains. Curators, registrars, and the loans team all edit it.

**Expected finding:** `[Length — Situation too long] The Situation is one sentence on paper but four semicolon-joined clauses, and each counts as a sentence, so it runs to four, over the 1–2 sentence limit. Rejoin the facts into at most two sentences without dropping any.`

---

## Passing SCR

### P1 — Compliant SCR with a known fact and a stakes clause

**GREEN:**

> SITUATION
> Every hospital pharmacist must hold a current registration to dispense medicines, and a lapsed registration stops that pharmacist dispensing the same day. The trust's 60 pharmacists each renew once a year.
>
> COMPLICATION
> Renewal dates sit in an HR spreadsheet the dispensing rota never reads, and in March the rota put two pharmacists on shift after their registrations lapsed.
>
> RESOLUTION
> The Chief Pharmacist links renewal dates to the dispensing rota by 30 June, so the rota blocks any pharmacist whose registration lapses.

**Expected finding:** `(No finding — SCR passes. The skill writes "SCR passes" with one line per element and gives no corrected version. "Every hospital pharmacist must hold a current registration" is a known fact, but the Complication builds on it, so it is not too broad. "A lapsed registration stops that pharmacist dispensing the same day" states what a lapse costs, which the Situation allows; it does not say the process is failing. The Complication is specific, active ("the rota put two pharmacists on shift"), and follows from the Situation, and the Resolution answers it with an owner and a date.)`

---

## Verification Log

**Verified 2026-10-22.** Result: **23/23 passed.** Graded by an Opus agent reading `SKILL.md` and `TESTS.md`, with no edit to either file afterwards.

Produced against `TESTS.md` body sha256 `87b668aade02f175` and `SKILL.md` sha256 `294b3a02fc3b1cf0`. The body hash covers everything above this heading, so it survives this table being written. Recompute both before trusting the rows: any later edit invalidates them, and a log that certifies rather than records hides the defects it exists to surface.

| Test                                                                    | RED flags | GREEN clean | Pass |
|-------------------------------------------------------------------------|-----------|-------------|------|
| B1 — Build draft invents facts the brief never gave                     | ✓         | ✓           | PASS |
| X1 — Memo with no Complication, mapped from its headings                | ✓         | ✓           | PASS |
| S1 — Situation smuggles in the complication                             | ✓         | ✓           | PASS |
| S2 — Situation too narrow (doesn't cover what the audience cares about) | ✓         | ✓           | PASS |
| S3 — Present tense used for a historical fact                           | ✓         | ✓           | PASS |
| S4 — Scheduled future fact, plan estimate, and present perfect          | n/a       | ✓           | PASS |
| C1 — Complication is a vague trend                                      | ✓         | ✓           | PASS |
| C2 — Complication not grounded in the Situation                         | ✓         | ✓           | PASS |
| C3 — Two complications stacked without choosing the sharper one         | ✓         | ✓           | PASS |
| C4 — Complication cites a table that holds the figure                   | ✓         | ✓           | PASS |
| C5 — A deadline and a lead time make one Complication                   | n/a       | ✓           | PASS |
| C6 — A bounded warning with a range and "may"                           | n/a       | ✓           | PASS |
| R1 — Resolution too broad                                               | ✓         | ✓           | PASS |
| R2 — Resolution stated as a principle, not an action                    | ✓         | ✓           | PASS |
| R3 — Resolution doesn't address the complication                        | ✓         | ✓           | PASS |
| R4 — Resolution introduces ideas not set up in S or C                   | ✓         | ✓           | PASS |
| R5 — Resolution has no owner or timing, and the draft supplies none     | ✓         | ✓           | PASS |
| T1 — Prohibited language in SCR elements                                | ✓         | ✓           | PASS |
| T2 — Passive voice in SCR                                               | ✓         | ✓           | PASS |
| T3 — A defined term and a passive whose actor is unknown                | n/a       | ✓           | PASS |
| L1 — Elements exceed maximum length                                     | ✓         | ✓           | PASS |
| L2 — Semicolons hide an over-long Situation                             | ✓         | ✓           | PASS |
| P1 — Compliant SCR with a known fact and a stakes clause                | n/a       | ✓           | PASS |

"n/a" marks a no-finding test with no RED; it passes only if the rules raise nothing on the GREEN.

**FAIL notes.** None. Counts checked with a Python script: X1 Background four sentences, L1 three sentences, L2 four semicolon-joined clauses, C4 overruns of 450 (May) and 700 (June) with April under capacity, T1 all eight prohibited terms present in the RED and none in the GREEN, B1's four invented details absent from the brief, T2 GREEN carries one [needs: date]; every GREEN element within its sentence limit.

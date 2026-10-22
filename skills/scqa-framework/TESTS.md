# SCQA Framework Skill — Red/Green Test Suite

Each test has:

- **RED:** draft opening that violates the SCQA principle (should be flagged)
- **GREEN:** corrected SCQA structure
- **Expected finding:** what the skill should identify and fix

---

## Situation

### S1 — Starting with complication (no situation)

**RED:**

> Roster clerks breach minimum-rest rules on about one shift swap in twelve. Every swap now needs a manual check, and the backlog grows each week.
>
> _(Audience: the operator's board, which has not been briefed on rostering before.)_

**GREEN:**

> **S:** Roster clerks process shift swaps under minimum-rest rules.
>
> **C:** Clerks breach those rules on about one swap in twelve. Every swap now needs a manual check, and the backlog grows each week.
>
> **Q** _(implicit)_: How do we keep shift swaps moving without breaching rest rules?
>
> **A:** [needs: the recommendation]

**Expected finding:** `[Situation missing] The opening jumps directly to the complication with no shared ground established. This audience has not been briefed on rostering, so it needs a neutral, uncontroversial starting point it can nod at before the problem lands. Add a 1–2 sentence Situation that both sides already accept as true.`

---

### S2 — Situation asserts rather than states fact

**RED:**

> **S:** The trust's imaging archive is inadequate and fails to support modern clinical workflows.

**GREEN:**

> **S:** The trust has an imaging archive. [needs: a structural fact about the archive, such as the volume or workflow it was designed for]
>
> **C:** The archive is inadequate and fails to support modern clinical workflows. [needs: which workflows, and what the failure costs clinical staff]

**Expected finding:** `[Situation quality] "Inadequate and fails to support modern clinical workflows" is an evaluative claim, not a neutral fact — the audience may push back on it. The Situation should be something every reader already accepts. State the structural fact (what the process is) rather than the judgment (what's wrong with it). Move the judgment ("inadequate and fails to support modern clinical workflows") to the Complication rather than dropping it, and mark what it lacks with [needs: …].`

---

### S3 — Situation too broad (restating industry-level facts)

**RED:**

> **S:** Digital transformation is reshaping every industry worldwide, and organizations everywhere are being forced to adapt to rapidly changing technology landscapes.

**GREEN:**

> **S:** [needs: a specific fact about the client's own systems or processes that the audience can confirm from its own experience]

**Expected finding:** `[Situation scope] The Situation restates industry-level trends the audience already knows and considers obvious. Ground the Situation in the client's specific context — a specific process, a specific system, a specific fact the audience can confirm from their own experience.`

---

### S4 — Sector-level Situation for a sector-wide audience (must stay unflagged)

**GREEN:**

> _(Audience: finance directors of every further-education college in the region.)_
>
> **S:** Most colleges in the region run payroll on one of two shared-service platforms, each serving eight to twelve colleges.
>
> **C:** Both platform contracts end in 2028, and neither has been re-tendered.
>
> **Q** _(implicit)_: How do the colleges keep payroll running after 2028?
>
> **A:** The colleges should run one joint re-tender for both platforms.

**Expected finding:** `(No finding — the audience is the whole regional sector, so a specific sector fact is the audience's own context and passes the Situation check. Do not raise [Situation scope]: that finding is for generic trend statements such as S3's, not for a specific fact the audience can confirm.)`

---

## Complication

### C1 — Weak complication (no urgency)

**RED:**

> **S:** Train operators build driver rosters in a scheduling system installed in 2016.
>
> **C:** There is some room to tighten how rest rules get checked.

**GREEN:**

> **S:** Train operators build driver rosters in a scheduling system installed in 2016.
>
> **C:** There is some room to tighten how rest rules get checked [needs: figure for how often a breach gets through], and [needs: consequence of a breach for the operator].

**Expected finding:** `[Complication urgency] "Some room to tighten how rest rules get checked" creates no urgency — the audience can continue as-is without feeling pressure. A complication must give the audience a reason to act: a cost, a failure rate, a deadline, a conflict, a risk, or an opportunity. Quantify only with figures the input supplies; otherwise mark [needs: figure for …]. Keep the author's wording: do not harden "some room to tighten" into a stronger claim such as "not checked tightly enough", which the input never made.`

---

### C2 — Complication not grounded in situation

**RED:**

> **S:** The trust routes every diagnostic image through one archive that was sized for 2019 volumes.
>
> **C:** Clinical staff satisfaction across the sector has declined because of rising administrative workload.

**GREEN:**

> **S:** The trust routes every diagnostic image through one archive that was sized for 2019 volumes.
>
> **C:** [needs: what the archive has run into since it was sized for 2019 volumes, and what that costs clinical staff]

**Expected finding:** `[Complication–Situation link] The Complication (sector-wide staff satisfaction) does not follow from the Situation (one undersized imaging archive). The Complication must be the thing the Situation has run into — it should feel inevitable given the Situation. Replace with a Complication that connects directly to the archive established above.`

---

### C3 — Complication is really the solution

**RED:**

> **S:** University departments are beginning to choose software for next year's teaching.
>
> **C:** We need to agree a campus licensing standard before departments place their orders.

**GREEN:**

> **S:** University departments are beginning to choose software for next year's teaching.
>
> **C:** Departments may place their orders before any campus licensing standard is agreed, and [needs: what goes wrong when orders are placed without the standard].
>
> **A:** Agree a campus licensing standard before departments place their orders.

**Expected finding:** `[Complication is the solution] "We need to agree a campus licensing standard" belongs in the Answer, not the Complication. The Complication should describe the problem that makes the current situation unsustainable — not the recommended fix. State what goes wrong without the standard; the Answer will name the standard.`

---

### C4 — Urgency figure missing from the input

**RED:**

> **S:** The county library service lends laptops from twelve branches using a paper sign-out sheet.
>
> **C:** Laptops go missing more often than they used to.
>
> _(The author's notes give no loss figures.)_

**GREEN:**

> **S:** The county library service lends laptops from twelve branches using a paper sign-out sheet.
>
> **C:** Laptops go missing more often than they used to [needs: figure for laptop losses per month], and [needs: what each loss costs the service].

**Expected finding:** `[Complication urgency] "Go missing more often than they used to" names a pain but gives no figure, and the input supplies none. Do not invent one: keep the author's words, write [needs: figure for laptop losses per month] where the number belongs, and list it under Gaps.`

---

### C5 — Conditional, estimated Complication (must stay unflagged)

**GREEN:**

> **S:** The water company supplies the district from one treatment plant licensed to abstract 90 megalitres a day.
>
> **C:** If the regulator adopts its draft drought order in May, the licence may fall to about 70 megalitres a day for up to four months, below the 75–80 megalitres a day forecast for summer demand.
>
> **Q** _(implicit)_: How do we meet summer demand if the order is adopted?
>
> **A:** Bring the standby borehole back into service before May.

**Expected finding:** `(No finding — a dated conditional risk with an estimate and a range is a valid Complication. Do not raise [Complication urgency]. Any rewrite must keep "If", "may", "about", "up to", and "75–80" exactly as written.)`

---

### C6 — Opportunity as the Complication (must stay unflagged)

**GREEN:**

> **S:** The council's waste service runs 24 diesel refuse trucks and replaces two or three a year.
>
> **C:** A national scheme now pays half the price of each electric refuse truck ordered before March 2028, while the council pays the full price of every diesel replacement.
>
> **Q** _(implicit)_: Which fuel should the next replacements use while the scheme runs?
>
> **A:** Order every replacement due before March 2028 as an electric truck.

**Expected finding:** `(No finding — a Complication can be an opportunity that makes the status quo worth changing. Do not raise [Complication urgency] and do not add a pain, such as rising diesel costs, that the input does not state.)`

---

### C7 — Complication given as a list and a table

**RED:**

> **S:** The hospital runs one discharge lounge for all wards.
>
> **C:** Since the winter bed plan started:
> - patients wait longer for transport home;
> - pharmacy turnaround for take-home medicines has slowed;
> - weekend discharges have fallen.
>
> | Step | Nov median (h) | Feb median (h) |
> |---|---|---|
> | Transport | 1.5 | 2.0 |
> | Pharmacy | 1.0 | 3.5 |
> | Paperwork | 0.5 | 0.5 |
>
> **A:** Place a pharmacist in the discharge lounge until the bed plan ends.

**GREEN:**

> **S:** The hospital runs one discharge lounge for all wards.
>
> **C:** Pharmacy turnaround for take-home medicines has slowed since the winter bed plan started. Its median in the step table is 1.0 hours in November and 3.5 in February.
>
> **Q** _(implicit)_: How do we cut pharmacy turnaround in the discharge lounge?
>
> **A:** Place a pharmacist in the discharge lounge until the bed plan ends.
>
> **Body material:** since the winter bed plan started, patients wait longer for transport home and weekend discharges have fallen; the per-step table (Transport, Pharmacy, Paperwork medians for November and February).

**Expected finding:** `[Complication form] The Complication runs to three bullets and a table, where the block allows one or two sentences. Name the pain that drives the Answer — pharmacy turnaround, a median of 1.0 hours in November and 3.5 in February — and keep those figures without tying November to the start of the bed plan, which the input does not do, because they are why the Answer targets pharmacy. List the transport wait, the fall in weekend discharges, and the table under Body material rather than dropping them.`

---

## Question

### Q1 — Question doesn't arise from complication

**RED:**

> **S:** The trust routes every diagnostic image through one archive that was sized for 2019 volumes.
>
> **C:** Retrieval requests have tripled and radiologists now wait an average of four minutes to open a study.
>
> **Q:** How can the trust improve its digital maturity?

**GREEN:**

> **S:** The trust routes every diagnostic image through one archive that was sized for 2019 volumes.
>
> **C:** Retrieval requests have tripled and radiologists now wait an average of four minutes to open a study.
>
> **Q** _(implicit)_: How do we cut retrieval time?

**Expected finding:** `[Question–Complication fit] The Question ("How can the trust improve its digital maturity?") does not arise from the Complication (four-minute image retrieval). The reader coming off that Complication is asking how to make retrieval fast again. Align the Question to the exact tension the Complication created.`

---

### Q2 — Implicit Question inferred from the Answer

**RED:**

> **S:** The council's planning team logs every application in one case system built in 2012.
>
> **C:** Applications have doubled since 2020, and decisions now take eleven weeks against an eight-week target.
>
> **A:** Moving the case system to the county's shared platform halves the annual hosting fee.

**GREEN:**

> **S:** The council's planning team logs every application in one case system built in 2012.
>
> **C:** Applications have doubled since 2020, and decisions now take eleven weeks against an eight-week target.
>
> **Q** _(implicit)_: How do we get decisions back inside eight weeks?
>
> **A:** Moving the case system to the county's shared platform halves the annual hosting fee. [needs: how the move shortens decision times — ask the author whether it does]

**Expected finding:** `[Answer–Question fit] Written from the Complication alone, the implicit Question is how to get decisions back inside eight weeks. The Answer addresses the hosting fee instead. Do not infer the Question from the Answer ("How do we cut hosting cost?"), which makes the fit check pass by construction. Keep the Answer as written, mark the gap, and ask the author whether the move shortens decisions; do not add that claim to the Answer or delete the hosting-fee claim.`

---

## Answer

### A1 — Answer doesn't address the question

**RED:**

> **Q:** How do we keep shift swaps moving without breaching rest rules?
>
> **A:** The rostering module offers a configurable rules engine and supports multiple swap request channels.

**GREEN:**

> **Q:** How do we keep shift swaps moving without breaching rest rules?
>
> **A:** The rostering module offers a configurable rules engine and supports multiple swap request channels. [needs: how the module keeps swaps moving and stops rest breaches — ask the author whether the rules engine checks each swap against the rest rules]

**Expected finding:** `[Answer–Question fit] The Question asks for two things — that swaps keep moving and that rest rules hold — and the Answer lists the module's features instead. These are adjacent, not the same. The Answer must address the Question directly, covering both clauses: how swaps stay fast and how breaches are prevented. If the input does not say the module does this, change the stated Question to fit what it does only if the new Question still arises from the Complication, or ask the author; keep the Answer's two claims, mark the gap, and do not add a capability to the Answer.`

---

### A2 — Answer too complex (details in answer, not body)

**RED:**

> **A:** Roster clerks will enter swaps through the new module, which validates rest rules at entry, moves sign-off along delegated approval chains, keeps audit logging for every change, allows offline depot access from terminals, and gives duty managers rest-compliance reporting by depot and grade.

**GREEN:**

> **A:** Roster clerks will enter swaps through the new module, which validates rest rules at entry.
>
> **Body material:** sign-off along delegated approval chains; audit logging for every change; offline depot access from terminals; rest-compliance reporting by depot and grade for duty managers.

**Expected finding:** `[Answer complexity] The Answer is one sentence but lists five module features. An SCQA Answer states one decision or claim; lists of three or more features or steps go to the body. Details about delegated approval chains, audit logging, offline depot access, and rest-compliance reporting by depot and grade belong in the pyramid body that follows.`

---

### A3 — Correct SCQA with appropriate variant

**GREEN:**

> **S:** The client's core analytics platform runs on on-premises infrastructure procured in 2018, managed by a team of six engineers.
>
> **C:** The vendor ends extended support for this infrastructure in March 2028. After that date, the client bears the full security patching and compliance burden at a cost that exceeds the annual licensing fee for a managed cloud equivalent.
>
> **Q** _(implicit)_: How do we avoid carrying the full patching and compliance burden after March 2028?
>
> **A:** The client must begin cloud migration scoping by Q2 2027 to complete the transition before the March 2028 support cutoff.
>
> Variant: **SCQA** — the cutoff date makes the Question obvious, so spelling it out would add a line the reader does not need.

**Expected finding:** `(No finding — this is a clean SCQA. Skill should confirm: Situation is neutral, Complication has a hard external trigger, Question arises from the Complication without presupposing the Answer, Answer directly addresses the deadline, variant selection is explained.)`

---

### A4 — One-sentence Answer packed with thresholds

**RED:**

> **A:** The housing service should sort repair requests into three urgency bands in which emergency repairs get a same-day visit from the duty team, urgent repairs get a visit within five working days from the area team, and routine repairs are batched into a monthly schedule, with every band reported weekly to the housing committee.

**GREEN:**

> **A:** The housing service should sort repair requests into three urgency bands.
>
> **Body material:** emergency repairs get a same-day visit from the duty team; urgent repairs get a visit within five working days from the area team; routine repairs are batched into a monthly schedule; every band is reported weekly to the housing committee.

**Expected finding:** `[Answer complexity] The Answer is one sentence, but it carries the response time for each of the three bands and a weekly reporting line. An SCQA Answer states one decision or claim; thresholds, tier specifications, and lists of three or more features or steps go to the body. Keep "sort repair requests into three urgency bands" and move the band times, teams, and reporting to the body.`

---

## Variant Selection

### V1 — Wrong variant selected

**RED:**

> Used variant **CSA** (audience already knows the situation).
>
> **C:** Three warehouse shifts have not finished slotting the new stock lines, and the carrier cannot begin booking collections.
>
> **A:** Leadership must approve the four-zone layout before any shift finalizes its pick paths.
>
> _(Audience: a new external client who has not seen the project context.)_

**GREEN:**

> Used variant **SCQA** for a new external audience.
>
> **S:** [needs: Situation for a reader new to the project — what the warehouse change is, and how slotting stock lines and booking collections connect]
>
> **C:** Three warehouse shifts have not finished slotting the new stock lines, and the carrier cannot begin booking collections.
>
> **Q** _(implicit)_: How do we get collection booking started?
>
> **A:** Leadership must approve the four-zone layout before any shift finalizes its pick paths. [needs: how approving the four-zone layout lets the carrier begin booking collections — ask the author]

**Expected finding:** `[Variant mismatch] CSA leads with the Complication and leaves the Situation brief or implied, on the assumption the audience already knows it. For a new external client with no prior context, that assumption is wrong — they need the Situation to understand what the Complication is disrupting. Use SCQA for this audience. Reserve CSA for audiences who were present for the full project context.`

---

### V2 — Complication-first opening for an audience that knows the Situation (must stay unflagged)

**GREEN:**

> _(Audience: the hospital's bed-management group, which set the 11:00 discharge target.)_
>
> **C:** Two medical wards missed the 11:00 discharge target on four of five days last week, so 30 emergency admissions waited past noon for a bed.
>
> **S:** The target exists because emergency admissions peak at 13:00.
>
> **A:** Move the two wards' consultant rounds to 08:30 for the next two weeks.
>
> Variant: **CSA** — the group set the target, so the Complication can lead.

**Expected finding:** `(No finding — this is CSA: the Complication leads and a brief Situation follows. The audience set the target, so opening with the Complication is correct. Do not raise [Situation missing].)`

---

### V3 — SCQ opening for an options paper (must stay unflagged)

**GREEN:**

> _(The board has asked for options, not a recommendation.)_
>
> **S:** The college runs student records on a system whose support contract ends in August 2027.
>
> **C:** The board must choose a route before then and has asked for options rather than a recommendation.
>
> **Q:** Should the college replace the system, extend support, or join the regional shared service?
>
> **A:** (deferred to body)
>
> **Governing thought for body:** Three routes are open, and the body compares them.
>
> Variant: **SCQ** — the board asked for options, so the Question closes the opening and the body carries the answer.

**Expected finding:** `(No finding — a clean SCQ. The A line is deferred and the governing thought for the body stands in for pyramid Level 1. Do not add a recommendation to the opening.)`

---

## Critique mode

### R1 — Prose opening submitted for review (must stay unflagged)

**GREEN:**

> _(Request: "Is this opening working?")_
>
> Although the depot's single overnight wash cycle was set up for a fleet of 40 buses, it now serves 65, and drivers report that about a third of morning departures leave unwashed. Adding a second, shorter evening cycle would clear the backlog without extra staff. The sections below cover the timing, the water cost, and a four-week trial.

**Expected finding:** `(No finding, and no rewrite. Report the elements: S is the "Although" clause (a cycle set up for 40 buses); C is "it now serves 65 … leave unwashed", keeping "about a third" as written; no sentence states a Question, so the variant is SCA; A is the second sentence. Do not raise [Situation missing] because the first sentence opens on a problem: the Situation sits in its subordinate clause.)`

---

## Verification Log

**Verified 2026-10-22.** Result: **21/21 passed.** Graded by an Opus agent reading `SKILL.md` and `TESTS.md`, with no edit to either file afterwards.

Produced against `TESTS.md` body sha256 `14985a86aba29aff` and `SKILL.md` sha256 `3a69a9efe21208f6`. The body hash covers everything above this heading, so it survives this table being written. Recompute both before trusting the rows: any later edit invalidates them, and a log that certifies rather than records hides the defects it exists to surface.

| Test                                                                     | RED flags | GREEN clean | Pass |
|--------------------------------------------------------------------------|-----------|-------------|------|
| S1 — Starting with complication (no situation)                           | ✓         | ✓           | PASS |
| S2 — Situation asserts rather than states fact                           | ✓         | ✓           | PASS |
| S3 — Situation too broad (restating industry-level facts)                | ✓         | ✓           | PASS |
| S4 — Sector-level Situation for a sector-wide audience                   | n/a       | ✓           | PASS |
| C1 — Weak complication (no urgency)                                      | ✓         | ✓           | PASS |
| C2 — Complication not grounded in situation                              | ✓         | ✓           | PASS |
| C3 — Complication is really the solution                                 | ✓         | ✓           | PASS |
| C4 — Urgency figure missing from the input                               | ✓         | ✓           | PASS |
| C5 — Conditional, estimated Complication                                 | n/a       | ✓           | PASS |
| C6 — Opportunity as the Complication                                     | n/a       | ✓           | PASS |
| C7 — Complication given as a list and a table                            | ✓         | ✓           | PASS |
| Q1 — Question doesn't arise from complication                            | ✓         | ✓           | PASS |
| Q2 — Implicit Question inferred from the Answer                          | ✓         | ✓           | PASS |
| A1 — Answer doesn't address the question                                 | ✓         | ✓           | PASS |
| A2 — Answer too complex (details in answer, not body)                    | ✓         | ✓           | PASS |
| A3 — Correct SCQA with appropriate variant                               | n/a       | ✓           | PASS |
| A4 — One-sentence Answer packed with thresholds                          | ✓         | ✓           | PASS |
| V1 — Wrong variant selected                                              | ✓         | ✓           | PASS |
| V2 — Complication-first opening for an audience that knows the Situation | n/a       | ✓           | PASS |
| V3 — SCQ opening for an options paper                                    | n/a       | ✓           | PASS |
| R1 — Prose opening submitted for review                                  | n/a       | ✓           | PASS |

14 tests check a RED finding and a clean GREEN; 7 are negative tests (S4, C5, C6, A3, V2, V3, R1) that must stay unflagged.

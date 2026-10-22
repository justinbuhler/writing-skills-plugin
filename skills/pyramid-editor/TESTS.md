# Pyramid Editor Skill — Red/Green Test Suite

Each test has:

- **RED:** draft or outline that violates the pyramid principle (should be flagged)
- **GREEN:** correctly restructured version
- **Expected finding:** what the skill should identify and fix

---

## Governing Thought (Level 1)

### 1.1 — Buried recommendation (lede buried)

**RED:**

> The vendor review closed on Friday. Platform Y's contract locks us in for two years, and Platform Z had two outages this quarter. We recommend Platform X. It scored highest on scalability, support quality, and total cost of ownership across all 12 platforms. Procurement can open contract talks next week.

**GREEN:**

> **We recommend Platform X.** It scored highest on scalability, support quality, and total cost of ownership across all 12 platforms. The vendor review closed on Friday. Platform Y's contract locks us in for two years, and Platform Z had two outages this quarter. Procurement can open contract talks next week.

**Expected finding:** `[Level 1 — buried lede] The recommendation ("We recommend Platform X") sits third, after a status line and the drawbacks of the two rival platforms. Pull it to the first sentence as a bold, direct governing thought, with its supporting result (highest on the three criteria across 12 platforms) next. Keep every other sentence, including both rivals' drawbacks and the next step; the draft is prose, so it stays prose rather than becoming a pillar outline.`

---

### 1.2 — No governing thought (topic statement only)

**RED:**

> ## Cloud Migration Strategy
>
> This document covers the current infrastructure state, migration options, risk factors, and a proposed timeline.

**GREEN:**

> ## [needs: recommendation]
>
> This document covers the current infrastructure state, migration options, risk factors, and a proposed timeline.

**Expected finding:** `[Level 1 — missing governing thought] The heading and opening sentence describe what the document covers, not what it concludes. The title heading carries the governing thought, and the draft states no conclusion, so the heading becomes ## [needs: recommendation] at the same level and the marker is listed under Gaps; do not write a conclusion for the author and do not add a bold sentence above the heading. The sentence "This document covers…" stays as written: the draft supplies no claim to replace it with.`

---

### 1.3 — Conditional recommendation keeps its conditions

**RED:**

> The print contract ends in March. We compared renewing it with moving to the shared print service. If the shared service can take our volume by February, we recommend moving to it. If it cannot, we recommend renewing for one year at an estimated $48,000.

**GREEN:**

> **Move to the shared print service if it can take our volume by February; if not, renew for one year (estimated $48,000).** The print contract ends in March. We compared renewing it with moving to the shared print service.

**Expected finding:** `[Level 1 — buried lede] Both recommendations sit after the context, and each depends on a condition. Pull them to the top as one bold governing thought that keeps the February condition, the one-year fallback, and "estimated". Do not shorten it to "Move to the shared print service": direct means first and explicit, not unconditional.`

---

### 1.4 — Governing thought supplied by the caller is used as written

**RED (input from `writing-workflow` Step 2; supplied governing thought: "Approve the move of the help desk to the central site by 30 June."):**

> We recommend moving the help desk to the central site. We also recommend extending its hours to 22:00.

**GREEN:**

> **Approve the move of the help desk to the central site by 30 June.**
>
> We recommend moving the help desk to the central site. We also recommend extending its hours to 22:00.

**Expected finding:** `[Level 1 — governing thought] The caller supplied the governing thought, so use it as written at the top. Do not replace it with a summary of the draft's two recommendations; summarizing parallel recommendations applies only when no governing thought is supplied. "Extending its hours to 22:00" is not covered by the supplied governing thought: it stays where it is and is not a finding, because the caller owns the answer.`

---

## Supporting Pillars (Level 2)

### 2.1 — Too few pillars (one pillar)

**RED:**

> **Governing thought:** Migrate to Platform X.
>
> **Pillar 1:** Platform X beats the current system: it costs less to operate, provisions faster, and has a strong security record in regulated environments.

**GREEN:**

> **Governing thought:** Migrate to Platform X.
>
> **Pillar 1:** Platform X costs less to operate than the current system.
> **Pillar 2:** Platform X provisions faster than the current system.
> **Pillar 3:** Platform X has a strong security record in regulated environments.

**Expected finding:** `[Level 2 — insufficient pillars] One pillar cannot carry the governing thought. The pillar bundles three reasons (operating cost, provisioning speed, security record); split them into separate, mutually exclusive pillars. Use only the reasons the draft gives. The input carries no evidence, so the rewrite adds no evidence markers.`

---

### 2.2 — Too many pillars (group, do not narrow)

**RED:**

> **Governing thought:** Reform the procurement process.
>
> **Pillar 1:** Approvals take too long
> **Pillar 2:** Staff are undertrained
> **Pillar 3:** The vendor list is outdated
> **Pillar 4:** Documentation is incomplete
> **Pillar 5:** IT systems don't support the workflow
> **Pillar 6:** Finance sign-off adds three extra weeks

**GREEN:**

> **Governing thought:** Reform the procurement process.
>
> **Pillar 1:** The approval chain is too slow.
>   - Approvals take too long.
>   - Finance sign-off adds three extra weeks.
> **Pillar 2:** The process records are outdated or incomplete.
>   - The vendor list is outdated.
>   - Documentation is incomplete.
> **Pillar 3:** Staff training and IT systems do not support the process.
>   - Staff are undertrained.
>   - IT systems don't support the workflow.

**Expected finding:** `[Level 2 — too many pillars] Six pillars exceed the 2–5 limit. Group related arguments into higher-level pillars: the six group cleanly into three (approval speed, process records, staff and systems), so the governing thought stays as written. Keep every original argument, including the three-week Finance figure, as Level 3 under its group.`

---

### 2.3 — Non-MECE pillars (overlap)

**RED:**

> **Governing thought:** Adopt the new data governance framework.
>
> **Pillar 1:** It reduces compliance risk.
> **Pillar 2:** It improves data quality.
> **Pillar 3:** It reduces regulatory exposure.

**GREEN:**

> **Governing thought:** Adopt the new data governance framework.
>
> **Pillar 1:** It reduces compliance and regulatory risk.
> **Pillar 2:** It improves data quality.

**Expected finding:** `[Level 2 — MECE failure: overlap] Pillar 1 ("compliance risk") and Pillar 3 ("regulatory exposure") cover the same ground. Pillars must be mutually exclusive — consolidate overlapping arguments into one pillar. Two pillars remain; do not add a third the draft does not argue.`

---

### 2.4 — Mixed abstraction levels in pillars

**RED:**

> **Pillar 1:** It includes a reporting module
> **Pillar 2:** It uses a REST API for data ingestion
> **Pillar 3:** It eliminates manual reconciliation

**GREEN:**

> **Pillar 1:** [needs: outcome of the reporting module]
>   - It includes a reporting module
> **Pillar 2:** [needs: outcome of REST API data ingestion]
>   - It uses a REST API for data ingestion
> **Pillar 3:** It eliminates manual reconciliation
>   - [needs: evidence for "It eliminates manual reconciliation"]

**Expected finding:** `[Level 2 — mixed abstraction] The three pillars are at different levels of abstraction: one is a capability, one is an implementation detail, one is an outcome. Pillar 2 (the REST API) is an implementation detail, so only outcome pillars stay. "It eliminates manual reconciliation" states an effect on work and stays as Pillar 3. The reporting module is a capability, so it moves down with the REST API: each becomes a Level 3 detail under an outcome pillar; the draft states no outcome for either, so their pillars are [needs: outcome of the reporting module] and [needs: outcome of REST API data ingestion].` `[Level 3 — missing evidence] Once those pillars carry Level 3 details, Pillar 3 needs evidence too: [needs: evidence for "It eliminates manual reconciliation"].`

---

### 2.5 — Pillars not ordered consistently

**RED:**

> **Pillar 1:** In phase 3, the remaining 40 sites move over in September.
> **Pillar 2:** In phase 1, the two pilot sites move over in March.
> **Pillar 3:** In phase 2, the regional hubs move over in June.

**GREEN:**

> **Pillar 1:** In phase 1, the two pilot sites move over in March.
> **Pillar 2:** In phase 2, the regional hubs move over in June.
> **Pillar 3:** In phase 3, the remaining 40 sites move over in September.

**Expected finding:** `[Level 2 — inconsistent ordering] The pillars are phases of a time sequence but run phase 3, phase 1, phase 2. Ordering is a property of the whole group: apply chronological order consistently, March, June, September. The input is a bare list of pillars, so do not add a governing thought or evidence markers.`

---

### 2.6 — Draft argues only one reason

**RED:**

> **Governing thought:** Move the weekly status call to Tuesday.
>
> **Pillar 1:** Three of the four workstream leads are at warehouse audits every Monday.

**GREEN:**

> **Governing thought:** Move the weekly status call to Tuesday.
>
> **Pillar 1:** Three of the four workstream leads are at warehouse audits every Monday.
> **Pillar 2:** [needs: second supporting argument]

**Expected finding:** `[Level 2 — insufficient pillars] The draft argues one reason, and it is a single reason, not a bundle to split. Keep it as Pillar 1, add Pillar 2: [needs: second supporting argument], and list it under Gaps; do not write a second reason. The input carries no evidence, so add no evidence markers.`

---

### 2.7 — Framing and back-matter sections are not pillars (must stay unflagged)

**RED (input to review):**

```
# Move outpatient booking to the main hospital by 1 April
## Executive Summary
We recommend moving the booking desk from the two clinic offices to the main hospital by 1 April.
## The clinic offices cannot staff evening shifts
Both offices lost their evening cover when the lease terms changed in May.
## The main hospital already has the phone lines
The hospital's call system has 20 unused lines.
## The move fits inside the lease notice period
Both clinic leases need 60 days' notice, and 1 April is 75 days away.
## Risks and open items
Parking at the main hospital is limited, and Estates has not yet confirmed staff permits.
## Next Steps
Estates confirms staff parking permits by 15 February.
## Appendix A: Floor Plan
```

**GREEN (expected output — returned unchanged):**

Same as RED.

**Expected finding:** `(No finding — three argument sections, each a claim with evidence, in problem-then-solution order. Executive Summary, Risks and open items, Next Steps, and Appendix A are framing or back matter: they are not counted as pillars, not failed as topic labels, and the risks section stays. Blink test: PASS. Skill should say "No structural changes needed".)`

---

## Evidence (Level 3)

### 3.1 — Pillar with no supporting evidence

**RED:**

> **Pillar 1:** The current vendor's price rises next year.
>
> - Its renewal quote is 18% above this year's rate.
>
> **Pillar 2:** The current vendor cannot scale to meet peak demand.

**GREEN:**

> **Pillar 1:** The current vendor's price rises next year.
>
> - Its renewal quote is 18% above this year's rate.
>
> **Pillar 2:** The current vendor cannot scale to meet peak demand.
>
> - [needs: evidence for "The current vendor cannot scale to meet peak demand"]

**Expected finding:** `[Level 3 — missing evidence] Pillar 1 carries evidence, so the input is in Level 3 scope, and Pillar 2 states a claim with none. Every pillar must then have at least one Level 3 evidence point: a data point, example, audit finding, or direct observation that proves the pillar claim. The draft supplies none, so mark the gap [needs: evidence for "The current vendor cannot scale to meet peak demand"] rather than writing figures.`

---

### 3.2 — Evidence that does not support its pillar

**RED:**

> **Pillar 1:** The framework reduces cost.
>
> - The framework uses a microservices architecture.
> - The framework has a dark-mode interface.
> - The vendor was founded in 2018.

**GREEN:**

> **Pillar 1:** The framework reduces cost.
>
> - [needs: evidence for "The framework reduces cost"]
>
> **Pillar 2:** [needs: second supporting argument]
>
> - [needs: evidence for Pillar 2]

**Expected finding:** `[Level 3 — evidence misalignment] The three Level 3 points (architecture, interface, founding year) do not support the pillar claim (cost reduction). Each Level 3 point must directly prove the pillar above it. The input has no other heading, so they support nothing in the document and step 4 deletes them. Mark the gap [needs: evidence for "The framework reduces cost"]; do not write cost figures the draft lacks.` `[Level 2 — insufficient pillars] The draft argues one reason, so add Pillar 2: [needs: second supporting argument] with its evidence marker; do not write a second reason.`

---

### 3.3 — Draft supplies evidence for one pillar only

**RED:**

> We propose moving inspection logging to tablets. Field crews log inspections on paper, and a clerk keys them in each Friday. Supervisors report that defects reach them up to a week after the crew finds them. Paper forms also go missing.

**GREEN:**

> We propose moving inspection logging to tablets. Field crews log inspections on paper, and a clerk keys them in each Friday. Supervisors report that defects reach them up to a week after the crew finds them. Paper forms also go missing. [needs: evidence for "Paper forms also go missing"]

**Expected finding:** `[Level 3 — missing evidence] The draft supports its first reason (Friday keying and supervisors' reports of week-old defects) but gives no evidence for its second, "Paper forms also go missing": the first reason carries a time (each Friday) and a named observer (supervisors), while the second is a bare assertion. Mark the gap as [needs: evidence for "Paper forms also go missing"] and list it under Gaps; do not supply a figure or incident. The draft is prose and already answer-first, so it stays prose; do not convert it to a pillar outline or add a third reason.`

---

### 3.4 — Counter-evidence under the wrong pillar is relocated, not deleted

**RED:**

> **We should switch the field crews' radios to the trunked network.**
>
> **Pillar 1:** The trunked network costs nothing extra to run.
> - The carrier contract already covers trunked use at no extra charge.
> - Two pumping stations still have indoor dead spots that the carrier has not yet fixed.
>
> **Pillar 2:** The network is ready now.
> - Coverage testing finished at all nine pumping stations in August.

**GREEN:**

> **We should switch the field crews' radios to the trunked network.**
>
> **Pillar 1:** The trunked network costs nothing extra to run.
> - The carrier contract already covers trunked use at no extra charge.
>
> **Pillar 2:** The network is ready now.
> - Coverage testing finished at all nine pumping stations in August.
>
> **Risks and open items:**
> - Two pumping stations still have indoor dead spots that the carrier has not yet fixed.

**Expected finding:** `[Level 3 — evidence misalignment] "Two pumping stations still have indoor dead spots" does not support Pillar 1 (cost). It qualifies Pillar 2's readiness claim, so it is counter-evidence, not a rogue point: relocate it under Risks and open items, or attach it to Pillar 2. Do not delete it.`

---

## Blink Test

### 4.1 — Headers do not tell a complete story

**RED:**

```
# Technology Platform Review
## Background
## Vendor Analysis
## Considerations
## Summary
```

**GREEN:**

```
# [needs: recommendation]
## Background
## [needs: claim for Vendor Analysis]
## [needs: claim for Considerations]
## Summary
```

**Expected finding:** `[Blink test — topic-label headers] FAIL. Reading the headings alone — "Vendor Analysis," "Considerations" — does not tell a complete story. Each is a topic label rather than a claim. "Background" and the closing "Summary" are framing headings, exempt from the claim-header rule and the blink test, so they stay unchanged. The H1 "Technology Platform Review" is a topic label too: it becomes the governing thought. Rewrite to carry the document's argument in the headings alone. The draft gives headings only and no claims, so each rewrite is a [needs: …] marker.`

---

### 4.2 — Headerless memo that already passes (must stay unflagged)

**RED (input to review):**

> We will open the east lot for overnight crew parking from 3 March. The west lot fills by 9 p.m. on shift-change nights, so late crews park on the street. The east lot already has lights and a fence, so it needs no new work. Security already patrols it every two hours. Please tell your crews before the end of February.

**GREEN (expected output — returned unchanged):**

Same as RED.

**Expected finding:** `(No finding — the memo has no headers, so the blink test reads first sentences only. The memo is one paragraph with no subject line, and its first sentence states the decision. The next three sentences give two reasons, that the west lot overflows on shift-change nights and that the east lot is ready, and the last asks readers to pass the decision on; none argues a separate point. Each reason carries its own evidence (the 9 p.m. fill time; the lights, fence, and two-hourly patrol), so neither needs a [needs: evidence …] marker. Every verb is active with its actor named. Blink test: PASS (first sentences). Skill should say "No structural changes needed" and leave the memo as prose, not convert it to an outline or add headers.)`

---

## Language Quality

### 5.1 — Corporate filler language

**RED:**

> We need to leverage our core competencies to optimize the value-add of this paradigm shift, creating synergy across all workstreams.

**GREEN:**

> We need to use our core strengths to get the most value from this fundamental change and help all workstreams work together.

**Expected finding:** `[Language — corporate filler] "Leverage," "optimize," "value-add," "paradigm shift," "synergy" — banned vocabulary per the quality checklist. Rewrite with plain verbs and plain words. "Core competencies" is jargon too. The draft names no specific strength, result, change, or benefit, and no rule calls for one, so the rewrite states none and adds no marker.`

---

### 5.2 — Sentence exceeds 22 words / passive voice

**RED:**

> It has been determined by the steering committee that the existing framework, which was developed in 2021 and has not been substantially updated since that time, is no longer sufficient to meet the current operational requirements of the program.

**GREEN:**

> The steering committee determined that the existing framework no longer meets the program's current operational requirements. [needs: actor] developed it in 2021. [needs: actor] has not substantially updated it since that time.

**Expected finding:** `[Language — sentence length and passive voice] The sentence is 39 words and uses passive voice ("has been determined," "was developed," "has not been substantially updated"). Rewrite in active voice with no sentence longer than 22 words. The steering committee is the named actor of "determined". The draft names no actor for "was developed" or "has not been substantially updated", so the rewrite uses [needs: actor] for each and lists both under Gaps.`

---

### 5.3 — Quotation, unknown actor, and product name (must stay unflagged)

**RED (input to review):**

> We must shorten our applicant-records policy and purge the old records this term. The regulator's guidance says: "Personal data held about applicants shall be deleted once it is no longer needed, and in any case no later than six months after the intake closes." Our policy keeps these records for 24 months. Some 2022 records were exposed in an incident whose source is still unknown. The purge can start this term: the tool runs on Kestrel Storage Optimization, which already manages our file servers.

**GREEN (expected output — returned unchanged):**

Same as RED.

**Expected finding:** `(No finding — the long sentence is a lead-in plus a 27-word verbatim quotation, which step 6 does not rewrite. "Were exposed" stays passive because the draft says the actor (the incident's source) is unknown; no [needs: actor]. "Kestrel Storage Optimization" is a product name, not the filler word "optimize". The conclusion comes first and every later sentence supports it: the quotation and the 24-month policy show why the policy must change, the exposure shows the cost of keeping records, and the last sentence shows the purge can start this term. No structural finding either. Each reason is a specific sentence (a named source, a figure, a date, a named system), so no evidence marker applies.)`

---

### 5.4 — Language checks skipped inside writing-workflow

**Scenario:** pyramid-editor's Rewrite job, called from writing-workflow Step 2, receives this outline.

**RED:**

> **Adopt one shared help desk for all campuses by May.**
>
> **Pillar 1:** A single shared desk would remove the duplicated overnight rotas that each of the nine campuses currently runs on its own every week.
> - The nine campuses each staff their own overnight rota.
>
> **Pillar 2:** It gives callers one number.

**GREEN:**

> **Adopt one shared help desk for all campuses by May.**
>
> **Pillar 1:** A single shared desk would remove the duplicated overnight rotas that each of the nine campuses currently runs on its own every week.
> - The nine campuses each staff their own overnight rota.
>
> **Pillar 2:** It gives callers one number.
> - [needs: evidence for "It gives callers one number"]

**Expected finding:** `[Level 3 — missing evidence] Pillar 1 carries evidence and Pillar 2 ("It gives callers one number") has none; mark [needs: evidence for "It gives callers one number"] and list it under Gaps. Inside writing-workflow, step 6 and the language checklist items are skipped, so Pillar 1's 23-word sentence is not flagged here; plain-language handles it at Step 4. The workflow's handoff does not override pyramid-editor's keep-the-input's-form rule, so the outline comes back as an outline.`

---

## Verification Log

**Verified 2026-10-22.** Result: **21/21 passed.** Graded by an Opus agent reading `SKILL.md` and `TESTS.md`, and `writing-workflow/SKILL.md` for the Step 2 governing-thought handoff in 1.4 and the Step 2 and Step 4 references and the handoff rule in 5.4, with no edit to either file afterwards.

Produced against `TESTS.md` body sha256 `ea579ddc56fed35d` and `SKILL.md` sha256 `4a46c3e2be416154`. The body hash covers everything above this heading, so it survives this table being written. Recompute both before trusting the rows: any later edit invalidates them, and a log that certifies rather than records hides the defects it exists to surface.

| Test                                                              | RED flags | GREEN clean | Pass |
|-------------------------------------------------------------------|-----------|-------------|------|
| 1.1 — Buried recommendation (lede buried)                         | ✓         | ✓           | PASS |
| 1.2 — No governing thought (topic statement only)                 | ✓         | ✓           | PASS |
| 1.3 — Conditional recommendation keeps its conditions             | ✓         | ✓           | PASS |
| 1.4 — Governing thought supplied by the caller is used as written | ✓         | ✓           | PASS |
| 2.1 — Too few pillars (one pillar)                                | ✓         | ✓           | PASS |
| 2.2 — Too many pillars (group, do not narrow)                     | ✓         | ✓           | PASS |
| 2.3 — Non-MECE pillars (overlap)                                  | ✓         | ✓           | PASS |
| 2.4 — Mixed abstraction levels in pillars                         | ✓         | ✓           | PASS |
| 2.5 — Pillars not ordered consistently                            | ✓         | ✓           | PASS |
| 2.6 — Draft argues only one reason                                | ✓         | ✓           | PASS |
| 2.7 — Framing and back-matter sections are not pillars            | ✓         | ✓           | PASS |
| 3.1 — Pillar with no supporting evidence                          | ✓         | ✓           | PASS |
| 3.2 — Evidence that does not support its pillar                   | ✓         | ✓           | PASS |
| 3.3 — Draft supplies evidence for one pillar only                 | ✓         | ✓           | PASS |
| 3.4 — Counter-evidence under the wrong pillar                     | ✓         | ✓           | PASS |
| 4.1 — Headers do not tell a complete story                        | ✓         | ✓           | PASS |
| 4.2 — Headerless memo that already passes                         | ✓         | ✓           | PASS |
| 5.1 — Corporate filler language                                   | ✓         | ✓           | PASS |
| 5.2 — Sentence exceeds 22 words / passive voice                   | ✓         | ✓           | PASS |
| 5.3 — Quotation, unknown actor, and product name                  | ✓         | ✓           | PASS |
| 5.4 — Language checks skipped inside writing-workflow             | ✓         | ✓           | PASS |

Counts checked with a Python whitespace split (tokens containing a letter or digit): 5.2 RED 39 words, GREEN 16, 6 and 10; 5.3 quotation 27 words (lead-in 4); 5.4 Pillar 1 23 words (label excluded); 1.3 GREEN governing thought 22 words and 5.1 GREEN 22 words (at the limit, not over); 2.1 RED Pillar 1 22 words. No GREEN adds a figure, name, or date absent from its RED, except 1.4's "30 June", which comes from the caller-supplied governing thought. No FAIL rows.

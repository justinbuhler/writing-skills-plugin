# Document QA Skill — Red/Green Test Suite

Each test has:

- **RED:** text that violates the check (should be flagged)
- **GREEN:** text that passes the check (should be clean)
- **Expected finding:** what the skill should flag in the RED case

A GREEN that carries a `[needs: …]` marker is Fix-mode output: the document lacks that detail, so the marker is the correct result and is listed under **Gaps**. Do not count the marker against the GREEN.

Bold labels such as **Section 2:** stand in for section headings; they are not bold-label findings.

Each excerpt is part of a longer, unseen document unless a context note says it is the whole document. Only the rule under test and rules checkable within the excerpt are assessed; a figure with no source in the excerpt is not a failure unless the test says the excerpt is the whole document.

---

## QA Area 1: Heading Hierarchy and Sequence

### 1.1 — Skipped heading level

**RED:**

```
# Support Model

### Priority Definitions

### Priority Assignment
```

**GREEN:**

```
# Support Model

## Priority Definitions

## Priority Assignment
```

**Expected finding:** `[Area 1 — hierarchy, Structural] H3 headings "Priority Definitions" and "Priority Assignment" appear directly under H1 with no H2 parent. Promote both to H2.`

---

### 1.2 — Single sub-heading (should be absorbed)

**RED:**

```
## Findings

### Missed Reporting Deadlines
Three of five districts missed the reporting deadline.
```

**GREEN:**

```
## Findings
Three of five districts missed the reporting deadline.
```

**Expected finding:** `[Area 1 — hierarchy, Structural] "Missed Reporting Deadlines" is the only child under "Findings." A single sub-heading serves no purpose — absorb its content into the parent section or remove the sub-heading.`

---

### 1.3 — Recommendations before findings

**RED:**

```
## Recommendations
- Redesign the intake process by March 1.
- Assign a dedicated case manager per district.

## Current State
The current process has 14 manual handoffs and averages 8 days.
```

**GREEN:**

```
## Current State
The current process has 14 manual handoffs and averages 8 days.

## Recommendations
- Redesign the intake process by March 1.
- Assign a dedicated case manager per district.
```

**Expected finding:** `[Area 1 — sequence, Structural] Recommendations appear before the findings that justify them. The reader has not yet been shown the evidence. Move "Current State" before "Recommendations."`

---

### 1.4 — Non-parallel headings at the same level

**RED:**

```
## Vendor Landscape
## Why the Current Contract Is Failing
## Transition
```

**GREEN:**

```
## Vendor Landscape
## Reasons the Current Contract Is Failing
## Transition
```

**Expected finding:** `[Area 1 — parallelism, Polish] Headings at H2 level are not grammatically parallel: "Why the Current Contract Is Failing" (subordinate clause) breaks the noun-phrase pattern of "Vendor Landscape" and "Transition". Rewrite it as a noun phrase. The within-kind exemption does not apply: none of the three headings is a claim heading.`

---

### 1.5 — Skipped level below a front-matter title

**RED:**

```
---
title: Label Printer Readiness Review
---

## Printer Firmware

#### Version Rollout

#### Rollback Plan

## Spare Stock
```

**GREEN:**

```
---
title: Label Printer Readiness Review
---

## Printer Firmware

### Version Rollout

### Rollback Plan

## Spare Stock
```

**Expected finding:** `[Area 1 — hierarchy, Structural] H4 headings "Version Rollout" and "Rollback Plan" appear directly under the H2 "Printer Firmware" with no H3 parent. Promote both to H3. Not flagged: the H2s have no H1 heading because the front-matter title is the H1.`

---

## QA Area 2: Title and Heading Clarity

### 2.1 — Vague heading

**RED:**

```
## Overview

The home-visit service has grown significantly over the past five years.
```

**GREEN:**

```
## Five years of home-visit service growth

The home-visit service has grown significantly over the past five years.
```

**Expected finding:** `[Area 2 — vague heading, Polish] "Overview" could apply to any section of any document. Rewrite to describe what this section actually contains, e.g., "Five years of home-visit service growth." A heading such as "How the home-visit service grew" would promise an explanation the body does not give.`

---

### 2.2 — Heading-body promise broken

**RED:**

```
## Risks of operating without a framework

When the program launched in 2019, the agency relied on ad hoc coordination between regional offices. Over time, this approach proved effective for smaller cohorts.
```

**GREEN:**

```
## How regional offices coordinated after the 2019 launch

When the program launched in 2019, the agency relied on ad hoc coordination between regional offices. Over time, this approach proved effective for smaller cohorts.
```

**Expected finding:** `[Area 2 — heading-body promise, Structural] The heading promises specific risks; the section describes program history instead. Either rewrite the heading to match the content ("How regional offices coordinated after the 2019 launch") or rewrite the content to enumerate the specific risks, which the author must supply because the section names none.`

---

### 2.3 — Mixed topic-label and claim-heading convention

**RED:**

```
## Every depot vehicle falls into one of four service classes
## Inspection Status
## Governance Recommendations
```

_(The first section describes the service class framework; the second reports the inspection findings; the third sets out the governance recommendations.)_

**GREEN:**

```
## Vehicle Service Class Framework
## Inspection Status
## Governance Recommendations
```

**Expected finding:** `[Area 2 — heading convention, Polish] The H2 headings follow neither accepted pattern: the context section has a claim heading ("Every depot vehicle falls into one of four service classes") while the findings and recommendations sections have topic labels ("Inspection Status," "Governance Recommendations"). Use one form throughout, or topic labels for context and claims for findings. With all topic labels, the context heading becomes "Vehicle Service Class Framework." [Area 1 — parallelism, Polish] The clause heading "Every depot vehicle falls into one of four service classes" breaks the noun-phrase pattern of "Inspection Status" and "Governance Recommendations"; because the headings follow neither Area 2 pattern, parallelism is checked across all three. [Area 1 — capitalization, Polish] "Every depot vehicle falls into one of four service classes" is in sentence case while the other two headings are in title case. The topic-label rewrite fixes both.`

---

### 2.4 — Vague heading among standard section names

**RED:**

```
## Executive Summary
The new till software is live in 11 of 14 stores.

Finish till testing at the remaining three stores.

## Background
Tills moved to the new payment provider in April.

## Additional Information
The help desk closes at 22:00 on Saturdays.

## Next Steps
Finish till testing at the remaining three stores.
```

_(Excerpt: the findings sections are omitted.)_

**GREEN:**

```
## Executive Summary
The new till software is live in 11 of 14 stores.

Finish till testing at the remaining three stores.

## Background
Tills moved to the new payment provider in April.

## Saturday Help Desk Closing Time
The help desk closes at 22:00 on Saturdays.

## Next Steps
Finish till testing at the remaining three stores.
```

**Expected finding:** `[Area 2 — vague heading, Polish] "Additional Information" could apply to any section of any document; its section gives the help desk's Saturday closing time. Rewrite it in the form of the other headings, e.g., "Saturday Help Desk Closing Time." Not flagged: "Executive Summary," "Background," and "Next Steps" are standard section names doing their jobs.`

---

## QA Area 3: Content Alignment

### 3.1 — First sentence does not state the paragraph's main point

**RED:**

> The agency was established in 1989. It has grown to serve 14 districts. The core issue is that manual data entry creates a 3-day backlog at every approval step.

**GREEN:**

> The core issue is that manual data entry creates a 3-day backlog at every approval step.

_(The founding year and district count move to the background section.)_

**Expected finding:** `[Area 3 — paragraph alignment, Structural] The first sentence ("The agency was established in 1989") is background, not the paragraph's main point. The main point — manual data entry causing a backlog — is buried at the end. Move it to the first sentence, and move the founding year and district count to the background section.`

---

### 3.2 — Mixed-type list

**RED:**

> The process has four problems:
>
> - 14 manual handoffs
> - Reviewing officers should be notified within 48 hours
> - The average cycle time is 8 days
> - Delays compound at district boundaries

**GREEN:**

> The process has three problems:
>
> - 14 manual handoffs
> - An average cycle time of 8 days
> - Delays that compound at district boundaries

_(The recommendation "Reviewing officers should be notified within 48 hours" moves to the recommendations section.)_

**Expected finding:** `[Area 3 — list alignment, Polish] The list mixes observations ("14 manual handoffs," "average cycle time is 8 days") with a recommendation ("Reviewing officers should be notified within 48 hours"). All items must be the same type. Move the recommendation to the recommendations section and change "four problems" to "three problems." The items also mix a noun phrase ("14 manual handoffs") with full clauses ("The average cycle time is 8 days," "Delays compound at district boundaries"), a parallel-structure failure; make them all noun phrases.`

---

### 3.3 — Figure without introduction

**RED:**

> The approval process has multiple failure points across the district network.
>
> **Figure 4: District Approval Flowchart**
>
> As shown in the table above, the bottleneck is at step 7.

_(No table appears anywhere earlier in the document. Figure 4 shows several failure points; step 7 is the largest.)_

**GREEN:**

> The approval process has multiple failure points across the district network. Figure 4 maps the approval steps and shows the bottleneck at step 7.
>
> **Figure 4: District Approval Flowchart**

**Expected finding:** `[Area 3 — figure alignment, Structural] Figure 4 appears without being introduced in the prose before it. Add a sentence referencing Figure 4 before the exhibit. [Area 6 — cross-reference, Blocking] The prose refers to "the table above", but no table precedes it; the exhibit is a flowchart. Point the reference at Figure 4. Not flagged separately: orphaned evidence, because the prose does point at the exhibit, under the wrong label.`

---

### 3.4 — Table row missing a required value

**RED:**

> The table below lists the three cutover decisions, with the owner and due date of each.
>
> | Decision | Owner | Due |
> |---|---|---|
> | Freeze new account requests | Identity lead | 3 May |
> | Switch sign-in to the new directory | | 10 May |
> | Retire the legacy library terminal app | Campus services manager | 17 May |

**GREEN:**

> The table below lists the three cutover decisions, with the owner and due date of each.
>
> | Decision | Owner | Due |
> |---|---|---|
> | Freeze new account requests | Identity lead | 3 May |
> | Switch sign-in to the new directory | [needs: owner] | 10 May |
> | Retire the legacy library terminal app | Campus services manager | 17 May |

**Expected finding:** `[Area 3 — table alignment, Structural] The "Switch sign-in to the new directory" row has an empty Owner cell, so the table is incomplete. The document names no owner for this decision; the author must supply one. In a fix, write [needs: owner] in the cell and list it under Gaps.`

---

## QA Area 4: Repetition and Redundancy

### 4.1 — Cross-section repetition

**RED:**

> **Section 3 — Findings:**
> The process averages 8 days end-to-end, exceeding the 5-day target by 60%.
>
> **Section 4 — Implications:**
> The process averages 8 days, exceeding the 5-day target by 60%. This creates downstream scheduling conflicts.

**GREEN:**

> **Section 3 — Findings:**
> The process averages 8 days end-to-end, exceeding the 5-day target by 60%.
>
> **Section 4 — Implications:**
> The overage against the 5-day target (see Section 3) creates downstream scheduling conflicts.

**Expected finding:** `[Area 4 — cross-section repetition, Polish] The finding "averages 8 days end-to-end, exceeding the 5-day target by 60%" is restated in Section 4, word for word except for the dropped "end-to-end," before the implication is added. Replace the restatement with a cross-reference ("see Section 3") and move directly to the implication. Not flagged separately: section-level re-introduction; a repeated specific point is reported once, as cross-section repetition. Not flagged separately: paragraph alignment in Section 4, whose first sentence is the restatement; the cross-reference fix puts the implication first.`

---

### 4.2 — Executive summary introduces new information

**RED:**

> **Executive Summary:**
> The utility serves 60,000 households across 14 districts.
>
> Three districts have not completed meter surveys.
>
> We recommend a two-track meter replacement programme and a new escalation protocol for stalled cases.

_(Body contains recommendations for the meter replacement programme only; escalation protocol does not appear in the body.)_

**GREEN:**

> **Executive Summary:**
> The utility serves 60,000 households across 14 districts.
>
> Three districts have not completed meter surveys.
>
> We recommend a two-track meter replacement programme.

**Expected finding:** `[Area 4 — exec summary introduces new information, Structural] The executive summary recommends "a new escalation protocol for stalled cases" but this recommendation does not appear anywhere in the body. Executive summaries synthesize — they do not originate. Either add the recommendation to the body or remove it from the exec summary.`

---

### 4.3 — Conclusion introduces a new fact

**RED:**

> **Findings:**
> Nine of the thirteen wards have wired nurse-call panels. Surveys at the other four are not booked, installs are scheduled only after a survey, and wiring must finish before the June go-live.
>
> **Conclusions:**
> Without surveys, the four remaining installs cannot be scheduled, which puts the June go-live at risk.
>
> The cabling contractor has also raised its day rate by 15%.

**GREEN:**

> **Findings:**
> Nine of the thirteen wards have wired nurse-call panels. Surveys at the other four are not booked, installs are scheduled only after a survey, and wiring must finish before the June go-live.
>
> The cabling contractor has also raised its day rate by 15%.
>
> **Conclusions:**
> Without surveys, the four remaining installs cannot be scheduled, which puts the June go-live at risk.

_(The day-rate increase moves from the conclusions to the findings.)_

**Expected finding:** `[Area 4 — conclusion introduces new information, Structural] "The cabling contractor has also raised its day rate by 15%" is a new fact that appears nowhere in the findings. Move it to the findings, or remove it. Not flagged: "puts the June go-live at risk" is an implication drawn from the findings, which is the job of a conclusions section. In the GREEN, the day-rate sentence is a prose observation in the findings, not orphaned evidence, although no conclusion cites it.`

---

## QA Area 5: Claim and Evidence Integrity

### 5.1 — Unsourced factual claim

**RED:**

> License costs will increase 40% over the next two years.

_(This excerpt is the whole document; no source for the 40% figure appears anywhere in it.)_

**GREEN:**

> License costs will increase 40% over the next two years [needs: source for "License costs will increase 40% over the next two years"].

**Expected finding:** `[Area 5 — unsourced assertion, Blocking] "License costs will increase 40% over the next two years" is a specific quantitative claim with no source, and the document contains none. Provide the source, label the figure as an estimate only if it is one, or remove the claim. In a fix, write [needs: source for "License costs will increase 40% over the next two years"] and list it under Gaps.`

---

### 5.2 — Overstated claim

**RED:**

> The new rota has eliminated overtime: depot overtime went from 640 hours in Q1 to 410 hours in Q2, the rota's first quarter.

**GREEN:**

> Depot overtime fell in the new rota's first quarter but was not eliminated: it went from 640 hours in Q1 to 410 hours in Q2.

**Expected finding:** `[Area 5 — overstated claim, Structural] "The new rota has eliminated overtime" exceeds the evidence in the same sentence: overtime fell from 640 to 410 hours, so 410 hours remain, and the figures show only that the fall came in the rota's first quarter, not that the rota caused it. Rewrite the claim to match the evidence.`

---

### 5.3 — Orphaned evidence

**RED:**

> **Figure 2: Case Volume by District (2023–2025)**
> _(Chart showing a 34% volume increase in District 7)_
>
> _(The chart appears under "Program History" and is never referenced in the analysis or recommendations.)_

**GREEN:**

> Figure 2 shows case volume by district for 2023 to 2025, including a 34% increase in District 7. [needs: the claim Figure 2 supports]
>
> **Figure 2: Case Volume by District (2023–2025)**
> _(Chart showing a 34% volume increase in District 7)_

**Expected finding:** `[Area 5 — orphaned evidence, Structural] Figure 2 (case volume by district) appears in the document but is never referenced in the analysis or tied to any claim. Introduce it in the prose and connect it to an argument; the author must supply the claim it supports. [Area 3 — figure alignment, Structural] Figure 2 is not introduced in the prose before it appears.`

---

### 5.4 — Author adopts a quotation as a finding

**RED:**

> One shift supervisor said: "Scanning in the freezer is a total disaster." Scans failed 412 times in the cold store in May. Cold-store scanning is therefore unusable, and the handheld scanners must be replaced.

**GREEN:**

> One shift supervisor said: "Scanning in the freezer is a total disaster." Scans failed 412 times in the cold store in May.

**Expected finding:** `[Area 5 — overstated claim, Structural] The author turns the supervisor's quotation into the finding "Cold-store scanning is therefore unusable, and the handheld scanners must be replaced", which the evidence in the same passage (412 failed scans in May) does not support. Cut the author's sentence or reduce it to what the evidence shows; here the preceding sentence already states that, so the rewrite cuts it. Not flagged: the quotation itself, which is attributed evidence; its words stay unchanged. Not flagged separately: "the handheld scanners must be replaced" as an untraced recommendation; it sits in the overstated sentence, and the rewrite removes it. Not flagged separately: paragraph alignment, although the "therefore" sentence comes last; cutting it leaves the evidence as the paragraph's point.`

---

### 5.5 — Footnote marker with no note

**RED:**

> Replacement bin requests doubled between the two collection trials[^1].
>
> Each request takes 6 minutes to log on average[^2].
>
> [^1]: Depot request logs for both collection trials.

_(This excerpt is the whole document.)_

**GREEN:**

> Replacement bin requests doubled between the two collection trials[^1].
>
> Each request takes 6 minutes to log on average [needs: source for "Each request takes 6 minutes to log on average"].
>
> [^1]: Depot request logs for both collection trials.

**Expected finding:** `[Area 6 — cross-reference, Blocking] Footnote marker [^2] has no note, so "Each request takes 6 minutes to log on average" is unsourced (Area 5). Supply the note, which the author must provide, or remove the marker and the claim. In a fix, write [needs: source for "Each request takes 6 minutes to log on average"] and list it under Gaps.`

---

## QA Area 6: Internal Consistency

### 6.1 — Terminology inconsistency

**RED:**

> **Section 2:** Clinical Directorates are responsible for defining ward roles.
>
> **Section 4:** CDs must submit their staffing plans by March 1.
>
> **Section 6:** Each business unit will receive a training allocation.

_(All three phrases refer to the same organizational unit.)_

**GREEN:**

> **Section 2:** Clinical Directorates (CDs) are responsible for defining ward roles.
>
> **Section 4:** CDs must submit their staffing plans by March 1.
>
> **Section 6:** Each CD will receive a training allocation.

**Expected finding:** `[Area 6 — terminology, Structural] The same organizational unit is called "Clinical Directorates," "CDs," and "business unit" across different sections. Define the term once on first use ("Clinical Directorates (CDs)") and use "CDs" consistently thereafter.`

---

### 6.2 — Numerical inconsistency

**RED:**

> **Executive Summary:** The program will require approximately 20,000 student accounts.
>
> **Section 3:** Provisioning must cover up to 18,500 accounts based on confirmed enrolments.

**GREEN:**

> **Executive Summary:** The program will require approximately 20,000 student accounts [needs: population for "approximately 20,000 student accounts"].
>
> **Section 3:** Provisioning must cover up to 18,500 accounts based on confirmed enrolments.

**Expected finding:** `[Area 6 — numerical consistency, Structural] The estimate "approximately 20,000" in the exec summary is above the ceiling "up to 18,500" that Section 3 states. If both figures cover the same accounts, the estimate falls outside the bound; Section 3's "based on confirmed enrolments" suggests they may cover different populations, but the document does not say which population the 20,000 covers. Add a note clarifying which population each figure covers, or state the shortfall. In a fix, write [needs: population for "approximately 20,000 student accounts"] and list it under Gaps.`

---

### 6.3 — Invalid cross-reference

**RED:**

> For the full risk register, see Section 3.2.
>
> _(The document has no Section 3.2 — Section 3 has no sub-sections.)_

**GREEN:**

> For the full risk register, see [needs: location of the full risk register].

**Expected finding:** `[Area 6 — cross-reference, Blocking] "See Section 3.2" points to a section that does not exist — Section 3 has no sub-sections. Update the cross-reference to the section that holds the risk register, which the author must identify, or add the sub-section.`

---

### 6.4 — One acronym with two expansions

**RED:**

```
## Key Terms

The table defines the terms this plan uses.

| Term | Definition |
|---|---|
| RBAC | Role-based access control: people get access through the role they hold. |

## Cutover Approach

The IT service desk moves depot staff into RBAC groups.

Every field engineer signs in through SSO (single sign-on).

During cutover, AMS (Asset Management System) opens tickets for meter faults.

## Group Sign-Off

AMS (Access Management Service) owners sign off each group.
```

_(Excerpt: no other section expands these acronyms.)_

**GREEN:**

```
## Key Terms

The table defines the terms this plan uses.

| Term | Definition |
|---|---|
| RBAC | Role-based access control: people get access through the role they hold. |

## Cutover Approach

The IT service desk moves depot staff into RBAC groups.

Every field engineer signs in through SSO (single sign-on).

During cutover, AMS (Asset Management System) opens tickets for meter faults.

## Group Sign-Off

AMS [needs: whether this AMS is the Asset Management System or a separate system that needs its own acronym; the draft says "Access Management Service"] owners sign off each group.
```

**Expected finding:** `[Area 6 — terminology, Structural] "AMS" is expanded as "Asset Management System" in Cutover Approach and "Access Management Service" in Group Sign-Off. Confirm whether these are two systems; if so, give one a distinct acronym, otherwise use the correct expansion in both places. The document does not say, so the author must supply it. Not flagged: "RBAC" (Key Terms entry), "SSO (single sign-on)" (an acronym-first parenthetical is a definition), "IT" (general-audience acronym), and the prose Definition column.`

---

### 6.5 — Table total does not match its rows

**RED:**

> The rollout plans 9,000 staff accounts.
>
> Table 2 lists planned accounts by tier.
>
> **Table 2: Planned accounts by tier**
>
> | Tier | Role group | Planned accounts |
> |---|---|---|
> | Tier 1 | Shop floor | 5,120 |
> | Tier 2 | Store managers | 2,460 |
> | Tier 3 | Head office | 1,310 |
> | Total | | 8,990 |

**GREEN:**

> The rollout plans approximately 9,000 staff accounts.
>
> Table 2 lists planned accounts by tier.
>
> **Table 2: Planned accounts by tier**
>
> | Tier | Role group | Planned accounts |
> |---|---|---|
> | Tier 1 | Shop floor | 5,120 |
> | Tier 2 | Store managers | 2,460 |
> | Tier 3 | Head office | 1,310 |
> | Total | | [needs: confirm the Total or the wrong row; the rows sum to 8,890] |

**Expected finding:** `[Area 6 — numerical consistency, Blocking] The Total row says 8,990, but the tier rows sum to 8,890 (5,120 + 2,460 + 1,310). Correct the Total, or the row that is wrong. [Area 6 — numerical consistency, Polish] "9,000 staff accounts" is unqualified; it is within rounding of the rows' sum of 8,890 (110 apart, about 1.2%), so write it as approximate or give the exact figure. Not flagged: the blank Role group cell in the Total row, which is blank by design.`

---

### 6.6 — Bare TBD beside a TBD with its dependency

**RED:**

> The open decisions are listed in the table that follows.
>
> | Decision | Owner | Due |
> |---|---|---|
> | Choose the backup courier | Procurement lead | TBD - awaiting two quotes |
> | Approve offline dispatch | Warehouse manager | TBD |

**GREEN:**

> The open decisions are listed in the table that follows.
>
> | Decision | Owner | Due |
> |---|---|---|
> | Choose the backup courier | Procurement lead | TBD - awaiting two quotes |
> | Approve offline dispatch | Warehouse manager | [needs: due date] |

**Expected finding:** `[Area 6 — placeholder, Blocking] The Due cell for "Approve offline dispatch" is a bare "TBD" left from drafting. Supply the date, which the author must provide; in a fix, write [needs: due date] and list it under Gaps. Not flagged: "TBD - awaiting two quotes", which states its dependency and is a status.`

---

### 6.7 — Value outside a stated range

**RED:**

> **Executive Summary:** The contact centre will staff 8–10 agents per shift.
>
> Recycling drop-off will run at no fewer than 6 depots.
>
> **Section 4:** The rota schedules 11 agents on the peak day shift.
>
> Drop-off points are confirmed at 7 depots.

**GREEN:**

> **Executive Summary:** The contact centre will staff 8–10 agents per shift.
>
> Recycling drop-off will run at no fewer than 6 depots.
>
> **Section 4:** The rota schedules 11 agents on the peak day shift [needs: whether the peak day shift is an exception to the 8–10 range, or whether the range or the 11 is wrong].
>
> Drop-off points are confirmed at 7 depots.

**Expected finding:** `[Area 6 — numerical consistency, Structural] Section 4 schedules 11 agents on the peak day shift, outside the "8–10 agents per shift" range in the executive summary. The author must say whether the peak day shift is an exception to the range or one of the two figures is wrong. Not flagged: 7 depots meets "no fewer than 6 depots".`

---

## Verification Log

**Verified 2026-10-22.** Result: **28/28 passed.** Graded by an Opus agent reading `SKILL.md` and `TESTS.md`, with no edit to either file afterwards. The skill has no `references/`.

Produced against `TESTS.md` body sha256 `756594b35fde7f23` and `SKILL.md` sha256 `d77f5acfc6c16925`. The body hash covers everything above this heading, so it survives this table being written. Recompute both before trusting the rows: any later edit invalidates them, and a log that certifies rather than records hides the defects it exists to surface.

Excerpts were read as parts of longer documents, per the header at line 13, except where a context note says otherwise; in 5.1 and 5.5, whose notes make the excerpt the whole document, every rule applies. Each Expected finding's tier was checked against the checklist tag it cites, and each GREEN was checked against every rule in the skill and for facts, figures, names or actors absent from its RED; `[needs: …]` markers were read as Fix-mode output per line 9. Precedence rules at `SKILL.md:180` (4.1), `SKILL.md:209` (5.4) and the orphaned-evidence rule at `SKILL.md:217` (3.3 wrong-label reference, 4.3 prose observation, 5.3 unreferenced chart) were applied as written; 5.3 has no reference of any kind, so the new wrong-label sentence does not reach it. 6.7's GREEN marker and finding now name the same three possibilities (exception, range wrong, 11 wrong). The worked examples in `SKILL.md` (lines 78–79, 108–110, 209, 227–229, 258–260) were checked against the skill's own rules; none breaks one.

Counts were checked with a Python script: 3.2 lists four items under "four problems" and its GREEN three under "three problems"; 3.4 has three decision rows and 6.6 two; 1.1 has two H3s and 1.5 two H4s; 4.1's two sentences differ only by "end-to-end" (8 days against a 5-day target is 60% over); 4.3's thirteen wards less nine leaves four; 2.4's 14 stores less 11 leaves three; 6.5's rows sum to 8,890 (110 below 9,000, about 1.22%; 100 below the stated Total of 8,990); 6.7's 11 exceeds 8–10 and 7 meets "no fewer than 6"; 6.2's 20,000 exceeds "up to 18,500".

FAIL notes: none.

| Test                                                           | RED flags | GREEN clean | Pass |
|----------------------------------------------------------------|-----------|-------------|------|
| 1.1 — Skipped heading level                                    | ✓         | ✓           | PASS |
| 1.2 — Single sub-heading (should be absorbed)                  | ✓         | ✓           | PASS |
| 1.3 — Recommendations before findings                          | ✓         | ✓           | PASS |
| 1.4 — Non-parallel headings at the same level                  | ✓         | ✓           | PASS |
| 1.5 — Skipped level below a front-matter title                 | ✓         | ✓           | PASS |
| 2.1 — Vague heading                                            | ✓         | ✓           | PASS |
| 2.2 — Heading-body promise broken                              | ✓         | ✓           | PASS |
| 2.3 — Mixed topic-label and claim-heading convention           | ✓         | ✓           | PASS |
| 2.4 — Vague heading among standard section names               | ✓         | ✓           | PASS |
| 3.1 — First sentence does not state the paragraph's main point | ✓         | ✓           | PASS |
| 3.2 — Mixed-type list                                          | ✓         | ✓           | PASS |
| 3.3 — Figure without introduction                              | ✓         | ✓           | PASS |
| 3.4 — Table row missing a required value                       | ✓         | ✓           | PASS |
| 4.1 — Cross-section repetition                                 | ✓         | ✓           | PASS |
| 4.2 — Executive summary introduces new information             | ✓         | ✓           | PASS |
| 4.3 — Conclusion introduces a new fact                         | ✓         | ✓           | PASS |
| 5.1 — Unsourced factual claim                                  | ✓         | ✓           | PASS |
| 5.2 — Overstated claim                                         | ✓         | ✓           | PASS |
| 5.3 — Orphaned evidence                                        | ✓         | ✓           | PASS |
| 5.4 — Author adopts a quotation as a finding                   | ✓         | ✓           | PASS |
| 5.5 — Footnote marker with no note                             | ✓         | ✓           | PASS |
| 6.1 — Terminology inconsistency                                | ✓         | ✓           | PASS |
| 6.2 — Numerical inconsistency                                  | ✓         | ✓           | PASS |
| 6.3 — Invalid cross-reference                                  | ✓         | ✓           | PASS |
| 6.4 — One acronym with two expansions                          | ✓         | ✓           | PASS |
| 6.5 — Table total does not match its rows                      | ✓         | ✓           | PASS |
| 6.6 — Bare TBD beside a TBD with its dependency                | ✓         | ✓           | PASS |
| 6.7 — Value outside a stated range                             | ✓         | ✓           | PASS |

Counts: 28 tests, 28 PASS, 0 PASS with discrepancy, 0 FAIL.

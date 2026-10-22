# Recommendations and Actions Skill — Red/Green Test Suite

Each test has:

- **RED:** statement with a quality failure (should be flagged)
- **GREEN:** corrected version at the right level
- **Expected finding:** what the skill should identify

---

## Level 1 — Observation (Finding)

### 1.1 — Observation is an interpretation, not a fact

**RED:**

> **Interview notes:** Three of five ward managers said they did not know who approves agency staff bookings. Two separate wards submitted conflicting rota change requests in the same two-week period.
>
> **Finding:** The governance model lacks clarity and creates confusion across the organization.

**GREEN:**

> **Interview notes:** Three of five ward managers said they did not know who approves agency staff bookings. Two separate wards submitted conflicting rota change requests in the same two-week period.
>
> **Finding:** Three of five ward managers said they did not know who approves agency staff bookings. Two separate wards submitted conflicting rota change requests in the same two-week period.

**Expected finding:** `[L1 Observation quality] "Lacks clarity and creates confusion" is an interpretation, not a verifiable fact. State what was observed: who reported confusion, how many incidents, what specifically was witnessed. An observation must be something an auditor could confirm from a source.`

---

### 1.2 — Evaluative language in an observation

**RED:**

> Unfortunately, license costs increased 34% between 2023 and 2025, highlighting the organization's poor budget management.

**GREEN:**

> **Observation:** License costs increased 34% between 2023 and 2025.
>
> **Insight:** [needs: evidence for "poor budget management"]

**Expected finding:** `[L1 Observation quality] "Unfortunately" and "poor budget management" are evaluative. Observations must be neutral. Remove the editorial framing and state the fact. "Highlighting the organization's poor budget management" is an insight mixed into the observation: split it onto its own line, and because the source gives no evidence that budget management caused the rise, mark it [needs: evidence for "poor budget management"].`

---

### 1.3 — Percentage with no base or period

**RED:**

> The building permit portal holds 6,200 unprocessed applications. Rework accounts for 27% of tickets.

**GREEN:**

> The building permit portal holds 6,200 unprocessed applications. Rework accounts for 27% of [needs: which tickets] over [needs: period].

**Expected finding:** `[L1 Observation quality] "27% of tickets" states no base or period — which tickets, over what period — so an auditor cannot confirm it. The source gives neither, so the rewrite marks [needs: which tickets] and [needs: period]. "Holds" is present tense and is not a failure: an observation may use any tense.`

---

### 1.4 — Methodology, a met target, and an assumption stay unflagged

**RED:**

> We interviewed 18 stakeholders across four council depots between 9 and 27 March 2026 and read 11 process documents.
>
> Spare-parts dispatch met its three-day turnaround target in every week of the pilot.
>
> Assumption: the depot count stays at 38.

**GREEN:**

> We interviewed 18 stakeholders across four council depots between 9 and 27 March 2026 and read 11 process documents.
>
> Spare-parts dispatch met its three-day turnaround target in every week of the pilot.
>
> Assumption: the depot count stays at 38.

**Expected finding:** `(No finding — the first sentence is methodology and the last is a stated assumption; neither is a finding-chain statement, so neither is labeled or flagged. The turnaround sentence reports a met target, so it is not an orphan and needs no recommendation. The chain is assessed within the supplied text only. In a rewrite, all three are kept and listed under "Carried unchanged".)`

---

## Level 2 — Insight

### 2.1 — Insight restates the observation

**RED:**

> **Observation:** Shipping label reprints averaged 340 per month across the last two quarters. The reprint log shows most reprints fall in the first week after each carrier contract change, and most carry the reason code "service changed after print".
>
> **Insight:** This means a lot of labels are being reprinted.

**GREEN:**

> **Observation:** Shipping label reprints averaged 340 per month across the last two quarters. The reprint log shows most reprints fall in the first week after each carrier contract change, and most carry the reason code "service changed after print".
>
> **Insight:** Most reprints carry the reason code "service changed after print", and most fall in the week after each carrier contract change, which indicates labels are printed before the shipping service is final.

**Expected finding:** `[L2 Insight quality] "A lot of labels are being reprinted" restates the observation without adding interpretation. The insight must explain why the reprints happen — the mechanism behind the number — drawn from what the source supports (here, the reason code and timing in the reprint log), not a new fact.`

---

### 2.2 — Insight is a generic principle, not client-specific

**RED:**

> **Observation:** Three of five treatment plants have not completed their asset risk registers. All three are waiting on the asset condition standard, which the Asset Management team has not yet published.
>
> **Insight:** Incomplete risk registers are a common challenge in large utilities and often lead to delays.

**GREEN:**

> **Observation:** Three of five treatment plants have not completed their asset risk registers. All three are waiting on the asset condition standard, which the Asset Management team has not yet published.
>
> **Insight:** The common factor across the three plants is the unpublished asset condition standard: all three are waiting on it, so the delay sits with the Asset Management team, not with the plants.

**Expected finding:** `[L2 Insight quality] "A common challenge in large utilities" is a generic principle, not an insight specific to this client. The insight must explain what this observation means for this client's situation — not what risk register delays mean in general.`

---

## Level 3 — Implication

### 3.1 — Vague implication (no specific consequence)

**RED:**

> If the untested backup restore is not addressed, it could cause problems down the line.

**GREEN:**

> If the untested backup restore is not addressed, [needs: consequence], affecting [needs: who is affected].

**Expected finding:** `[L3 Implication quality] "Could cause problems down the line" is vague and creates no urgency. Name the specific consequence — cost, timeline impact, risk event, compliance exposure, or reputational damage — and scope it to who is affected. The source states none of these, so the rewrite marks each one [needs: …] rather than inventing a consequence or figure, and keeps the source's condition "If the untested backup restore is not addressed" without adding a deadline it does not state.`

---

### 3.2 — Implication confused with insight (Level 2 vs. Level 3)

**RED:**

> **Observation:** No software licensing policy has been agreed.
>
> **Insight:** Without an agreed software licensing policy, each department will independently request licenses based on assumptions rather than validated needs.

**GREEN:**

> **Observation:** No software licensing policy has been agreed.
>
> **Insight:** [needs: insight]
>
> **Implication:** Without an agreed software licensing policy, each department will independently request licenses based on assumptions rather than validated needs, [needs: cost or provisioning impact of those requests].

**Expected finding:** `[L2/L3 misclassification] The statement describes what will happen if the finding is left unaddressed — that is the implication (L3), not the insight (L2). The insight should explain what the observation means; the implication should name the cost of inaction. Split into separate labeled statements. The source states no insight beyond the observation, so the Insight is marked [needs: insight] rather than written by rewording the observation. [L3 Implication quality] Once moved to L3, "each department will independently request licenses based on assumptions" names a behaviour, not a consequence — no cost, timeline impact, or risk event. The source states none, so the rewrite marks [needs: cost or provisioning impact of those requests].`

---

### 3.3 — Conditional implication stays unflagged

**RED:**

> **Observation:** The checkout terminal vendor has missed two of its four interim milestones. Staff training on the new terminals starts in about 140 stores on 1 June, and each store needs its terminals installed to run the training. Terminals ship to stores only after the vendor passes its 30 April factory acceptance test; if it fails, the earliest retest is 15 May, and installation takes four weeks from shipment.
>
> **Implication:** If the vendor also fails the 30 April factory acceptance test, about 140 stores will reach the 1 June training start without terminals.

**GREEN:**

> **Observation:** The checkout terminal vendor has missed two of its four interim milestones. Staff training on the new terminals starts in about 140 stores on 1 June, and each store needs its terminals installed to run the training. Terminals ship to stores only after the vendor passes its 30 April factory acceptance test; if it fails, the earliest retest is 15 May, and installation takes four weeks from shipment.
>
> **Implication:** If the vendor also fails the 30 April factory acceptance test, about 140 stores will reach the 1 June training start without terminals.

**Expected finding:** `(No finding on the implication — it is conditional, but its consequence is specific (about 140 stores without terminals), dated, and grounded in the observations: a failed test means shipment no earlier than the 15 May retest, and four weeks of installation from then ends after 1 June. A conditional implication passes L3 when its consequence does; "not speculation" does not mean "unconditional".)`

---

## Level 4 — Recommendation

### 4.1 — Hedged recommendation ("consider" / "explore")

**RED:**

> The team should consider whether it might be worth exploring improvements to the intake process.

**GREEN:**

> [needs: owner] should [needs: specific change] to the intake process by [needs: date].

**Expected finding:** `[L4 Recommendation quality] "Consider whether it might be worth exploring" is an invitation to defer, not a recommendation. Replace with a direct verb, a named owner, and a deadline or milestone. "The team" names no owner and the source gives no change or date, so the rewrite carries [needs: owner], [needs: specific change], and [needs: date].`

---

### 4.2 — Recommendation doesn't address the implication

**RED:**

> **Implication:** Without action, the process backlog will grow to 14-day cycle times by Q3, exceeding the 5-day SLA and triggering a penalty clause.
>
> **Recommendation:** The team should invest in staff training to improve process knowledge.

**GREEN:**

> **Implication:** Without action, the process backlog will grow to 14-day cycle times by Q3, exceeding the 5-day SLA and triggering a penalty clause.
>
> **Recommendation:** [needs: owner] should [needs: specific change to the process] so that cycle time meets the 5-day SLA, and should invest in staff training to improve process knowledge, both by [needs: date].

**Expected finding:** `[L4 Recommendation–implication fit] The implication is about speed and SLA penalties; the recommendation addresses staff training. The recommendation must directly address the implication it responds to. If the implication is about cycle time, the recommendation must fix cycle time; the training recommendation can stay, but it cannot be the only response. [Ownership gap] "The team" names no owner, so the rewrite carries [needs: owner]. The source gives no date for either recommendation, so the rewrite carries [needs: date].`

---

### 4.3 — Wrong modal verb

**RED:**

> The Finance team may want to move unspent contingency into the device refresh line before the next cycle.

**GREEN:**

> The Finance team should move unspent contingency into the device refresh line before the next cycle.

**Expected finding:** `[L4 Modal verb] "May want to" signals permission or suggestion, not a recommendation. Use "must" (required, no discretion), "should" (recommended, judgment allowed), or "may" (permitted, reader's choice). "May want to" is not on this list — it obscures the recommendation entirely. The source states no requirement, so the rewrite uses "should", not "must", and keeps the action and the "before the next cycle" limit unchanged.`

---

### 4.4 — Missing owner and timing are marked, not invented

**RED:**

> If the patient-intake system pilot misses its 12 May readiness review, we should think about bringing in extra admissions staff.

**GREEN:**

> If the patient-intake system pilot misses its 12 May readiness review, [needs: owner] should bring in [needs: number] extra admissions staff by [needs: date].

**Expected finding:** `[L4 Recommendation quality] "Think about" is a hedge and "we" names no accountable owner. The source gives no owner, date, or number of staff, so the rewrite carries [needs: owner], [needs: date], and [needs: number] instead of an invented team, date, or headcount, keeps the condition "If the patient-intake system pilot misses its 12 May readiness review", and lists all three gaps under Gaps.`

---

### 4.5 — Study verb in place of a commitment

**RED:**

> The Service Desk should evaluate options for student self-service password reset.

**GREEN:**

> The Service Desk should [needs: specific change] for student self-service password reset by [needs: date].

**Expected finding:** `[L4 Recommendation quality] "Evaluate options" commits only to studying a change, not to making one — the same deferral as "explore". A study verb passes only when the study is itself the deliverable with an output and a date, and the source gives neither. The Service Desk is a named owner and stays; the change is marked [needs: specific change]. The source gives no date, so [needs: date].`

---

### 4.6 — Owner and deadline in the heading, evidence below: stays unflagged

**RED:**

> **Recommendation 2 — The Parking Permits team should issue permits from the verified address record before the Zone 3 rollout (14 September 2026)**
>
> **Owner:** Parking Permits Manager
>
> - Start issuing new permits from the verified address record alongside the application form.
> - Stop issuing from the application form before the Zone 3 rollout.
>
> **Why.** In the July zone, 96 of 610 permits (16%) were reissued because the address changed after issue. Permits are issued from the application form, which is filed before the address is verified. Any address change after application therefore forces a reissue. Zone 3 adds 2,300 permits. At the July rate, about 360 Zone 3 permits would be reissued.

**GREEN:**

> **Recommendation 2 — The Parking Permits team should issue permits from the verified address record before the Zone 3 rollout (14 September 2026)**
>
> **Owner:** Parking Permits Manager
>
> - Start issuing new permits from the verified address record alongside the application form.
> - Stop issuing from the application form before the Zone 3 rollout.
>
> **Why.** In the July zone, 96 of 610 permits (16%) were reissued because the address changed after issue. Permits are issued from the application form, which is filed before the address is verified. Any address change after application therefore forces a reissue. Zone 3 adds 2,300 permits. At the July rate, about 360 Zone 3 permits would be reissued.

**Expected finding:** `(No finding — the "Start …" and "Stop …" bullets spell out Recommendation 2, so they are labeled Level 4 with it, not Level 6 actions, and the action tests for output and status do not apply. Both inherit the owner (Parking Permits Manager) and the deadline (14 September 2026) from the heading and the Owner label, so there is no ownership gap. The evidence sits below the recommendation, but the chain is judged by what supports what, not by position: observation (96 of 610 reissued), insight (issuing from the application form before the address is verified), implication (about 360 reissues in Zone 3), recommendation.)`

---

## Level 5 — Decision Required

### 5.1 — Decision disguised as a recommendation

**RED:**

> **Scope:** complete document.
>
> **Decision Required:** The Estates Director must decide whether to adopt the shared building access standard.

**GREEN:**

> **Scope:** complete document.
>
> **Observation:** [needs: supporting observation]
>
> **Insight:** [needs: insight]
>
> **Implication:** [needs: implication]
>
> **Recommendation:** The Estates Director should adopt the shared building access standard by [needs: date].

**Expected finding:** `[L5 Decision vs. recommendation] "Whether to adopt the shared building access standard" is not a genuine fork — the document states no alternative to adopting the standard. Reserve "Decision Required" for genuine choices between two or more real alternatives. When there is only one recommended path, label it a recommendation; if the Estates Director needs a genuine decision, the author must state the alternative to adopting. [Chain integrity] The scope is the complete document and the recommendation has no supporting observation, insight, or implication, so it is an assertion; the skill marks each missing level [needs: …] rather than writing it. The source gives no date for the recommendation, so the rewrite carries [needs: date].`

---

### 5.2 — Decision with no decision-maker, question, options, or deadline

**RED:**

> Leadership needs to make a decision about the vendor contract.

**GREEN:**

> [needs: decision-maker role within leadership] must decide by [needs: date] whether to [needs: option A for the vendor contract] or [needs: option B]. Without a decision by that date, [needs: consequence of delay].

**Expected finding:** `[L5 Decision quality] "Leadership needs to make a decision" does not name the decision-maker, the question being decided, the options, or the consequence of delay. A decision required must name: the role, the specific question (option A vs. option B), and the deadline with its consequence. The source supplies none of them, so each is marked [needs: …].`

---

### 5.3 — Conditional fork and an approval are decisions

**RED:**

> If the primary vendor fails the 30 April factory acceptance test, Procurement should issue a cure notice within five working days. Should the Board decline the secondary supplier budget, the fallback is to install meters with manual reading only.
>
> The Steering Committee must approve the FY27 licence budget by 12 June 2026.

**GREEN:**

> If the primary vendor fails the 30 April factory acceptance test, Procurement should issue a cure notice within five working days.
>
> **Decisions required**
>
> | Decision-maker | Question | Options | Deadline | Consequence of delay |
> |---|---|---|---|---|
> | Board | Whether to fund the secondary supplier budget | (a) fund the secondary supplier; (b) install meters with manual reading only | [needs: deadline] | [needs: consequence of delay] |
> | Steering Committee | Whether to approve the FY27 licence budget | Approve / reject | 12 June 2026 | [needs: consequence of delay] |

**Expected finding:** `[L5 Decision buried] "Should the Board decline the secondary supplier budget, the fallback is …" turns on the Board's yes or no, so it is a Level 5 decision even though it matches no decision pattern; surface it in the Decisions table. "The Steering Committee must approve the FY27 licence budget" is an approval by a governing body, so it is Level 5, not a recommendation: approve or reject is its fork, so the rule that a "whether to X" question needs a stated alternative does not apply. Neither states a consequence of delay and the Board item states no deadline, so those cells read [needs: …]. The Procurement recommendation keeps its condition "If the primary vendor fails the 30 April factory acceptance test".`

---

## Level 6 — Action

### 6.1 — Action without a named owner

**RED:**

> All stakeholders to sign off the warehouse scanner allowlist before the first site handover.

**GREEN:**

> [needs: owner] to sign off the warehouse scanner allowlist before the first site handover ([needs: date]). Output: [needs: output]. Status: [needs: status].

**Expected finding:** `[L6 Action quality] "All stakeholders" is not a single owner — it has no accountability. An action must have one named person, specific named role, or named team, a specific deadline, a named output, and a stated status. Replace "all stakeholders" with the accountable owner; the source names none, so write [needs: owner]. The source names no output either, so the rewrite writes [needs: output] rather than deriving one from the task. "Before the first site handover" is not a date: the document gives no handover date, so the rewrite marks [needs: date]. No status is stated, so [needs: status].`

---

### 6.2 — Action with a vague deadline

**RED:**

> Clinical Systems to complete system configuration before go-live.

**GREEN:**

> Clinical Systems to complete system configuration by [needs: date before go-live]. Output: [needs: output]. Status: [needs: status].

**Expected finding:** `[L6 Action quality] "Before go-live" is not a specific deadline — the document gives no go-live date, so it cannot be tracked or enforced. Actions require a specific date, a named output, and a stated status. The source gives none of them, so each is marked [needs: date before go-live], [needs: output], [needs: status], keeping the source's "before go-live" limit.`

---

### 6.3 — Action table read as records

**RED:**

> **Action log**
>
> | # | Action | Owner | Due | Status |
> |---|--------|-------|-----|--------|
> | A1 | Publish the lab printer allowlist | R. Okafor | 20 May 2026 | Complete |
> | A2 | Confirm the handheld scanner firmware baseline | Library Systems | 29 May 2026 | In Progress |
> | A3 | Issue the revised staff joiner form | HR Operations | 5 June 2026 | Not started |

**GREEN:**

> **Action log**
>
> | # | Action | Owner | Due | Output | Status |
> |---|--------|-------|-----|--------|--------|
> | A1 | Publish the lab printer allowlist | R. Okafor | 20 May 2026 | [needs: output] | Complete |
> | A2 | Confirm the handheld scanner firmware baseline | Library Systems | 29 May 2026 | [needs: output] | In Progress |
> | A3 | Issue the revised staff joiner form | HR Operations | 5 June 2026 | [needs: output] | Not started |

**Expected finding:** `[L6 Action quality — table] Each row is one action, and its Owner, Due, and Status cells are its attributes, so no row is an ownership gap. The table has no Output column: report that once for the table, not once per row. The rewrite adds the Output column and fills each cell with [needs: output], because the source names no output for any action; Gaps lists [needs: output] once. "Not started" is a stated status and is not a failure. The log gives no as-of date, so the overdue check is skipped and the review says so.`

---

### 6.4 — Overdue action and a sequence conflict

**RED:**

> **Action log (as at 14 April 2026)**
>
> - Network team to close legacy VPN accounts by 31 March 2026. Output: closure report. Status: Open.
> - Identity team to configure the renewal workflow chosen under decision D1 by 15 May 2026. Output: configured renewal workflow. Status: Open.
>
> **Decision D1:** The CIO must decide by 30 May 2026 whether contractor renewals are approved by sponsors or by central IAM. Without a decision, renewals continue under the current manual process.

**GREEN:**

> **Action log (as at 14 April 2026)**
>
> - Network team to close legacy VPN accounts by [needs: revised date; 31 March 2026 has passed]. Output: closure report. Status: Open.
> - Identity team to configure the renewal workflow chosen under decision D1 by [needs: date after D1's 30 May 2026 deadline]. Output: configured renewal workflow. Status: Open.
>
> **Decision D1:** The CIO must decide by 30 May 2026 whether contractor renewals are approved by sponsors or by central IAM. Without a decision, renewals continue under the current manual process.

**Expected finding:** `[Date conflict] As at 14 April 2026, "close legacy VPN accounts" is Open and past its 31 March 2026 deadline: overdue. "Configure the renewal workflow chosen under decision D1" is due 15 May 2026, before D1's 30 May 2026 deadline: sequence conflict. The source gives no revised dates, so each is marked [needs: …].`

---

### 6.5 — Deadlines that do not resolve to a date

**RED:**

> The depot modernisation programme runs from January 2026 to December 2027.
>
> - Network Services to complete the network cutover by Gate 3 (12 June 2026). Output: signed cutover checklist. Status: Open.
> - Fleet Services to tag the pilot vehicles by 90 days before handover. Output: 200 tagged vehicles. Status: Open.
> - Finance to confirm the FY27 licence budget by 14 March. Output: confirmation memo. Status: In Progress.

**GREEN:**

> The depot modernisation programme runs from January 2026 to December 2027.
>
> - Network Services to complete the network cutover by Gate 3 (12 June 2026). Output: signed cutover checklist. Status: Open.
> - Fleet Services to tag the pilot vehicles by 90 days before handover ([needs: calendar date for 90 days before handover]). Output: 200 tagged vehicles. Status: Open.
> - Finance to confirm the FY27 licence budget by 14 March [needs: year]. Output: confirmation memo. Status: In Progress.

**Expected finding:** `[L6 Action quality — deadline] "By 90 days before handover" does not resolve to a calendar date: the document never gives the handover date. "By 14 March" has no year, and the programme spans two Marches (2026, 2027). Mark [needs: calendar date for 90 days before handover] and [needs: year]. "By Gate 3 (12 June 2026)" passes because the document gives the milestone's date.`

---

## Chain Integrity

### 7.1 — Recommendation with no supporting observation

**RED:**

> **Scope:** complete document.
>
> **Recommendation:** The Finance team should adopt zero-based budgeting by Q4.

**GREEN:**

> **Scope:** complete document.
>
> **Observation:** [needs: supporting observation]
>
> **Insight:** [needs: insight]
>
> **Implication:** [needs: implication]
>
> **Recommendation:** The Finance team should adopt zero-based budgeting by Q4.

**Expected finding:** `[Chain integrity] The recommendation for zero-based budgeting has no supporting observation, insight, or implication. A recommendation without an evidence chain is an assertion. Add the supporting levels or remove the recommendation. The skill does not write the missing levels; it marks each one [needs: …].`

---

### 7.2 — Observation with no recommendation (orphan)

**RED:**

> **Scope:** complete document.
>
> Three of five wards have not completed their access-role review. The gap means Clinical Systems cannot configure access for nursing staff on those three wards.

**GREEN:**

> **Scope:** complete document.
>
> **Observation:** Three of five wards have not completed their access-role review.
>
> **Insight:** [needs: insight]
>
> **Implication:** The gap means Clinical Systems cannot configure access for nursing staff on those three wards.
>
> **Recommendation:** [needs: owner] should [needs: action that closes the access-role review gap] by [needs: date].

**Expected finding:** `[Chain integrity — orphan observation] This observation (and its stated implication) has no corresponding recommendation. Add a recommendation that addresses the access-role review gap; the source names no owner, action, or date, so each is marked [needs: …]. The source also states no insight linking the observation to its implication, so the Insight is marked [needs: insight] rather than written.`

---

### 7.3 — Quoted and attributed wording is observed, not rewritten

**RED:**

> **Scope:** complete document.
>
> **Observation:** Clause 12.4 of the site security contract states that CCTV footage "must be retained for no less than 31 days."
>
> **Observation:** The current recorders overwrite footage after 14 days.
>
> **Observation:** The recorder console shows retention set to 14 days; the recorders have storage for 45 days of footage.
>
> **Observation:** One warehouse manager called the recorder settings "an accident waiting to happen."
>
> **Observation:** The installer's statement of work says the supplier "should consider" encrypting exported footage.
>
> **Insight:** The gap is in the recorder configuration, not in storage: the recorders can hold 45 days of footage but are set to keep 14, against the 31 days the contract requires.
>
> **Implication:** Footage from days 15 to 31 that Clause 12.4 requires is not kept, so current retention breaches the clause.
>
> **Recommendation:** Site Security should change the recorder retention setting to 31 days by 30 June 2026.

**GREEN:**

> **Scope:** complete document.
>
> **Observation:** Clause 12.4 of the site security contract states that CCTV footage "must be retained for no less than 31 days."
>
> **Observation:** The current recorders overwrite footage after 14 days.
>
> **Observation:** The recorder console shows retention set to 14 days; the recorders have storage for 45 days of footage.
>
> **Observation:** One warehouse manager called the recorder settings "an accident waiting to happen."
>
> **Observation:** The installer's statement of work says the supplier "should consider" encrypting exported footage.
>
> **Insight:** The gap is in the recorder configuration, not in storage: the recorders can hold 45 days of footage but are set to keep 14, against the 31 days the contract requires.
>
> **Implication:** Footage from days 15 to 31 that Clause 12.4 requires is not kept, so current retention breaches the clause.
>
> **Recommendation:** Site Security should change the recorder retention setting to 31 days by 30 June 2026.
>
> **Insight:** [needs: insight]
>
> **Implication:** [needs: implication]
>
> **Recommendation:** [needs: owner] should [needs: action on encrypting exported footage] by [needs: date].

**Expected finding:** `[Chain integrity — orphan observation] The statement-of-work observation (the supplier "should consider" encrypting exported footage) has no recommendation; add one, marking what the source lacks [needs: …]. The source gives no insight or implication about encryption, so those levels are [needs: insight] and [needs: implication]. The quoted words are not flagged: "must be retained" is the contract's wording, "should consider" is the statement of work's, and "an accident waiting to happen" is the warehouse manager's. Each is an observation of its source, so the modal, hedge, and neutrality tests do not apply and the quotes are not rewritten.`

---

### 7.4 — Excerpt of unknown completeness: no orphan reported

**RED:**

> **4.2 Repair requests**
>
> In April 2026, 212 of 1,180 housing repair requests arrived as email attachments and were re-entered by hand. Re-entered requests took a median of three working days longer to close. Section 5 covers contractor repairs.

**GREEN:**

> **4.2 Repair requests**
>
> In April 2026, 212 of 1,180 housing repair requests arrived as email attachments and were re-entered by hand. Re-entered requests took a median of three working days longer to close. Section 5 covers contractor repairs.

**Expected finding:** `(No finding — the input is Section 4.2 and points to Section 5, so it is not known to be the full document. Report "Chain assessed within the supplied text only" and report no orphan observation, even though no recommendation appears in the excerpt.)`

---

## Verification Log

**Verified 2026-10-22.** Result: **27/27 passed.** Graded by an Opus agent reading `SKILL.md` and `TESTS.md`, with no edit to either file afterwards.

Produced against `TESTS.md` body sha256 `807817fe83c655fb` and `SKILL.md` sha256 `efd17fc252185d67`. The body hash covers everything above this heading, so it survives this table being written. Recompute both before trusting the rows: any later edit invalidates them, and a log that certifies rather than records hides the defects it exists to surface.

| Test                                                                     | RED flags | GREEN clean | Pass |
|--------------------------------------------------------------------------|-----------|-------------|------|
| 1.1 — Observation is an interpretation, not a fact                       | ✓         | ✓           | PASS |
| 1.2 — Evaluative language in an observation                              | ✓         | ✓           | PASS |
| 1.3 — Percentage with no base or period                                  | ✓         | ✓           | PASS |
| 1.4 — Methodology, a met target, and an assumption stay unflagged        | ✓         | ✓           | PASS |
| 2.1 — Insight restates the observation                                   | ✓         | ✓           | PASS |
| 2.2 — Insight is a generic principle, not client-specific                | ✓         | ✓           | PASS |
| 3.1 — Vague implication (no specific consequence)                        | ✓         | ✓           | PASS |
| 3.2 — Implication confused with insight (Level 2 vs. Level 3)            | ✓         | ✓           | PASS |
| 3.3 — Conditional implication stays unflagged                            | ✓         | ✓           | PASS |
| 4.1 — Hedged recommendation ("consider" / "explore")                     | ✓         | ✓           | PASS |
| 4.2 — Recommendation doesn't address the implication                     | ✓         | ✓           | PASS |
| 4.3 — Wrong modal verb                                                   | ✓         | ✓           | PASS |
| 4.4 — Missing owner and timing are marked, not invented                  | ✓         | ✓           | PASS |
| 4.5 — Study verb in place of a commitment                                | ✓         | ✓           | PASS |
| 4.6 — Owner and deadline in the heading, evidence below: stays unflagged | ✓         | ✓           | PASS |
| 5.1 — Decision disguised as a recommendation                             | ✓         | ✓           | PASS |
| 5.2 — Decision with no decision-maker, question, options, or deadline    | ✓         | ✓           | PASS |
| 5.3 — Conditional fork and an approval are decisions                     | ✓         | ✓           | PASS |
| 6.1 — Action without a named owner                                       | ✓         | ✓           | PASS |
| 6.2 — Action with a vague deadline                                       | ✓         | ✓           | PASS |
| 6.3 — Action table read as records                                       | ✓         | ✓           | PASS |
| 6.4 — Overdue action and a sequence conflict                             | ✓         | ✓           | PASS |
| 6.5 — Deadlines that do not resolve to a date                            | ✓         | ✓           | PASS |
| 7.1 — Recommendation with no supporting observation                      | ✓         | ✓           | PASS |
| 7.2 — Observation with no recommendation (orphan)                        | ✓         | ✓           | PASS |
| 7.3 — Quoted and attributed wording is observed, not rewritten           | ✓         | ✓           | PASS |
| 7.4 — Excerpt of unknown completeness: no orphan reported                | ✓         | ✓           | PASS |

27 tests: 4 negative (must stay unflagged), 23 RED/GREEN pairs; 0 discrepancies; 0 SKILL.md example defects.

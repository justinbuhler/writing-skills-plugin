# Writing Workflow Skill — Red/Green Test Suite

Orchestrator tests verify routing decisions and sequencing, not language quality.
Each sub-skill's language checks are covered in its own TESTS.md.

Each test has:

- **Scenario:** the input document type or situation
- **RED:** incorrect routing or sequencing decision
- **GREEN:** correct decision
- **Expected finding:** what the skill should do

---

## Step 4 Language Fork — plain-language vs. ste100-writer

### L1 — Technical procedure → ste100-writer

**Scenario:** User submits a draft maintenance procedure for replacing a hydraulic filter on industrial equipment.

**RED (wrong routing):**

> Apply `plain-language` at Step 4 — the document is about a technical topic.

**GREEN (correct routing):**

> Apply `ste100-writer` at Step 4 — the document is a technical procedure, and document type decides the fork.

**Expected finding:** `[Step 4 fork] Document type is a maintenance procedure → use ste100-writer. The fork criterion is not whether the topic is technical but whether the document is a procedure, manual, work instruction, or safety notice.`

---

### L2 — Executive memo → plain-language

**Scenario:** User submits a draft strategy memo for a leadership team recommending a cloud migration.

**RED (wrong routing):**

> Apply `ste100-writer` at Step 4 — the memo discusses technical infrastructure.

**GREEN (correct routing):**

> Apply `plain-language` at Step 4 — the document is a stakeholder communication, not a technical procedure.

**Expected finding:** `[Step 4 fork] Document type is a strategy memo to a leadership audience → use plain-language. ste100-writer is for procedures and manuals, not reports or communications that discuss technical subjects.`

---

### L3 — Unclear document type → default to plain-language

**Scenario:** User submits a "technical brief on cloud architecture options" — neither a procedure nor a standard report.

**RED (wrong routing):**

> Ask the user to clarify before proceeding, or apply both skills.

**GREEN (correct routing):**

> Default to `plain-language` at Step 4 without asking: a technical brief fits neither Step 4 list, so the default applies. Note to the user: "I've applied plain-language. Use ste100-writer instead if this document will serve as a procedure, manual, work instruction, or safety notice, or must be read accurately by non-native English speakers or processed by machine translation."

**Expected finding:** `[Step 4 fork — default] A document type that fits neither Step 4 list takes the Step 4 default, plain-language, without a question to the user. The one question allowed before Step 1 is not for this case. Do not apply both skills.`

---

## Step 3 — Skip recommendations-and-actions when there are none

### R1 — Analytical briefing with no recommendations → skip Step 3

**Scenario:** User submits a market analysis briefing that presents data and trends (observations, which are findings) but contains no recommendations, decisions required, or action items.

**RED (wrong routing):**

> Apply `recommendations-and-actions` at Step 3 to audit the document.

**GREEN (correct routing):**

> Skip Step 3. Note: "This document contains no recommendations or action items — skipping recommendations-and-actions and proceeding to Step 4."

**Expected finding:** `[Step 3 skip] The document is a purely analytical briefing. Step 3 applies only when the document contains recommendations, decisions required, or action items; findings alone do not trigger it. Applying it here would report its observations as orphans with no recommendation.`

---

### R2 — Document with hidden action items → do not skip Step 3

**Scenario:** User submits what they describe as "a summary report" — but the document contains bullet points such as "Finance to confirm budget by Q3" and "Leadership should review the options."

**RED (wrong routing):**

> Skip Step 3 because the user called it a summary report.

**GREEN (correct routing):**

> Apply Step 3. The document contains action items ("Finance to confirm budget") and a recommendation ("Leadership should review the options") — both require the recommendations-and-actions quality check regardless of how the user labeled the document.

**Expected finding:** `[Step 3 detection] Label the document type by its content, not the user's description. Any document containing recommendations, decisions required, or action items must go through Step 3, even if informally worded.`

---

## Steps 4.5 and 4.6 — humanizer and no-ai-slop

### H1 — Text reaching Step 4.5 shows humanizer patterns → apply humanizer (Step 4.5)

**Scenario:** User says: "I had ChatGPT write a first draft of this strategy memo. Can you clean it up?" After the Step 4 language review, the text still shows not-X-but-Y contrasts and one-line closers.

**RED (wrong routing):**

> Skip Step 4.5 (humanizer) and go straight to document-qa.

**GREEN (correct routing):**

> Apply `humanizer` at Step 4.5 after the language review. The text reaching Step 4.5 still shows patterns humanizer catalogues (not-X-but-Y contrasts, one-line closers), and that text decides the step; who wrote the draft plays no part. Then run `plain-language` again on the passages humanizer changed.

**Expected finding:** `[Step 4.5 trigger] The trigger is the text reaching Step 4.5, not the draft's authorship. That text still shows humanizer's patterns, so apply humanizer, then run the Step 4 language skill again on the passages it changed.`

---

### H2 — Human-authored draft with flat voice → apply no-ai-slop (Step 4.6), skip humanizer

**Scenario:** User submits a draft they wrote themselves. The writing is technically correct but reads as generic consulting prose — no personality, everything sounds like it could have been written by anyone. After Step 4 it shows none of the patterns humanizer catalogues.

**RED (wrong routing):**

> Apply `humanizer` at Step 4.5 because the writing sounds AI-like.

**GREEN (correct routing):**

> Skip Step 4.5 (humanizer — the text shows none of its patterns). Apply `no-ai-slop` at Step 4.6 to sharpen the voice and remove editorial slop.

**Expected finding:** `[Step 4.5 vs. 4.6] Humanizer applies when the text reaching Step 4.5 shows the patterns it catalogues; no-ai-slop targets voice flatness in any draft. A draft that sounds generic but shows none of humanizer's patterns gets no-ai-slop, not humanizer. The two steps can both apply when a draft shows AI patterns AND is still flat after humanizer.`

---

### H3 — AI draft that is still flat after humanizer → apply both 4.5 and 4.6

**Scenario:** An AI-generated executive memo has been run through humanizer (Step 4.5). The specific AI patterns are gone, but the writing still feels smooth and voiceless.

**RED (wrong routing):**

> Stop after Step 4.5 and proceed to document-qa.

**GREEN (correct routing):**

> Apply `no-ai-slop` at Step 4.6 after humanizer. The draft has cleared the AI-pattern check but still lacks the writer's voice — no-ai-slop's sharper editorial pass addresses that.

**Expected finding:** `[Steps 4.5 + 4.6 combined] Both steps apply when the text reaching 4.5 shows humanizer's patterns (→ humanizer) and still reads as polished but voiceless after humanizer (→ no-ai-slop). Run 4.5 first, then 4.6 on the output.`

---

## Step sequencing

### S1 — Correct full sequence (all steps apply)

**Scenario:** User submits a strategy brief that is AI-drafted, shows humanizer's patterns after Step 4, contains recommendations, still reads flat after the AI-pattern pass, and will go to a senior leadership audience.

**RED (wrong sequence):**

> Run plain-language → pyramid-editor → document-qa.

**GREEN (correct sequence):**

```
1. scqa-framework               — opening and governing thought
2. pyramid-editor               — body structure and logical flow
3. recommendations-and-actions  — recommendations, decisions, actions
4. plain-language               — stakeholder communication (not a procedure)
4.5 humanizer                   — the text reaching 4.5 shows humanizer's patterns
4.6 no-ai-slop                  — voice still flat after humanizer
5. document-qa                  — final pre-delivery gate
```

**Expected finding:** `[Sequencing] All seven steps apply here. The governing thought from Step 1 feeds Step 2; the structured draft from Step 2 feeds Step 3; and so on. Each step's output is the next step's input — do not run steps in parallel or skip ahead.`

---

### S1b — Long strategic document → scr-narrative at Step 1

**Scenario:** User submits a brief for a 40-page white paper recommending a full operating model redesign across five workstreams. The narrative logic must carry through every major section.

**RED (wrong routing):**

> Apply `scqa-framework` at Step 1 because it's a strategy document.

**GREEN (correct routing):**

> Apply `scr-narrative` at Step 1. The document is long enough that S→C→R must hold across every section — not just the introduction. The SCR Resolution becomes the governing thought (Level 1) fed into pyramid-editor at Step 2.

**Expected finding:** `[Step 1 fork] Use scr-narrative when the full document needs a narrative spine. Use scqa-framework when only the opening needs it. Default to scqa-framework when unsure.`

---

### S2 — Pyramid before SCQA (wrong order)

**Scenario:** User asks to "structure this draft" — they want the body organized and the opening written.

**RED (wrong sequence):**

> Run pyramid-editor first, then scqa-framework.

**GREEN (correct sequence):**

> Run `scqa-framework` first. The SCQA Answer becomes Level 1 of the pyramid — if pyramid runs first, it anchors to the draft's own governing thought, and the Step 1 Answer written afterwards can contradict the structure already built.

**Expected finding:** `[Step ordering] scqa-framework must precede pyramid-editor. The Answer from Step 1 is the governing thought (Level 1) that the pyramid organizes supporting evidence around. Running pyramid first builds the structure around the draft's own governing thought, which the later Step 1 Answer can contradict.`

---

### S3 — document-qa run before language review

**Scenario:** Mid-way through a `writing-workflow` run on a memo, Step 3 is done. To save time, the model considers running document-qa next and the language review afterwards.

**RED (wrong sequence):**

> Run document-qa (Step 5), then the language review (Step 4).

**GREEN (correct sequence):**

> Run the language review (Step 4) before document-qa. document-qa is the final pre-delivery gate; a language rewrite after it would ship unchecked. A user who wants only a QA pass on a finished draft is routed to `document-qa` alone, outside the workflow.

**Expected finding:** `[Step ordering] Inside the workflow, document-qa is always Step 5 — it is the final pre-delivery gate, so it runs after the language review. A QA-only request is a different route: document-qa alone, per the routing guide.`

---

## Pause behavior

### P1 — Pause after each step for a long, complex document

**Scenario:** User submits a 25-page program review document with multiple sections, competing recommendations, and a senior client audience.

**RED (wrong behavior):**

> Run all five steps without pausing, then deliver the final document.

**GREEN (correct behavior):**

> Pause after each step and show the user the output before continuing. A document this long with complex structure warrants checkpoints — a structural decision made in Step 2 that the user rejects means Steps 3–5 must be redone.

**Expected finding:** `[Pause behavior] Documents over 10 pages or with complex structure require step-by-step checkpoints. Pause after each step and await user confirmation before proceeding.`

---

### P2 — Run straight through for a short memo

**Scenario:** User submits a two-page executive memo for their department head, with its recommendation already stated in the opening, and wants it cleaned up before sending this afternoon.

**RED (wrong behavior):**

> Pause after every step and ask for confirmation before continuing.

**GREEN (correct behavior):**

> Run all applicable steps without pausing and deliver the final document. A memo under 3 pages with a clear answer and a known audience runs straight through.

**Expected finding:** `[Pause behavior] Short memos under 3 pages with a clear answer and known audience run without step-by-step checkpoints. Pausing on a two-pager creates friction without adding value.`

---

### P3 — Mid-length document with no pause trigger → run straight through

**Scenario:** User submits a six-page status report for a known audience, with its single recommendation stated in the opening. They did not ask for checkpoints, and no step makes a significant structural change.

**RED (wrong behavior):**

> Stop and ask whether to pause, because six pages is neither under 3 nor over 10.

**GREEN (correct behavior):**

> Run all applicable steps without pausing. None of the pause triggers applies, and every document that meets none of them runs straight through.

**Expected finding:** `[Pause behavior] Pause only when a trigger applies: over 10 pages (about 5,000 words) or complex structure, checkpoints requested, or a significant structural change to approve. Otherwise run straight through, whatever the length.`

---

## Handoffs between steps

### W1 — A step hands the next step the full document, not a findings list

**Scenario:** A two-page memo with a recommendation and two next steps reaches Step 3.

**RED (wrong handoff):**

> Step 3 returns a list of flagged statements with suggested rewrites, and Step 4 reviews that list.

**GREEN (correct handoff):**

> Step 3 runs `recommendations-and-actions` in its Rewrite job and returns the whole memo as prose, with the recommendation and next steps rewritten in place, then its What changed list. Step 4 receives that memo.

**Expected finding:** `[Handoff] From Step 2 on, each step runs its sub-skill's rewriting job and returns the full document with the changes in place, then What changed. A findings list, a table, or changed sections only is not a handoff; the next step needs the whole document.`

---

### W2 — Answer-first order survives Steps 4A and 5

**Scenario:** After Step 2, a memo opens with an SCQA opening whose Answer is the recommendation, followed by the findings that support it.

**RED (wrong handling):**

> Step 4A moves the opening's Situation to the end as background. Step 5 moves the recommendation below the findings because recommendations should follow findings.

**GREEN (correct handling):**

> Both steps leave the order alone. Step 4A is told the Step 1 opening stays where it is, because its Answer already puts the bottom line up front. Step 5 is told the answer-first order is deliberate and checks sequence within the body only.

**Expected finding:** `[Structure is set by Steps 1 and 2] The Step 1 opening and the answer-first order from Step 2 are deliberate. No later step moves the opening, the governing thought, or the recommendation, and each later sub-skill is told so when loaded.`

---

### W3 — Step 4A keeps named owners and adds no actor

**Scenario:** The memo from Step 3 reads: "Finance will confirm the budget. The Facilities team will book the rooms. The depot lease was signed in 2024." The writer is the council's project office, which does not know who signed the lease.

**RED (wrong handling):**

> Step 4A rewrites it as "We will confirm the budget. We will book the rooms. We signed the depot lease in 2024."

**GREEN (correct handling):**

> Step 4A leaves all three sentences as they are. Finance and the Facilities team are named owners and stay named. The lease sentence keeps its passive: the actor is genuinely unknown, so there is no actor to name.

**Expected finding:** `[Step 4A handoff] Owners named in the document stay named and are not replaced with "we". Rewriting "was signed" as "We signed" asserts an actor the input never names, which the facts rule forbids; plain-language allows the passive when the actor is genuinely unknown.`

---

### W4 — Step 5 applies document-qa's number rules as written

**Scenario:** At Step 5, the summary says "approximately 1,200 laptops need replacement". The body says "the 1,190 laptops in Table 2", and Table 2's rows (500, 410, 280) sum to 1,190.

**RED (wrong handling):**

> Flag "approximately 1,200" and "1,190" as an inconsistent number, because every number must match across all occurrences.

**GREEN (correct handling):**

> No finding. "Approximately 1,200" is an estimate, and 1,190 is within 2% of it, so document-qa treats the two as consistent.

**Expected finding:** `[Step 5] Run document-qa's QA areas as written, not a summary of them. Its estimate rule treats a breakdown within 2% of the larger figure as consistent: 1,200 − 1,190 = 10, under 2% of 1,200 (24). No inconsistency.`

---

### W5 — A supplied draft keeps its author's content

**Scenario:** User supplies a finished two-page memo and asks for it to be cleaned up. It opens with a Background section, then Findings, a Recommendation, and Next steps.

**RED (wrong handling):**

> Step 1A writes a new SCQA opening from the topic and audience alone, ignoring the memo's Background and content, and Step 2 outputs only a pyramid outline.

**GREEN (correct handling):**

> Step 1A builds the Situation, Complication, Question, and Answer from the memo's own Background and content, and replaces only the opening. Background facts the opening does not use stay in the memo for Step 2 to place. Step 2 returns the full memo in pyramid order, keeping the author's content.

**Expected finding:** `[Input] With a supplied draft, every step works on that draft and keeps the author's content unless a sub-skill rule requires the change. Step 1A builds the opening from the draft's own opening and content. Only a brief-only input has Step 2 write the body prose.`

---

### W6 — Step 1B on a draft replaces only the opening

**Scenario:** User supplies a long board paper on consolidating a water utility's three billing systems and asks for the full workflow. Its opening states a Situation and a Complication, but its Resolution sentence proposes a staff survey that does not answer the Complication.

**RED (wrong handling):**

> Step 1B runs scr-narrative's Critique job and returns its findings and the corrected SCR block. Step 2 receives that block alone and builds a new body from it, dropping the paper's sections.

**GREEN (correct handling):**

> Step 1B runs the Critique job. Because the Resolution fails, the corrected SCR replaces only the paper's opening, written as prose. Step 2 receives the full paper with that opening in place, and the corrected Resolution is Level 1 of the pyramid. Had the Critique found SCR passes, the opening would stay as written and its quoted Resolution would be Level 1.

**Expected finding:** `[Step 1 exception] Step 1 sets the opening and the governing thought, not the whole document, and returns its sub-skill's output. With a draft it also returns the full draft with only the opening replaced, and Step 2 receives that draft; a passing SCR leaves the opening unchanged.`

---

## Procedure route

### L4 — AI-drafted procedure → Steps 4B and 5 only

**Scenario:** User says an AI tool drafted a nine-step procedure for replacing a pump seal, with a WARNING and a tools line, and asks for the writing workflow before issue.

**RED (wrong routing):**

> Run Steps 1–3, 4B, and 4.5: write an SCQA opening above the WARNING, group the nine steps into pillars, flag each step for a missing owner and deadline, then humanize the STE text.

**GREEN (correct routing):**

> Take the procedure route: Step 4B (`ste100-writer`, given the command to show the changes so it returns its change table), then Step 5 (`document-qa`). Skip Steps 1–3, because a procedure has no argument and its numbered steps are instructions, not action items. Skip 4.5 and 4.6, which do not run on STE text.

**Expected finding:** `[Procedure route] A technical procedure runs Step 4B and Step 5 only. Steps 1–3 build an argument and do not apply; 4.5 and 4.6 do not run on STE text, whoever drafted it.`

---

### L5 — Memo with a procedure appendix → both language skills, by section

**Scenario:** User submits a memo recommending new handheld scanners, with an appendix titled "Enrol a replacement scanner" containing four numbered instructions.

**RED (wrong routing):**

> Apply `plain-language` to the whole document at Step 4, including the appendix.

**GREEN (correct routing):**

> Apply `ste100-writer` (4B) to the appendix and `plain-language` (4A) to the memo body. The sections differ in type.

**Expected finding:** `[Step 4 fork — mixed] Apply one language skill per document, except when sections differ in type: 4B for procedure sections, 4A for the rest.`

---

### L6 — Mixed document with AI patterns → 4.5 on the memo body only

**Scenario:** A university IT team's memo recommends moving staff laptops to a new device-management service. It has an appendix, "Enrol a laptop", with five numbered instructions. Step 4 has applied `plain-language` to the memo body and `ste100-writer` to the appendix. The memo body still shows not-X-but-Y contrasts and one-line closers.

**RED (wrong routing):**

> Run `humanizer` on the whole document, appendix included, then run `ste100-writer` again on the appendix passages it changed.

**GREEN (correct routing):**

> Run `humanizer` on the memo body only and pass the appendix through unchanged. Then run `plain-language` again on the body passages humanizer changed.

**Expected finding:** `[STE text is final at Step 4] Steps 4.5 and 4.6 never run on text Step 4B wrote. In a mixed document they run on the 4A sections only, so the Step 4 skill to run again afterwards is always plain-language.`

---

## Gap markers across steps

### G1 — Brief lacks an owner and a figure → gaps carried to Step 5's Gaps list

**Scenario:** User supplies a brief for a memo: "Recommend moving the parts warehouse inventory count from annual to quarterly. Write-offs from miscounts have grown. Audience: operations director." The brief names no owner for the change, gives no figure for the write-off growth, and does not say why quarterly counts would reduce write-offs or what happens if counts stay annual.

**RED (wrong handling):**

> Step 1 opens with "Miscount write-offs rose 18% last year." Step 3 assigns the recommendation to "the Warehouse Manager, by the end of Q2." Step 5 finds nothing to report and returns a clean document.

**GREEN (correct handling):**

> Step 1 writes "Write-offs from miscounts have grown by [needs: figure for write-off growth]." Step 3 writes "Owner: [needs: owner]" and "Due: [needs: date]". Every other step that needs a detail the brief lacks, such as a missing link between annual counting and the write-offs, also writes a [needs: …] marker instead of a value. Steps 4 through 4.6 pass every marker through unchanged. Step 5 runs document-qa's Fix job, adds [needs: source for "Write-offs from miscounts have grown"], and lists every open marker under **Gaps**, which is the author's punch list.

**Expected finding:** `[Use only the facts you were given] The brief supplies no owner, no deadline, no write-off figure, and no link between annual counting and the write-offs. No step may fill these in: each writes a [needs: …] marker instead, including [needs: figure for write-off growth], [needs: owner] and [needs: date], and every later step carries each marker forward untouched. Step 5 adds [needs: source for "Write-offs from miscounts have grown"] and lists every open marker under Gaps, as document-qa's Fix job directs, for the author to supply rather than resolving it. The RED fails because it invents a figure, an owner, and a deadline and reports no gaps.`

---

## Verification Log

**Verified 2026-10-22.** Result: **25/25 passed.** Graded by an Opus agent reading `SKILL.md`, `routing-guide.md`, and `TESTS.md`, plus the sub-skill `SKILL.md` files the tests depend on (`document-qa`, `recommendations-and-actions`, `scqa-framework`, `pyramid-editor`, `scr-narrative`, `plain-language`, `no-ai-slop`, the job, output-mode, and pattern-list sections of `humanizer`, and the jobs and procedure sections of `ste100-writer`), with no edit to either file afterwards. Checked after the 2026-10-22 edits to Step 4.6's Deliver line, W5, and G1: the Step 4.6 What changed lists match `no-ai-slop`'s Edit output, G1's `[needs: date]` matches `recommendations-and-actions` step 5, and W4's figures (500 + 410 + 280 = 1,190; 1,200 − 1,190 = 10, under 24) were computed by script.

Produced against `TESTS.md` body sha256 `bc0a9ab324c42164` and `SKILL.md` sha256 `55f1785d6cb59941`. The body hash covers everything above this heading, so it survives this table being written. Recompute both before trusting the rows: any later edit invalidates them, and a log that certifies rather than records hides the defects it exists to surface.

| Test                                                                                    | RED flags | GREEN clean | Pass |
|-----------------------------------------------------------------------------------------|-----------|-------------|------|
| L1 — Technical procedure → ste100-writer                                                | ✓         | ✓           | PASS |
| L2 — Executive memo → plain-language                                                    | ✓         | ✓           | PASS |
| L3 — Unclear document type → default to plain-language                                  | ✓         | ✓           | PASS |
| R1 — Analytical briefing with no recommendations → skip Step 3                          | ✓         | ✓           | PASS |
| R2 — Document with hidden action items → do not skip Step 3                             | ✓         | ✓           | PASS |
| H1 — Text reaching Step 4.5 shows humanizer patterns → apply humanizer (Step 4.5)       | ✓         | ✓           | PASS |
| H2 — Human-authored draft with flat voice → apply no-ai-slop (Step 4.6), skip humanizer | ✓         | ✓           | PASS |
| H3 — AI draft that is still flat after humanizer → apply both 4.5 and 4.6               | ✓         | ✓           | PASS |
| S1 — Correct full sequence (all steps apply)                                            | ✓         | ✓           | PASS |
| S1b — Long strategic document → scr-narrative at Step 1                                 | ✓         | ✓           | PASS |
| S2 — Pyramid before SCQA (wrong order)                                                  | ✓         | ✓           | PASS |
| S3 — document-qa run before language review                                             | ✓         | ✓           | PASS |
| P1 — Pause after each step for a long, complex document                                 | ✓         | ✓           | PASS |
| P2 — Run straight through for a short memo                                              | ✓         | ✓           | PASS |
| P3 — Mid-length document with no pause trigger → run straight through                   | ✓         | ✓           | PASS |
| W1 — A step hands the next step the full document, not a findings list                  | ✓         | ✓           | PASS |
| W2 — Answer-first order survives Steps 4A and 5                                         | ✓         | ✓           | PASS |
| W3 — Step 4A keeps named owners and adds no actor                                       | ✓         | ✓           | PASS |
| W4 — Step 5 applies document-qa's number rules as written                               | ✓         | ✓           | PASS |
| W5 — A supplied draft keeps its author's content                                        | ✓         | ✓           | PASS |
| W6 — Step 1B on a draft replaces only the opening                                       | ✓         | ✓           | PASS |
| L4 — AI-drafted procedure → Steps 4B and 5 only                                         | ✓         | ✓           | PASS |
| L5 — Memo with a procedure appendix → both language skills, by section                  | ✓         | ✓           | PASS |
| L6 — Mixed document with AI patterns → 4.5 on the memo body only                        | ✓         | ✓           | PASS |
| G1 — Brief lacks an owner and a figure → gaps carried to Step 5's Gaps list             | ✓         | ✓           | PASS |

25 tests: 25 PASS, 0 PASS with discrepancy, 0 FAIL.

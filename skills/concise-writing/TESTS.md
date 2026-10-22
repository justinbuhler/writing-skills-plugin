# Concise Writing Skill: Red/Green Test Suite

Each test has:

- **RED:** text the skill should act on
- **GREEN:** the corrected text, which should pass
- **Expected finding:** what the skill should report for the RED

Tests 1 to 9 cover the taxonomy categories in `SKILL.md`; bureauspeak has two cases, one where the text names the actor and one where it does not. Tests 10 to 12 check the contract this skill shares with the other writing skills: review mode changes nothing, gaps become `[needs: …]` markers, and quoted text stays verbatim. Tests 13 and 14 check an actor named elsewhere in the input and a rule restated across sections. Tests N1 to N6 must stay unflagged or be flagged without a cut; their GREEN is the RED unchanged. 20 tests in all.

No RED reuses a worked example from `SKILL.md` or `references/taxonomy.md`. Watch-list trigger phrases appear inside new sentences, because a test has to contain the pattern it tests. Checked by longest shared word-run over RED text, Context lines excluded, against both files: the longest is 4 words, and every 4-word run is a watch-list phrase ("in a position to", "it has been decided", "in the event that", "for the purpose of").

GREEN texts add no fact, name, number, date, or actor that is absent from their RED.

Grading notes. Tests without a request line, and tests whose request is to tighten, run as Rewrite, the default job. For those, the Expected finding lists the fixes the rewrite must apply; the rewrite's own diagnosis may name fewer, under the skill's cap, and a one- or two-sentence input may drop the headers. A GREEN is graded under its RED's context line, which most GREENs leave out. A `[needs: …]` already in a GREEN may or may not be listed again under Gaps; either is clean. Tags such as `[Review]` and `[Never invent specifics]` are test labels, not skill categories.

---

## A. Taxonomy categories

### 1. Pleonasm

**RED:**

> The vendor and the depot team will collaborate together to plan ahead for the cutover and sign off the end result.

**GREEN:**

> The vendor and the depot team will collaborate to plan for the cutover and sign off the result.

**Expected finding:** `[Pleonasm] "collaborate together" → "collaborate"; "plan ahead for" → "plan for"; "end result" → "result"`

---

### 2. Circumlocution

**RED:**

> For the reason that the data freeze moved, IT is not in a position to start bulk account creation until such time as HR confirms the new date.

**GREEN:**

> Because the data freeze moved, IT cannot start bulk account creation until HR confirms the new date.

**Expected finding:** `[Circumlocution] "For the reason that" → "Because"; "is not in a position to" → "cannot"; "until such time as" → "until"`

---

### 3. Sesquipedalianism

**RED:**

> Ward clerks should utilize the shared laptops to facilitate admissions, and IT should be cognizant of faults and endeavor to effectuate repairs within the hour.

**GREEN:**

> Ward clerks should use the shared laptops to help with admissions, and IT should be aware of faults and try to repair them within the hour.

**Expected finding:** `[Sesquipedalianism] "utilize" → "use"; "facilitate" → "help with" (any plain replacement passes); "cognizant of" → "aware of"; "endeavor to effectuate repairs" → "try to repair them" (any plain replacement that says IT should try to repair the faults passes, for example "try to make repairs")`

---

### 4. Legalese

**RED:**

> Context: a sentence in an internal planning document, not a contract.
>
> Pursuant to the provisions of the policy hereinafter referred to as the AUP, any and all students shall, prior to and as a condition of access, accept the said policy, provided that minors shall also obtain parental consent.

**GREEN:**

> Under the AUP, all students must accept it before access and as a condition of access. Minors must also obtain parental consent as a condition of access.

**Expected finding:** `[Legalese] "Pursuant to the provisions of the policy hereinafter referred to as the AUP" → "Under the AUP" ("pursuant to" becomes "under", and the clause stays because it says the rule comes from the AUP); "said" removed; "any and all" → "all" (labelled Legalese or Pleonasm; either label passes); "shall, prior to and as a condition of access, accept" → "must accept it before access and as a condition of access" (any wording that keeps the duty, the timing and the condition passes; "shall" may stay); the "provided that" clause becomes its own sentence and keeps its duty and its link to access`

---

### 5. Bureauspeak, actor named in the text

**RED:**

> A review of the license cap was undertaken by the IT Service Manager, and a decision was made by Finance that the cap will be raised going forward.

**GREEN:**

> The IT Service Manager reviewed the license cap, and Finance decided that the cap will be raised.

**Expected finding:** `[Bureauspeak] nominalizations "A review … was undertaken" → "reviewed" and "a decision was made" → "decided"; actors taken from the text (the IT Service Manager, Finance); filler "going forward" deleted; "the cap will be raised" stays passive because the sentence reports Finance's decision; who raises the cap is not the point`

---

### 6. Bureauspeak, actor absent

**RED:**

> The shared PINs were changed without notice, and it has been decided that the depot roster will be frozen on Friday.

**GREEN:**

> [needs: actor] changed the shared PINs without notice, and [needs: actor] decided that the depot roster will be frozen on Friday.

**Expected finding:** `[Bureauspeak] "were changed" and "it has been decided" hide who acted, the text names no one and does not say the actor is unknown, and here the actor matters (who changed the PINs, who decided), so the rewrite writes [needs: actor] for each, never "we" or another invented actor, and lists both under Gaps; "will be frozen" stays passive because the decision, not who freezes the roster, is the point`

---

### 7. Prolixity

**RED:**

> This section describes the exception process. In short, the exception process is how a department asks for technology outside a position's tier. In other words, when a position needs something its tier does not provide, the department raises an exception. It could potentially be the case that some requests might take up to five days.

**GREEN:**

> When a position needs technology its tier does not provide, the department raises an exception. Some requests might take up to five days.

**Expected finding:** `[Prolixity] the announcing sentence and the restated definition cut to one statement of the idea; the stacked hedges "could potentially be the case that … might" collapsed to one hedge ("might"; "may" also passes)`

---

### 8. Logorrhea / word salad

**RED:**

> Going forward, the holistic harmonization of the various aspects of the onboarding journey will drive meaningful outcomes across multiple dimensions of the student experience for all stakeholders.

**GREEN:**

> [needs: the claim and its evidence]

**Expected finding:** `[Logorrhea / word salad] the sentence has no recoverable claim ("the various aspects", "multiple dimensions" name nothing), so the skill does not invent one: it marks [needs: the claim and its evidence] and tells the user the passage needs content, not editing; "meaningful outcomes" names no property a reader could confirm, so the vague-reason rule does not keep it`

---

### 9. Purple prose

**RED:**

> The truly transformative, breathtakingly magical onboarding journey will gently guide each eager student through a beautifully choreographed symphony of account activation.

**GREEN:**

> The onboarding journey will gently guide each eager student through account activation.

**Expected finding:** `[Purple prose] the intensifiers "truly" and "breathtakingly" and the praise "transformative" and "magical", none of which names a property a reader could check, cut; the second image, "a beautifully choreographed symphony of", cut whole, "choreographed" included, so one image stays (the journey); "gently" and "eager" may stay, one modifier each`

---

## B. Contract shared with the other writing skills

### 10. Review mode changes nothing

**RED:**

> Context: the user asks, "Why does this paragraph feel bloated? Don't change it yet."
>
> In the event that a student has a personal smartphone, the student should install Microsoft Authenticator prior to the first lecture for the purpose of completing MFA.

**GREEN:**

> If a student has a personal smartphone, the student should install Microsoft Authenticator before the first lecture to complete MFA.

**Expected finding:** `[Review] diagnosis and suggested fixes only; the passage is not rewritten in the response: [Circumlocution] "In the event that" → "If"; "prior to" → "before"; "for the purpose of completing" → "to complete"; a finding beyond these three is a discrepancy`

---

### 11. No invented specifics

**RED:**

> Context: the user asks to tighten this sentence.
>
> Each Grade 3 engineer will be issued with one of the very latest, top-of-the-range laptops that money can buy.

**GREEN:**

> Each Grade 3 engineer will be issued with one of the latest top-of-the-range laptops: [needs: model or specification].

**Expected finding:** `[Never invent specifics] "very" and "that money can buy" are filler, but "latest" and "top-of-the-range" are checkable (recency, range tier), so they stay; the sentence promises laptops without saying which, so a [needs: …] for the model or specification follows the kept phrase and is listed under Gaps, instead of an invented model; "will be issued with" stays as written (British register) and stays passive because who issues the laptops is not the point`

---

### 12. Quoted text stays verbatim

**RED:**

> Context: the user asks to tighten this sentence.
>
> As the site safety policy states, "each and every visitor must at all times carry their visitor pass", and in order to comply, reception staff will need to check passes at every entry point.

**GREEN:**

> As the site safety policy states, "each and every visitor must at all times carry their visitor pass", and to comply, reception staff will need to check passes at every entry point.

**Expected finding:** `[Circumlocution] "in order to" → "to"; the quotation stays verbatim even though it contains the listed pleonasm "each and every"`

---

## C. Whole-input cases

### 13. Actor named elsewhere in the input

**RED:**

> IT creates, disables and deletes student accounts. After graduation, all student accounts are deleted.

**GREEN:**

> IT creates, disables and deletes student accounts. After graduation, IT deletes all student accounts.

**Expected finding:** `[Bureauspeak] "are deleted" hides an actor the input names in its first sentence, so the rewrite takes "IT" from there instead of writing [needs: actor]`

---

### 14. Rule restated across sections

**RED:**

> Context: two sections of the same document.
>
> Section 2: Students must accept the AUP before they get application access.
>
> Appendix A: As stated earlier, students must accept the AUP before they get application access, and they must accept it again each year.

**GREEN:**

> Section 2: Students must accept the AUP before they get application access, and again each year.
>
> Appendix A: See Section 2 for AUP acceptance.

**Expected finding:** `[Prolixity] the appendix restates Section 2's rule ("As stated earlier") and adds one condition Section 2 lacks (accepting again each year), so the addition moves into the kept statement in Section 2, which keeps its "must", and the appendix copy becomes a pointer to it`

---

## D. Must stay unflagged, or flagged without a cut

### N1. Technical prose with precise terms

**RED:**

> Conditional Access evaluates the device compliance claim before it issues a token. A token issued during a Temporary Access Pass sign-in expires no later than the pass.

**GREEN:**

> Conditional Access evaluates the device compliance claim before it issues a token. A token issued during a Temporary Access Pass sign-in expires no later than the pass.

**Expected finding:** `(No finding: return the text unchanged. "Conditional Access", "device compliance claim" and "Temporary Access Pass" are domain terms the reader expects, not sesquipedalianism; "A token issued during …" is a participle that describes the token, which the actor rule leaves alone even though the first sentence names the issuer; and no word can go without losing meaning.)`

---

### N2. Operative contract doublet

**RED:**

> Context: clause 14.2 of a signed services agreement.
>
> The Supplier shall indemnify and hold harmless the Customer against any and all claims arising from the Services.

**GREEN:**

> Context: clause 14.2 of a signed services agreement.
>
> The Supplier shall indemnify and hold harmless the Customer against any and all claims arising from the Services.

**Expected finding:** `(Flag, do not cut: return the clause unchanged. This is operative contract text, so "indemnify and hold harmless" and "any and all" may carry distinct legal force; the skill flags them for the author instead of deleting them.)`

---

### N3. Deliberate emphasis

**RED:**

> Every nurse needs an active account before their first shift. Every one. A nurse without an account cannot sign in on the ward.

**GREEN:**

> Every nurse needs an active account before their first shift. Every one. A nurse without an account cannot sign in on the ward.

**Expected finding:** `(No finding: return the text unchanged. "Every one." is deliberate emphasis, which the skill keeps: repetition for emphasis is legitimate, and the rewrite must not flatten it.)`

---

### N4. Controlled language

**RED:**

> Context: a step from a maintenance procedure written to ASD-STE100.
>
> Make sure that there is sufficient clearance between the cover and the frame. Then install the cover.

**GREEN:**

> Context: a step from a maintenance procedure written to ASD-STE100.
>
> Make sure that there is sufficient clearance between the cover and the frame. Then install the cover.

**Expected finding:** `(No finding: return the text unchanged and point the user to ste100-writer. The text follows ASD-STE100, where "sufficient" is the approved word, so this skill does not apply to it.)`

---

### N5. A vague but stated reason

**RED:**

> Context: the user asks to tighten this sentence.
>
> The council does not lend phones to staff because of budget and supply constraints.

**GREEN:**

> Context: the user asks to tighten this sentence.
>
> The council does not lend phones to staff because of budget and supply constraints.

**Expected finding:** `(No finding: return the text unchanged. "budget and supply constraints" is vague but states the reason; a reason needs no [needs: …] after it, and replacing it with one fails.)`

---

### N6. A passive that should stay

**RED:**

> Each badge is printed on recycled card.

**GREEN:**

> Each badge is printed on recycled card.

**Expected finding:** `(No finding: return the text unchanged. "is printed" stays passive: who prints the badge is irrelevant to the point, which is the card.)`

---

## Verification Log

**Verified 2026-10-22.** Result: **20/20 passed.** Graded by an Opus agent reading `SKILL.md`, `references/taxonomy.md` and `TESTS.md`, with no edit to any of the three afterwards.

Produced against `TESTS.md` body sha256 `a835378cfb4a0748`, `SKILL.md` sha256 `44406820def10832` and `references/taxonomy.md` sha256 `f1d7e9ba11c0f482`. The body hash covers everything above this heading, so it survives this table being written. Recompute all three before trusting the rows: any later edit invalidates them.

| Test                                    | Finding matches Expected | Pass |
|-----------------------------------------|--------------------------|------|
| 1. Pleonasm                             | ✓                        | PASS |
| 2. Circumlocution                       | ✓                        | PASS |
| 3. Sesquipedalianism                    | ✓                        | PASS |
| 4. Legalese                             | ✓                        | PASS |
| 5. Bureauspeak, actor named in the text | ✓                        | PASS |
| 6. Bureauspeak, actor absent            | ✓                        | PASS |
| 7. Prolixity                            | ✓                        | PASS |
| 8. Logorrhea / word salad               | ✓                        | PASS |
| 9. Purple prose                         | ✓                        | PASS |
| 10. Review mode changes nothing         | ✓                        | PASS |
| 11. No invented specifics               | ✓                        | PASS |
| 12. Quoted text stays verbatim          | ✓                        | PASS |
| 13. Actor named elsewhere in the input  | ✓                        | PASS |
| 14. Rule restated across sections       | ✓                        | PASS |
| N1. Technical prose with precise terms  | ✓                        | PASS |
| N2. Operative contract doublet          | ✓                        | PASS |
| N3. Deliberate emphasis                 | ✓                        | PASS |
| N4. Controlled language                 | ✓                        | PASS |
| N5. A vague but stated reason           | ✓                        | PASS |
| N6. A passive that should stay          | ✓                        | PASS |

Counts: 20 tests (14 RED/GREEN, 6 must-stay-unflagged); 20 PASS, 0 PASS with discrepancy, 0 FAIL.

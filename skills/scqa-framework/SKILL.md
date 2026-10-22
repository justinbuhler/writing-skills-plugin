---
name: scqa-framework
description: Use when an opening, hook, or persuasive narrative needs to create reader tension before delivering a recommendation — especially for white papers, problem-solution docs, or any content where the audience must care before they'll listen.
allowed-tools: Read
---

# SCQA Framework

SCQA (Situation → Complication → Question → Answer) is Barbara Minto's pattern, developed while she was at McKinsey. It builds narrative tension so readers are primed to receive your core message. Use it for openings and hooks; use pyramid-editor to organize the supporting evidence that follows. When the full document needs a narrative spine — not just the opening — use scr-narrative instead.

## Two jobs

**Build (default).** The user gives a topic, notes, or a recommendation. You produce the labeled block in **Output format**.

**Critique.** The user shares an existing opening and asks whether it works. Report findings and change nothing unless the user asks for a rewrite. For each element, say whether it is present and quote the sentence or clause that carries it. Then list each failed check as `[Label] <what fails and why>`, using the label that the **Quality checklist** gives for that check, for example `[Complication urgency] …`. Use only those labels. Label by function, not by sentence position: one clause can carry an element, so "Although the cycle was built for X, it now covers Y" holds both S and C. If no check fails, say so and name the variant.

## What to ask for

If the audience is not stated, ask who it is and what it already knows. The audience decides whether a Situation is needed and which variant fits. Do not ask more than two questions. If you have enough to draft, draft, state your assumption about the audience, and write `[needs: …]` for each missing detail.

## The four elements

| Element | What it is | Key constraint |
|---|---|---|
| **Situation** | Stable, uncontroversial starting point | Reader nods along — no controversy; a fact the audience can confirm from its own context (for a sector-wide audience, a specific sector fact qualifies); generic trend statements fail |
| **Complication** | Change that disrupts the situation — a threat or an opportunity | Gives this audience a reason to act; may be conditional, estimated, or a range |
| **Question** | The question reader now wants answered | Usually implicit; when implicit, write it from C alone before reading A; must not presuppose A; your answer must address it exactly |
| **Answer** | Your core message / recommendation | One decision or claim, in one or two sentences — details go in the body |

## Complete example

**S**: Our engineering teams use AI coding assistants every day.

**C**: But generic assistants don't understand domain specifics. Teams spend more time correcting suggestions than coding, and 40% abandon them within weeks.

**Q** *(implicit)*: How do we get assistants that understand our domain?

**A**: **CAF turns Claude Code into domain-specific agents through markdown-based customization** — no programming required.

Variant used: **SCQA**. The Question comes from C alone (assistants that miss domain specifics), and A answers it with domain-specific agents; stating Q would add a line the reader does not need.

## Combined with pyramid-editor

SCQA gets the reader to care about your answer. Pyramid organizes proof of it.

```
Opening (SCQA)
└── S → C → Q → A  [A becomes Level 1 of the pyramid; under SCQ, the governing thought for body does]

Body (Pyramid)
├── Argument 1 supporting A  [Level 2]
│   └── Evidence             [Level 3]
├── Argument 2 supporting A  [Level 2]
│   └── Evidence             [Level 3]
└── Argument 3 supporting A  [Level 2]
    └── Evidence             [Level 3]

Closing: reinforce A + call to action
```

## Variations

| Variant | When to use | What's dropped |
|---|---|---|
| **SCQ** | The document body is the answer | Answer is not in the opening; the Question closes the intro |
| **SCA** | The Question can be left out altogether | Question is not written at all — an implicit Question still marked in the text is SCQA |
| **CSA** | Audience already knows the situation, for example because it set the arrangement being disrupted | Question is not written; C comes first, and S follows briefly or is left implied |

## Quality checklist

Each check carries the label a critique uses when it fails.

- [ ] `[Situation missing]` A Situation comes before the Complication; a Complication-first opening is a defect only when the audience lacks the Situation (for an audience that has it, the opening is CSA)
- [ ] `[Situation quality]` Situation is familiar and non-controversial: a structural fact, not a judgment; move an evaluative claim to C rather than dropping it
- [ ] `[Situation scope]` Situation is a fact the audience can confirm from its own context; for a sector-wide audience a specific sector fact qualifies, and generic trends ("digital transformation is reshaping every industry") fail; if the input gives no such fact, write `[needs: …]` for it
- [ ] `[Complication–Situation link]` Complication follows from the Situation: it is what the Situation has run into, not an unrelated trend or a problem about something else
- [ ] `[Complication is the solution]` Complication states the problem, not the fix; "we need to …" or a recommended action belongs in A, and C says what goes wrong without it
- [ ] `[Complication urgency]` Complication gives this audience a reason to act (not "could be better"), using only figures the input supplies; a conditional risk, an estimate, a range, or an opportunity qualifies; where urgency needs a number the input lacks, write `[needs: figure for …]`
- [ ] `[Complication form]` Complication fits in one or two sentences; for several pains or a table, see **Output format**
- [ ] `[Question–Complication fit]` Question naturally arises from complication; when implicit, write it from C alone before reading A; it does not presuppose A (no "the transition" before A has named one)
- [ ] `[Answer–Question fit]` Answer directly addresses the question — not adjacent to it. If it does not and the text states the Question outright, you may change that stated Q to fit A only if the new Q still arises from C; otherwise, and always when Q is implicit, keep the Q written from C, mark the gap with `[needs: …]`, and ask the author. Never add claims to A
- [ ] `[Answer complexity]` Answer states one decision or claim in one or two sentences; thresholds, tier specifications, and lists of three or more features or steps go to the body
- [ ] `[Variant mismatch]` The variant fits the audience and the document: CSA only for an audience that already knows the Situation, SCQ only when the body is the answer; flow reads S → C → Q → A (C → S → A under CSA)

## Output format

Deliver as a labeled block:

```
**S:** [one to two sentences]
**C:** [one to two sentences]
**Q:** [stated, or marked as implicit]
**A:** [one to two sentences — the governing thought]
```

Variant shapes:

- **SCA:** omit the Q line. In a prose opening, a Question that no sentence states counts as SCA.
- **SCQ:** write `**A:** (deferred to body)`, then `**Governing thought for body:** [one sentence]`. That sentence becomes Level 1 of the pyramid.
- **CSA:** put the C line first; the S line is brief or reads `(implied — audience already knows it)`; omit the Q line.

Note which variant was used (SCQA / SCQ / SCA / CSA) and why. When writing-workflow calls this skill, give the block, then the prose opening it asks for.

If the Complication holds several pains or a table, name in C the pain that drives A, keep the figures A depends on, and list the rest under **Body material**.

**Keep claims as strong as the input makes them.** Carry every condition, modal verb, range, and qualifier ("if", "may", "up to", "about", "15–20%") into the block unchanged. Sharpen a weak Complication with `[needs: …]` markers, never by making its wording stronger.

**Use only the facts you were given.** Do not add a fact, name, number, date, owner, source, or claim that is not in the input or supplied by the user. When a rule calls for a detail the input lacks, write `[needs: <detail>]` in its place, for example `[needs: owner]` or `[needs: source for "Eight of twelve depots report the fault"]`, and list every gap under **Gaps** at the end of your response. Leave any `[needs: …]` already in the input where it is.

---

## Second example — government procurement reform

**Input:** A policy brief recommending that the agency overhaul its procurement approval process, which is causing project delays. The author's notes: every request goes through one six-week review cycle designed for capital purchases above $1 million; the cycle now also covers routine purchases under $50,000; it delays projects by an average of two months per contract and takes 30% of the procurement team's capacity on low-risk approvals; the proposal is a five-day fast-track for purchases under $50,000, keeping the existing cycle for capital items so oversight stays where financial risk is highest.

**S**: The agency approves all procurement requests through a single six-week review cycle that was designed for capital purchases above $1 million.

**C**: The same cycle now also covers routine purchases under $50,000. It delays projects by an average of two months per contract and takes 30% of the procurement team's capacity on low-risk approvals.

**Q** *(implicit)*: How do we stop routine purchases from tying up the six-week cycle?

**A**: **The agency should introduce a two-track approval system** that fast-tracks routine purchases and keeps the existing cycle for capital items, so oversight stays where financial risk is highest. (The $50,000 threshold and the five-day review go in the body.)

Variant used: **SCQA**. Q is written from C alone and left implicit because it arises naturally from the complication; stating it explicitly would slow the brief. The oversight point comes from the author's proposal, so it lives in A, not in Q.

---

## Common mistakes

**Starting with complication** — reader lacks context. This is a defect only when the audience does not already know the Situation; for an audience that does, the opening is CSA.

Before: "AI coding assistants produce unreliable code..."

After: "[needs: Situation the audience already accepts]. But AI coding assistants produce unreliable code..." (Situation first, then Complication; the Before gives no Situation, so mark the gap rather than invent one)

---

**Weak complication** — no urgency, reader doesn't care.

Before: "Sometimes the suggestions could be better."

After: "Sometimes the suggestions could be better [needs: figure for how often they are wrong], and [needs: what a wrong suggestion costs the team]." (Keep the author's words; name the pain and quantify it only with what the input supplies, marking each gap. Do not harden "could be better" into a stronger claim the input never made)

---

**Answer doesn't match question** — reader notices the mismatch.

Before: Q: "How do we make AI more reliable?" A: "CAF provides markdown-based customization." (Customization ≠ reliability)

After: Q: "How do we make AI more reliable?" A: "CAF provides markdown-based customization. [needs: how customization makes the assistant more reliable — ask the author whether it does]" (Do not rewrite Q from A: that makes the fit pass by construction. Keep A's claim, mark the gap, and ask the author; do not add claims to A)

---

**Answer too complex** — save details for the body.

Before: "CAF is a meta-framework that provides commands, agents, and skills organized in a plugin architecture with markdown-based configuration that allows..."

After: "CAF is a meta-framework configured in markdown." (One claim in one sentence; the commands, agents, and skills, the plugin architecture, and the rest go in the body)

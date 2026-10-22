# No AI Slop Skill — Red/Green Test Suite

Each test has:

- **RED:** text with an AI slop pattern (should be flagged or edited)
- **GREEN:** cleaned version
- **Expected finding:** the pattern the skill should name (detect mode) or remove (edit mode)

---

## Words to Cut

### W1 — Banned vocabulary

**RED:**

> We need to leverage the payroll team's audit checklist to streamline month-end close and empower regional leads to deliver robust, cutting-edge reports at every stage of this ever-evolving journey.

**GREEN:**

> We need to use the payroll team's audit checklist to simplify month-end close and help regional leads deliver reports at every stage.

**Expected finding:** `[banned words] "leverage," "streamline," "empower," "robust," "cutting-edge," "ever-evolving" — all on the banned list. Replace the verbs "leverage," "streamline," and "empower" with plain verbs, cut the adjectives "robust," "cutting-edge," and "ever-evolving," and add no claim the draft does not make.`

---

### W2 — Often-empty adverbs

**RED:**

> The login bug is literally blocking sign-ups. We truly fundamentally need to fix it.

**GREEN:**

> The login bug is blocking sign-ups. We need to fix it.

**Expected finding:** `[empty adverbs] "literally," "truly," "fundamentally" add nothing and compound each other. Cut them.`

---

### W3 — Often-empty phrases

**RED:**

> At the end of the day, when it comes to shipping great software, it's worth noting that in today's world, the reality is that speed matters.

**GREEN:**

> Speed matters when shipping great software.

**Expected finding:** `[empty phrases] "At the end of the day," "when it comes to," "it's worth noting that," "in today's world," "the reality is" — five consecutive throat-clearing phrases before the point. Cut all of them and lead with the point.`

---

## Patterns to Cut

### P1 — Binary contrasts

**RED:**

> The new rota isn't a spreadsheet. It's a commitment to the crew. Shift swaps are not just a convenience; they're how people keep their weekends. The question isn't flexibility. It's fairness.

**GREEN:**

> The new rota is a commitment to the crew. Shift swaps are how people keep their weekends. Fairness matters more than flexibility.

**Expected finding:** `[binary contrasts] Three consecutive "not X / it's Y" constructions. State Y directly each time. No negated item is an alternative the reader might assume, such as a ruled-out cause or a scope exclusion, and the draft is not first-person, so neither keep condition applies.`

---

### P2 — Throat-clearing openers

**RED:**

> Here's the thing: most teams ship the wrong feature. Let me be clear: prioritization is a skill. I'll be honest, the backlog is usually too long.

**GREEN:**

> Most teams ship the wrong feature. Prioritization is a skill. The backlog is usually too long.

**Expected finding:** `[throat-clearing openers] "Here's the thing," "Let me be clear," "I'll be honest" — cut each opener and state the point directly. The third opener introduces a general claim about backlogs, not an admission by the writer, so the keep condition for "I'll be honest" does not apply.`

---

### P3 — Faux-insight setups

**RED:**

> Here's what most people miss: the bottleneck isn't the API. What nobody tells you about deployments: the real cost is the rollback. The part everyone skips: you have to test the unhappy path.

**GREEN:**

> The bottleneck is not the API. The real cost of a deployment is the rollback. Test the unhappy path.

**Expected finding:** `[faux-insight setups] "Here's what most people miss," "What nobody tells you," "The part everyone skips" — these frame common knowledge as secret insider wisdom. Cut the flattering setup; make the claim stand on its own.`

---

### P4 — Colon reveals

**RED:**

> The change that fixed it: we capped the queue. The real cost: reviewer time. The number worth watching: retries per job.

**GREEN:**

> We capped the queue, which fixed it. Reviewer time is the real cost. Retries per job is the number worth watching.

**Expected finding:** `[colon reveals] Three "teaser phrase, colon, reveal" constructions; none is a field label. Rewrite each as a plain sentence. Use colons for lists, labels, and quotes — not fake drama.`

---

### P5 — Superficial analysis (-ing clauses)

**RED:**

> The team shipped daily releases, highlighting their commitment to continuous improvement and showcasing a culture of speed, reflecting the broader shift in how software teams operate.

**GREEN:**

> The team shipped daily releases.

**Expected finding:** `[superficial analysis] "Highlighting," "showcasing," "reflecting" — three trailing -ing clauses that claim to interpret the fact without adding information. State what happened; cut the interpretation. If there's a real point about what the daily releases meant, state it as a fact only if the draft says so.`

---

### P6 — Importance puffery

**RED:**

> This partnership marks a pivotal moment for the industry. It stands as a testament to what's possible when two organizations align on shared values and plays a vital role in solidifying their position as market leaders.

**GREEN:**

> The two organizations formed a partnership.

**Expected finding:** `[importance puffery] "Marks a pivotal moment," "stands as a testament," "plays a vital role," "solidifying their position" — four consecutive importance claims with no supporting facts. State what actually happened and let the reader judge whether it matters.`

---

### P7 — Interpretive metadiscourse

**RED:**

> This distinction matters. What's worth noticing here is that the index is stale. To put it another way, the report's figures are out of date. The takeaway is that the numbers can't be trusted.

**GREEN:**

> The index is stale. The report's figures are out of date and can't be trusted.

**Expected finding:** `[interpretive metadiscourse] "This distinction matters," "What's worth noticing here is," "To put it another way," "The takeaway is that" — four consecutive lines telling the reader what to notice instead of showing the fact. State the claim directly and cut all the commentary.`

---

### P7b — Metadiscourse that points at evidence

**RED:**

> The pilot logged every help-desk call for six weeks. As you can see in Table 2, password resets made up half of them.

**GREEN:**

> The pilot logged every help-desk call for six weeks. Table 2 shows that password resets made up half of them.

**Expected finding:** `[interpretive metadiscourse] "As you can see in Table 2" tells the reader what to notice, but it also points to the evidence. Keep the reference as a plain pointer ("Table 2 shows"); do not delete it.`

---

### P8 — Weasel attribution

**RED:**

> Experts agree that remote work improves productivity. Industry reports suggest the trend will continue. Many argue it cuts staff turnover.

**GREEN:**

> Remote work improves productivity [needs: source for "remote work improves productivity"]. The trend will likely continue [needs: source for "the trend will continue"]. It may cut staff turnover [needs: source for "it cuts staff turnover"].
>
> **Gaps**
>
> - [needs: source for "remote work improves productivity"]
> - [needs: source for "the trend will continue"]
> - [needs: source for "it cuts staff turnover"]

**Expected finding:** `[weasel attribution] "Experts agree," "industry reports suggest," "many argue" — no source named for any claim. The draft gives no source, so remove each weasel phrase, keep the claim with its hedge ("suggest" becomes "likely", "argue" becomes "may"), and write [needs: source for "<claim>"] after it. List all three markers under Gaps. Do not cut the claims unless the user says to, and do not invent a source.`

---

### P9 — Fake-strong verbs

**RED:**

> The reservoir functions as the town's main water supply. The pumping station serves as a link between the reservoir and the treatment works. The control room acts as the place where operators watch every pump.

**GREEN:**

> The reservoir is the town's main water supply. The pumping station links the reservoir and the treatment works. Operators watch every pump from the control room.

**Expected finding:** `[fake-strong verbs] "Functions as," "serves as," "acts as" stand in for "is" or a direct verb, and none marks an acting or interim role, so the keep condition does not apply. Use "is" or a direct verb the draft supports ("links," "watch"), and name no function the draft does not state.`

---

### P10 — Synonym cycling

**RED:**

> The gritter leaves the depot at 5 a.m. The truck salts the main roads first. The vehicle then covers the bus routes. The lorry is back by 9 a.m.

**GREEN:**

> The gritter leaves the depot at 5 a.m., salts the main roads first, then covers the bus routes, and is back by 9 a.m.

**Expected finding:** `[synonym cycling] "Gritter," "truck," "vehicle," "lorry" all refer to the same thing. Use one clear term consistently. Don't rotate names for style — it confuses the reader about whether these are the same or different entities.`

---

### P11 — Negative listing

**RED:**

> From January, staff get something new from IT. Not a newsletter. Not a podcast. Not a poster campaign. A shared pool of laptops they can book by the day.

**GREEN:**

> From January, staff get a shared pool of laptops from IT that they can book by the day.

**Expected finding:** `[negative listing] Three-item "not X, not Y, not Z" setup before the real definition. State the definition directly. Nothing in the draft suggests a reader would take a laptop pool for a newsletter, podcast, or poster campaign, so no negation rules out something the reader might assume and the keep condition does not apply. The three negations only delay the point.`

---

### P12 — Dramatic fragmentation

**RED:**

> We shipped. Then we iterated. Then we iterated again. Simple as that. Nothing more to it. Ship. Learn. Repeat.

**GREEN:**

> We shipped, then iterated twice.

**Expected finding:** `[dramatic fragmentation] Stacked one-sentence fragments used as a rhetorical rhythm device. Merge into complete sentences. A single fragment for emphasis would stay; a row of them reads as performance. "Simple as that. Nothing more to it." add nothing: cut them. "Ship. Learn. Repeat." is also a fake-profound kicker: delete it, do not restate it, and end on the concrete sentence.`

---

### P13 — Rhetorical setups

**RED:**

> What if I told you the bottleneck wasn't the database? Think about it: most engineers optimize the wrong layer. Plot twist: the slow part is the ORM, not the query.

**GREEN:**

> The bottleneck wasn't the database. Most engineers optimize the wrong layer. The slow part is the ORM, not the query.

**Expected finding:** `[rhetorical setups] "What if I told you," "Think about it," "Plot twist" — cut each setup and make the claim directly. These framing devices delay the point.`

---

### P14 — Fake-profound kickers

**RED:**

> We fixed the bug, shipped the patch, and closed the incident. In the end, reliability isn't a feature. It's a promise.

**GREEN:**

> We fixed the bug, shipped the patch, and closed the incident.

**Expected finding:** `[fake-profound kicker] The last two sentences ("reliability isn't a feature. It's a promise.") turn a concrete incident resolution into a metaphor. Delete it. End on the last concrete sentence. Don't rewrite the kicker into a better one — remove it.`

---

### P15 — Summary-recap endings

**RED:**

> Overall, we've seen that the new process reduces handoffs, improves quality, and gives teams clearer ownership. In conclusion, this approach is the right move for the organization. Ultimately, it comes down to execution.

**GREEN:**

> _(Cut the paragraph. End on the last concrete sentence before this recap.)_

**Expected finding:** `[summary-recap ending] "Overall," "In conclusion," "Ultimately" — three sentences that restate the document without adding anything. "This approach is the right move for the organization" restates the case the piece has made; it records no decision (no one approves, adopts, or schedules anything) and adds no figure, date, or action, so the keep condition does not apply. The reader was just there. End on the last concrete point or next action.`

---

### P16 — Formatting slop

**RED:**

> ## Handover Changes 🩺
>
> From Monday the **night shift** starts at 19:30. Two changes:
>
> - Handover moves to the nurses' station.
> - Each nurse hands over four beds.

**GREEN:**

> From Monday the night shift starts at 19:30. Handover moves to the nurses' station, and each nurse hands over four beds.

**Expected finding:** `[formatting slop] Emoji in the heading, a header over a short section (one sentence, a "Two changes:" lead-in, and a two-item list), bold sprinkled mid-sentence on "night shift", and a two-item bullet list where two sentences of prose would read better. Format follows content — drop the heading and the bold, and merge the bullets into prose. The draft makes no unsupported claim, so no [needs: …] marker is called for.`

---

## Editing Principles

### E1 — Claimed result with no figure in the draft

**RED:**

> Switching the depot to the new rota software significantly cut overtime for the night crew.

**GREEN:**

> Switching the depot to the new rota software significantly cut overtime for the night crew [needs: figure for overtime reduction].
>
> **Gaps**
>
> - [needs: figure for overtime reduction]

**Expected finding:** `[be concrete] "significantly cut overtime" claims a result the draft gives no figure for. Keep the claim, do not supply a number, write [needs: figure for overtime reduction] after it, and list it under Gaps.`

---

## Voice Preservation

### V1 — Skill should preserve distinctive human voice

**RED (input to edit):**

> I spent three years building the wrong thing. Not wrong as in buggy — wrong as in nobody cared. Turns out, I'd been talking to myself the whole time. Embarrassing, honestly.

**GREEN (expected output — returned unchanged):**

> I spent three years building the wrong thing. Not wrong as in buggy — wrong as in nobody cared. Turns out, I'd been talking to myself the whole time. Embarrassing, honestly.

**Expected finding:** `(No finding — this draft contains no AI pattern. Skill should return it unchanged and say why: the "not X as in Y" contrast is the writer's own rather than a default sentence shape, the one-sentence "Embarrassing, honestly" fragment is characteristic cadence, and the "Turns out," beat belongs to the spoken rhythm the skill is told to keep. The dash is humanizer's remit, not this skill's. Under the minimum-effective-edit principle there is nothing to fix. Do not homogenize.)`

---

### V2 — "I'll be honest" that introduces an admission

**RED (input to edit):**

> I'll be honest, I argued against the four-day week for most of last year. I assumed output would drop, and it didn't. It went up 8% over two quarters, and I was slow to admit it. Honestly, that stung.

**GREEN (expected output — returned unchanged):**

> I'll be honest, I argued against the four-day week for most of last year. I assumed output would drop, and it didn't. It went up 8% over two quarters, and I was slow to admit it. Honestly, that stung.

**Expected finding:** `(No finding — return it unchanged. "I'll be honest" introduces a genuine admission (the writer argued against the change), so the throat-clearing cut does not apply. "It didn't. It went up" is the writer's own first-person contrast. "Honestly, that stung." is one short sentence in the writer's spoken rhythm, not a run of fragments, so the adverb and the sentence both stay.)`

---

## Structured Text (must stay unflagged)

### N1 — Incident report with field labels, passives, and a ruled-out cause

**RED (input to edit):**

> ## Payroll export incident summary
>
> Root cause: A disk on the reporting server filled up during the nightly export.
> Impact: 212 of 1,040 payslips were delayed by one day.
>
> The new tax tables loaded on Monday did not cause the failure. Log files that had not been rotated since March caused it.
>
> The disk was cleared at 02:15 and the export was rerun at 02:40. Two payslips were sent twice and have been recalled.
>
> Overall, 9 of 11 regional offices had no delayed payslips.
>
> Next step: Enable daily log rotation on the reporting server (owner: Platform team, due 14 October).

**GREEN (expected output — returned unchanged):**

> _(Same as RED.)_

**Expected finding:** `(No finding — return it unchanged. "Root cause:", "Impact:", and "Next step:" are field labels, not colon reveals. "did not cause the failure" rules out a cause the reader might suspect, so the binary-contrast cut does not apply. The remaining passives name no actor, and the only team named owns the future action, so none becomes active. "Overall," opens a new figure (9 of 11 offices), not a recap.)`

---

### N2 — FAQ and procedure

**RED (input to edit):**

> ## Guest Wi-Fi FAQ
>
> **How do I get a guest password?**
> Open the visitor app and tap **Request access**. The password arrives by text within two minutes.
>
> **Why did my password stop working?**
> Guest passwords expire at midnight. Request a new one the next day.
>
> ## Reset the lobby access point
>
> WARNING: Do not unplug the access point while the status light is flashing. The firmware can be damaged.
>
> 1. Wait until the status light is steady.
> 2. Press and hold the reset button for 10 seconds.
> 3. Wait for the light to turn green.
> 4. Test the connection from a guest device.
>
> Use only the reset button. Record the reset in the site log.

**GREEN (expected output — returned unchanged):**

> _(Same as RED.)_

**Expected finding:** `(No finding — return it unchanged. The two bold questions are FAQ question-and-answer pairs, not rhetorical setups or headers over tiny sections. **Request access** is a bold UI label, not decorative bold. The WARNING, the four uniform numbered steps, and "Use only the reset button" are safety, procedure, and compliance text, exempt from the portability test, robotic rhythm, and formatting slop.)`

---

### N3 — Status rows, quotation, product name, code, and a footnoted claim

**RED (input to edit):**

> # Depot fleet status, week 41
>
> **North depot.** 18 of 20 vans are in service, and 6 of 8 charging bays work. Risk: One bay is waiting for a part.
> **South depot.** 15 of 20 vans are in service, and 8 of 8 charging bays work. Risk: Two vans are waiting for tyres.
> **East depot.** 20 of 20 vans are in service, and 7 of 8 charging bays work. Risk: None open.
>
> Tom Okafor acts as fleet manager until the new hire starts on 3 November. The tyre supplier just confirmed delivery for Thursday, so the South depot risk may close this week.
>
> The drivers' rep wrote: "Honestly, the new booking screen is a game changer. We can finally leverage the spare vans." Bookings run on Streamline Fleet 3.1, and drivers reset their PIN with the `harness-reset` command.
>
> Studies show that overnight charging extends battery life by about 15% [2].
>
> [2] Electric Fleet Operators Survey 2025, table 7.

**GREEN (expected output — returned unchanged):**

> _(Same as RED. Naming the survey inline is an optional suggestion, not a required edit.)_

**Expected finding:** `(No finding — return it unchanged. The three depot rows are deliberately parallel status entries, exempt from robotic rhythm. "acts as" marks an interim role, so it stays. "just confirmed" means recently, a time meaning, so it stays. "Honestly," "game changer," and "leverage" sit inside a quotation, "Streamline Fleet 3.1" is a product name, and the harness-reset command is code, so the word lists do not apply. "Studies show" carries footnote [2], so the claim already has its source and gets no [needs: …] marker. "Risk:" is a field label.)`

---

## Detect Mode

### D1 — Detect without rewriting

**Input (detect request):**

> Is this AI slop?
>
> This groundbreaking initiative marks a pivotal moment for our industry. Leveraging cutting-edge technology, our team has worked to streamline processes and empower stakeholders across the organization. It's worth noting that experts agree this transformative approach will fundamentally reshape how we operate going forward.

**Expected finding (detect mode output — no rewrite):**

> **Patterns found:**
>
> - [importance puffery] "groundbreaking," "marks a pivotal moment" — sentence 1; "will … reshape how we operate" — sentence 3. Fix: cut them, or state what the initiative is and what it changes; the writer must supply that.
> - [banned words] "Leveraging," "cutting-edge," "streamline," "empower" — sentence 2; "transformative" — sentence 3. Fix: replace the verbs ("Leveraging," "streamline," "empower") with plain verbs and cut the adjectives ("cutting-edge," "transformative").
> - [empty phrases] "It's worth noting that," "going forward" — sentence 3. Fix: cut both.
> - [weasel attribution] "experts agree" — sentence 3. Fix: if the claim stays, name the source; the writer must supply it.
> - [empty adverb] "fundamentally" — sentence 3. Fix: cut.
>
> Want me to edit the draft?

The portability test is an editing principle, not a pattern, so detect mode does not report it.

---

### D2 — Detect on a clean draft

**Input (detect request):**

> Is this AI slop?
>
> The printer on floor 3 jams when the tray holds more than 200 sheets. Facilities will fit a smaller tray on Friday. Until then, load 150 sheets at most.

**Expected finding (detect mode output — no rewrite):**

> No pattern from this skill appears in this draft, and there is no near-miss to report. No edit offered: the draft needs none.

---

## Verification Log

**Verified 2026-10-22.** Result: **28/28 passed.** Graded by an Opus agent reading `SKILL.md` and `TESTS.md`, with no edit to either file afterwards. `eval.md` was read only to check the GREENs against it.

Produced against `TESTS.md` body sha256 `dd824fdda948d940` and `SKILL.md` sha256 `161c43e618f9d4ce`. The body hash covers everything above this heading, so it survives this table being written. Recompute both before trusting the rows: any later edit invalidates them, and a log that certifies rather than records hides the defects it exists to surface.

Failures: none.

Every count in an Expected finding was checked by a Python split (word-list hits, sentences, colons, trailing -ing clauses, new words in each GREEN). No GREEN adds a fact, figure, name, source, or actor its RED lacks; P6's "formed" is entailed by "This partnership", P8's "likely" and "may" carry the hedges in "suggest" and "argue", and P12's "twice" is derived from "iterated. Then we iterated again."

| Test                                                                    | RED flags | GREEN clean | Pass |
|-------------------------------------------------------------------------|-----------|-------------|------|
| W1 — Banned vocabulary                                                  | ✓         | ✓           | PASS |
| W2 — Often-empty adverbs                                                | ✓         | ✓           | PASS |
| W3 — Often-empty phrases                                                | ✓         | ✓           | PASS |
| P1 — Binary contrasts                                                   | ✓         | ✓           | PASS |
| P2 — Throat-clearing openers                                            | ✓         | ✓           | PASS |
| P3 — Faux-insight setups                                                | ✓         | ✓           | PASS |
| P4 — Colon reveals                                                      | ✓         | ✓           | PASS |
| P5 — Superficial analysis (-ing clauses)                                | ✓         | ✓           | PASS |
| P6 — Importance puffery                                                 | ✓         | ✓           | PASS |
| P7 — Interpretive metadiscourse                                         | ✓         | ✓           | PASS |
| P7b — Metadiscourse that points at evidence                             | ✓         | ✓           | PASS |
| P8 — Weasel attribution                                                 | ✓         | ✓           | PASS |
| P9 — Fake-strong verbs                                                  | ✓         | ✓           | PASS |
| P10 — Synonym cycling                                                   | ✓         | ✓           | PASS |
| P11 — Negative listing                                                  | ✓         | ✓           | PASS |
| P12 — Dramatic fragmentation                                            | ✓         | ✓           | PASS |
| P13 — Rhetorical setups                                                 | ✓         | ✓           | PASS |
| P14 — Fake-profound kickers                                             | ✓         | ✓           | PASS |
| P15 — Summary-recap endings                                             | ✓         | ✓           | PASS |
| P16 — Formatting slop                                                   | ✓         | ✓           | PASS |
| E1 — Claimed result with no figure in the draft                         | ✓         | ✓           | PASS |
| V1 — Skill should preserve distinctive human voice                      | n/a       | ✓           | PASS |
| V2 — "I'll be honest" that introduces an admission                      | n/a       | ✓           | PASS |
| N1 — Incident report with field labels, passives, and a ruled-out cause | n/a       | ✓           | PASS |
| N2 — FAQ and procedure                                                  | n/a       | ✓           | PASS |
| N3 — Status rows, quotation, product name, code, and a footnoted claim  | n/a       | ✓           | PASS |
| D1 — Detect without rewriting                                           | ✓         | n/a         | PASS |
| D2 — Detect on a clean draft                                            | n/a       | ✓           | PASS |

Counts: 22 flagging tests (W1-W3, P1-P16 plus P7b, E1, D1) and 6 no-finding tests (V1, V2, N1-N3, D2).

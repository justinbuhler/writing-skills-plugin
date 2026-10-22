# Humanizer Skill — Red/Green Test Suite

Each test has:

- **RED:** text that violates the check (should be flagged and rewritten)
- **GREEN:** humanized version of the same text
- **Expected finding:** the AI pattern the skill should identify

Section numbers follow the humanizer skill's pattern catalogue in `SKILL.md` (1–25 as of v3.0.0) and are grouped under the same A–E headings. Not every pattern has a test case — patterns with no test are omitted. The 28 pattern tests cover the patterns concrete enough to evaluate with a RED/GREEN pair. Section F adds five tests, N1 to N5, whose GREEN is the RED unchanged: they check that the skill stays quiet on clean text, gated tells, and text it must leave alone. 33 tests in all.

No RED text reuses a "Before" example from `SKILL.md`. A test whose input is the skill's own worked example checks recall, not application, and cannot fail when the rule changes. Checked by longest shared word-run, not exact match: the longest run any RED shares with a `Before:` block is 5 words, and those runs contain watch-list trigger phrases the test has to include.

GREEN texts add no fact, name, number, date, or actor that is absent from their RED, per step 2 of the skill's workflow. Test 11 turns the reader's own actions into an imperative or `You`, and keeps the passive for actions the RED assigns to no one, per §11.

Every GREEN stays inside its RED. That claim is checkable: no GREEN introduces a figure, date, proper noun, named entity, or actor absent from its RED, and none adds a ranking, broadens a claim, or drops a qualifier. Number words used idiomatically or as rewording do not count.

Patterns with no test case: 5, 10, 21, 24, 25.

---

## A. Staging instead of stating

### 1 — Not X but Y

**RED:**

> It's not just a report; it's a roadmap. It's not merely data; it's a call to action. Data included, no guessing.

**GREEN:**

> The report sets out the data and the actions it points to, so nothing is left to infer.

**Expected finding:** `[1 not X but Y] Two consecutive flip constructions — "It's not just a report; it's a roadmap" and "It's not merely data; it's a call to action" — plus the clipped negative tail "no guessing." Remove the rhetorical flip; state each point directly.`

---

### 2 — One-line closers and dramatic fragments

**RED:**

> The migration finished ahead of schedule. No downtime. No rollback. No angry tickets.
>
> That is the real win.

**GREEN:**

> The migration finished ahead of schedule with no downtime, no rollback, and no angry tickets.

**Expected finding:** `[2 one-line closers] A row of fragments ("No downtime. No rollback. No angry tickets.") followed by a one-sentence closer that restates the paragraph. Merge the fragments into one sentence with a specific claim and cut the closer.`

---

### 3 — Sayings that sound deep

**RED:**

> The real question is whether the schema survives the move. At its core, this is a documentation problem. What really matters is field-level meaning, and fundamentally, migration is the currency of trust between the two systems.

**GREEN:**

> The question is whether the schema survives the move, which depends on whether each field's meaning is documented.

**Expected finding:** `[3 sayings that sound deep] "The real question is," "At its core," "What really matters," "fundamentally," and the aphorism "the currency of trust" — ordinary points dressed as hidden truths. Replace each saying with the specific claim. "Migration is the currency of trust" has no specific claim behind it, so it is cut rather than restated.`

---

### 4 — Staged run-up before the point

**RED:**

> Now let's look at the certificate renewal path. Quick note before we start: this one trips people up. Let's break it down step by step.

**GREEN:**

> The certificate renewal path trips people up.

**Expected finding:** `[4 staged run-up] "Now let's look at," "Quick note before we start," "Let's break it down step by step" — three consecutive announcements that stage the point instead of making it. Remove them and state the first fact directly.`

---

### 4 — Staged run-up before the point (staged candor)

**RED:**

> Honestly? The results are mixed. Look, the data tells a clear story. Here's the thing: not every team has the capacity to implement this.

**GREEN:**

> The results are mixed. The data tells a clear story. Not every team has the capacity to implement this.

**Expected finding:** `[4 staged run-up] "Honestly?," "Look," "Here's the thing" — standalone openers that stage candor before ordinary claims. Remove the three openers and keep all three claims that follow them.`

---

## B. Rhythm by rule

### 6 — Forced triads

**RED:**

> Seamless, frictionless, and effortless onboarding is what every vendor in this category promises. Our scoring weighed cost, risk, and cultural fit before anything else was considered.

**GREEN:**

> Every vendor in this category promises easy onboarding. Our scoring weighed cost, risk, and cultural fit first.

**Expected finding:** `[6 forced triads] "Seamless, frictionless, and effortless" is one claim in three words, not three ideas. Merge it into one claim, or develop the item that carries the weight. Keep "cost, risk, and cultural fit": three distinct scoring criteria are three real items.`

---

### 7 — Repeated sentence openings

**RED:**

> She completed the audit in March. She submitted the report in April. She presented to the board in May. She received approval by June.

**GREEN:**

> She completed the audit in March, submitted the report in April, presented to the board in May, and had approval by June.

**Expected finding:** `[7 repeated openings] Four consecutive sentences opening with "She." Merge the sentences, change the subject, or begin with the action.`

---

### 8 — Dashes as the universal connector

**RED:**

> The depot reopened on Monday — two weeks after the flood. Crews moved the salt store to higher ground — the old bay sat below the drainage line. Gritting routes now start from the north yard – a change the drivers asked for.

**GREEN:**

> The depot reopened on Monday, two weeks after the flood. Crews moved the salt store to higher ground: the old bay sat below the drainage line. Gritting routes now start from the north yard, a change the drivers asked for.

**Expected finding:** `[8 dashes] Three dashes used as the connector in one paragraph, one in each sentence: two em dashes (—) and one en dash (–). A run of dashes clears the gate without other tells. Replace each with a comma, period, colon, or parentheses, or rewrite. Exception: keep if the writer's sample uses them at a comparable rate.`

---

### 9 — Stacked qualifiers

**RED:**

> Here's the thing: the change could potentially affect up to 10% of scheduled reports, and in some cases it may arguably delay delivery by about an hour. To be fair, reports rebuilt on the new template after 1 July should see no change.

**GREEN:**

> The change may affect up to 10% of scheduled reports and can delay delivery by about an hour. Reports rebuilt on the new template after 1 July should see no change.

**Expected finding:** `[9 stacked qualifiers] "could potentially," "in some cases it may arguably," and "To be fair" pile qualifiers onto the passage. Cut each stack to one hedge and never remove the last. Keep "up to 10%," "about an hour," "should," and the condition "rebuilt on the new template after 1 July": numeric qualifiers and conditions are part of the claim. §9 is *weak alone*; the §4 opener "Here's the thing:" supplies the company and is cut too. "Can delay" keeps the "only sometimes" sense of the cut "in some cases".`

---

### 11 — Passive voice and missing subjects

**RED:**

> The form must be submitted by the deadline. Approval will be granted upon review, and the portal serves as the system of record. Errors may be corrected before submission is finalized.

**GREEN:**

> Submit the form by the deadline. Approval will be granted after review, and the portal is the system of record. You can correct errors before the submission is finalized.

**Expected finding:** `[11 passive voice] Four passive constructions across three sentences — "must be submitted," "will be granted," "may be corrected," "is finalized" — hide who acts. Where the reader acts (submits, corrects), use the imperative or "you". The RED never names who grants approval or who finalizes the submission, so keep those passives rather than invent an actor. §11 is *weak alone*; the §18 verb "serves as" in the same passage supplies the company the gate requires.`

---

## C. Inflation and borrowed authority

### 12 — Overused AI words

**RED:**

> Additionally, this initiative showcases the team's commitment to fostering a vibrant, inclusive culture. It is crucial that all stakeholders align with the pivotal values that underscore our enduring mission.

**GREEN:**

> This initiative shows the team supports an inclusive culture. All stakeholders must follow the core values behind our mission.

**Expected finding:** `[12 overused AI words] Cluster of high-frequency AI vocabulary in one passage: "Additionally," "showcases," "fostering," "vibrant," "crucial," "align," "pivotal," "underscore," "enduring." The §16 phrase "commitment to" goes with them. Replace each with plain words or cut the phrase.`

---

### 13 — Inflated significance

**RED:**

> The university's IT team moved staff sign-in to a shared identity provider last year. The change stands as a watershed for access management and reflects a broader shift toward federated trust. It has left an indelible mark on the team's security posture.

**GREEN:**

> The university's IT team moved staff sign-in to a shared identity provider last year, part of a broader shift toward federated trust.

**Expected finding:** `[13 inflated significance] "stands as a watershed," "reflects a broader shift," "left an indelible mark" — a routine change of sign-in provider is framed as a turning point with a legacy. Cut the watershed and the indelible mark; they state no fact. The RED does assert the broader shift toward federated trust, so keep the shift as a fact: the change is part of it.`

---

### 13 — Inflated significance (challenges and outlook section)

**RED:**

> ## Challenges and Outlook
>
> No transformation of this scale is without obstacles, and the programme has encountered its share. Nevertheless, buoyed by executive sponsorship, the team remains well placed to navigate what lies ahead.

**GREEN:**

> The programme has run into its share of obstacles. The team has executive sponsorship.
>
> _(Nothing else in the section survives: it names no obstacle and states no plan.)_

**Expected finding:** `[13 inflated significance] A stock "Challenges and Outlook" section. "No transformation of this scale is without obstacles" names no obstacle, and "remains well placed to navigate what lies ahead" states no plan. Keep the two facts — the programme has met its share of obstacles, and the team has executive sponsorship — and cut the rest. Do not supply obstacles the source does not give. The title-case heading is also §20; because §13 cuts the stock section, the heading goes with it rather than being recased, and the two facts stand without it.`

---

### 13 — Inflated significance (send-off paragraph)

**RED:**

> This is a step in the right direction for the whole portfolio. With continued investment and the right partners, the platform is well positioned to shape the next chapter of the organisation's digital journey.

**GREEN:**

> _(Cut the paragraph. End on the last concrete fact or action item.)_

**Expected finding:** `[13 inflated significance] "a step in the right direction," "well positioned to shape the next chapter," "digital journey" — a send-off paragraph that promises a future without stating a plan. Remove it and end on the last substantive sentence.`

---

### 14 — Vague connection or association

**RED:**

> The vendor is associated with two national infrastructure programmes, and built the baggage handling system for both. Its founder was connected to the original standards body, which he chaired from 2009 to 2014.

**GREEN:**

> The vendor built the baggage handling system for two national infrastructure programmes. Its founder chaired the original standards body from 2009 to 2014.

**Expected finding:** `[14 vague connection] "is associated with," "was connected to" — the text asserts a relationship without naming it, though both sentences supply the detail. Name the relationship the source gives. If the source does not say, keep the vague wording rather than inventing a role.`

---

### 15 — Shallow -ing riders

**RED:**

> The program's three-year timeline reflects the organization's commitment to sustainable growth, fostering deeper community relationships while ensuring long-term impact across all stakeholder groups.

**GREEN:**

> The program runs for three years.

**Expected finding:** `[15 shallow -ing riders] "fostering," "ensuring" — participial phrases riding on the main clause that add no factual content. They make a timeline sound meaningful without stating what will happen. Keep the fact (the three-year timeline) and cut the riders; the RED supports neither. The "reflects the organization's commitment" clause is the same inflation and goes with them.`

---

### 16 — Sales language

**RED:**

> The winery, nestled in the breathtaking Okanagan Valley, boasts stunning views, a vibrant atmosphere, and a rich heritage of winemaking excellence. It is a must-visit destination for connoisseurs and casual visitors alike.

**GREEN:**

> The winery is in the Okanagan Valley.

**Expected finding:** `[16 sales language] "nestled," "breathtaking," "boasts," "stunning," "vibrant," "rich heritage," "must-visit" — every sentence reads like promotional copy. Strip evaluative adjectives; state what exists.`

---

### 17 — Borrowed authority (unnamed authority)

**RED:**

> Experts believe the revised standard will cut assurance effort substantially. Industry reports suggest most operators are already moving to adopt it.

**GREEN:**

> _(Cut both sentences. The RED names no source for either claim.)_

**Expected finding:** `[17 borrowed authority] "Experts believe," "Industry reports suggest" — unnamed authorities prop up two claims. Name the expert or report and what it said, or cut the claim. Never invent a source.`

---

### 17 — Borrowed authority (prestige list)

**RED:**

> The practice has been profiled in three trade publications and has received independent coverage across the sector press. Its lead architect speaks regularly at industry events and has built a following of more than 40,000 on professional networks.

**GREEN:**

> The practice's lead architect speaks regularly at industry events.

**Expected finding:** `[17 borrowed authority] "profiled in three trade publications," "independent coverage across the sector press," "a following of more than 40,000" — unnamed outlets and a follower count stand in for a credential. Name the outlet and what it said, or cut the claim.`

---

### 17 — Borrowed authority (source named in a footnote)

**RED:**

> Industry reports put the platform's share of the point-of-sale software market at roughly 25%.[^1] Experts argue it will keep growing.
>
> [^1]: Harbour Analytics, Retail Systems Survey, March 2026.

**GREEN:**

> Harbour Analytics' Retail Systems Survey of March 2026 puts the platform's share of the point-of-sale software market at roughly 25%.[^1]
>
> [^1]: Harbour Analytics, Retail Systems Survey, March 2026.

**Expected finding:** `[17 borrowed authority] "Industry reports" stands in for the source, but footnote [^1] names it, which counts as naming the source: name the survey in the sentence and keep the roughly 25% figure. "Experts argue it will keep growing" names no one; cut it. Never invent a source.`

---

### 18 — Avoiding is, are, and has

**RED:**

> Every release goes through the staging cluster, which serves as the only environment with masked production data. Jobs land in one of the two batch queues the scheduler offers, on nodes that each feature 64 GB of memory.

**GREEN:**

> Every release goes through the staging cluster, which is the only environment with masked production data. Jobs land in one of the scheduler's two batch queues, on nodes that each have 64 GB of memory.

**Expected finding:** `[18 avoiding is/are/has] "serves as," "offers," "features" stand in for the simple verbs, and each can take "is" or "has" without changing the meaning. Restore "is" and "has," or drop the verb where a possessive says it ("the scheduler's two batch queues"). Keep a verb such as "represents" or "maintains" where it carries meaning "is" or "has" would lose.`

---

## D. Formatting by rule

### 19 — Bold as decoration

**RED:**

> The rollout covers **Identity and Access Management (IAM)**, **Network Access Control (NAC)**, and **Public Key Infrastructure (PKI)**, with **Segmentation** handled in a later phase.

**GREEN:**

> The rollout covers Identity and Access Management (IAM), Network Access Control (NAC), and Public Key Infrastructure (PKI), with Segmentation handled in a later phase.

**Expected finding:** `[19 bold as decoration] Four terms bolded without a reason — three wrap acronym definitions and one is a plain term; none is critical information. Remove the bold formatting and keep each parenthetical acronym with its expansion.`

---

### 19 — Bold as decoration (labeled list)

**RED:**

> Key improvements include:
>
> - **Intake:** Requests now route automatically to the owning team.
> - **Review:** Two approvers are required for changes above £50k.
> - **Audit:** Every decision is written to an immutable log.

**GREEN:**

> The main improvements include automatic routing of requests to the owning team, two approvers required for changes above £50k, and an immutable log of every decision.

**Expected finding:** `[19 bold as decoration] Every list item carries a bold label and a colon. The labels carry no information of their own. Turn the list into prose, or drop the bold labels. "Key" in "Key improvements" is §12 *weak alone*; the §19 labels supply the company, so it becomes "main".`

---

### 20 — Decorative headings

**RED:**

> ## Quarterly Review Of Vendor Performance And Contract Compliance

**GREEN:**

> ## Quarterly review of vendor performance and contract compliance

**Expected finding:** `[20 decorative headings] The heading capitalizes every main word. Use sentence case: capitalize only the first word and proper nouns.`

---

### 20 — Decorative headings (emoji and arrow decoration)

**RED:**

> 📌 **Discovery:** Site surveys complete at nine of twelve pumping stations.
> ⚡ **Build:** Cabling starts in the first week of March.
> → **Handover:** Operations takes ownership at go-live.

**GREEN:**

> Site surveys complete at nine of twelve pumping stations. Cabling starts in the first week of March, and operations takes ownership at go-live.

**Expected finding:** `[20 decorative headings] Emojis and an arrow used as decorative list-item prefixes. Remove the decoration. The bold labels on each item are also pattern 19.`

---

## E. Leftovers from the chat and the draft

### 22 — Chatbot residue

**RED:**

> Certainly! Below you'll find a summary of the audit results. Processing times exceed the target by 60%, and three of five districts have not completed role mapping. Would you like me to break any of these down further?

**GREEN:**

> The audit found that processing times exceed the target by 60%, and three of five districts have not completed role mapping.

**Expected finding:** `[22 chatbot residue] "Certainly!," "Below you'll find," "Would you like me to break any of these down further?" — a chatbot greeting and closing offer wrapped around real content. Remove the wrapper and keep the content.`

---

### 22 — Chatbot residue (praise before the answer)

**RED:**

> Great question! You're absolutely right that this is a complex topic. That's an excellent point about the funding constraints: they account for roughly half the delay.

**GREEN:**

> The funding constraints account for roughly half the delay.

**Expected finding:** `[22 chatbot residue] "Great question!," "You're absolutely right," "That's an excellent point" — chatbot praise aimed at the questioner before any answer. Cut the agreement and state the answer. "this is a complex topic" is part of the agreement, carries no claim, and goes with it.`

---

### 23 — Knowledge-limit disclaimers and guesses

**RED:**

> As of my last update, the contract value had not been disclosed, though it was likely in the region of £20m given comparable awards. The delivery date is unclear, but the programme presumably ran to the original schedule.

**GREEN:**

> The contract value and the delivery date are unknown.

**Expected finding:** `[23 knowledge-limit disclaimers] "As of my last update," "likely in the region of," "presumably ran to the original schedule" — a training-cutoff disclaimer, one invented figure, and one unsupported schedule guess. Say plainly what is unknown and remove both guesses.`

---

## F. Must stay unflagged

Each input below contains no tell that clears its gate, or only text the skill must leave alone. The skill returns it unchanged and says so.

### N1 — Clean note with one dash and a numeric range

**RED:**

> Facilities swapped out the door readers at the hospital's staff entrance in April. The replacements read both barcode and NFC cards, so staff with older ID cards can still get through. Throughput over the first two weeks is 40–45 people a minute per door. The key performance indicator in the facilities plan is queue time, and it has stayed under four minutes at every shift change — the busiest was the night shift on 19 April.

**GREEN:**

> Facilities swapped out the door readers at the hospital's staff entrance in April. The replacements read both barcode and NFC cards, so staff with older ID cards can still get through. Throughput over the first two weeks is 40–45 people a minute per door. The key performance indicator in the facilities plan is queue time, and it has stayed under four minutes at every shift change — the busiest was the night shift on 19 April.

**Expected finding:** `(No finding — return the text unchanged and say no pattern clears its gate. The single em dash is §8 *weak alone* with no company. The en dash in "40–45" is a range, not a connector. "key performance indicator" is a fixed term, not the §12 adjective.)`

---

### N2 — Status email with a dated figure, a table, and a real request

**RED:**

> Hi Priya,
>
> As of 12 August 2026, 9 of 11 loading docks are scanning live parcels, and the other two go live on 26 August.
>
> | Dock | Status | Next step |
> |---|---|---|
> | North yard | Live | None. |
> | Cold store | Delayed | Scanner swap. Awaiting spares. |
> | South yard | Live | Label reorder. |
>
> Let me know whether the spares can ship to the cold store directly; if they can, I will book the engineer for the next morning.
>
> Thanks,
> Tom

**GREEN:**

> Hi Priya,
>
> As of 12 August 2026, 9 of 11 loading docks are scanning live parcels, and the other two go live on 26 August.
>
> | Dock | Status | Next step |
> |---|---|---|
> | North yard | Live | None. |
> | Cold store | Delayed | Scanner swap. Awaiting spares. |
> | South yard | Live | Label reorder. |
>
> Let me know whether the spares can ship to the cold store directly; if they can, I will book the engineer for the next morning.
>
> Thanks,
> Tom

**Expected finding:** `(No finding — return the text unchanged. "As of 12 August 2026" dates a status figure, not a knowledge cutoff (§23). The table is data: its fragment cells are the format, not §2. "Let me know" asks the email's real recipient to act, not the model's user (§22). The salutation and sign-off predate chatbots.)`

---

### N3 — Requirements with normative keywords and a warning

**RED:**

> ## Session requirements
>
> The client MUST NOT write session tokens to local storage. The server SHOULD expire idle sessions after 15 minutes.
>
> The supplier shall provide a named security contact. The supplier shall report incidents within 24 hours. The supplier shall retain access logs for 12 months.
>
> WARNING: Disconnect the mains supply before you open the rack. Fuses are replaced only by a qualified electrician.

**GREEN:**

> ## Session requirements
>
> The client MUST NOT write session tokens to local storage. The server SHOULD expire idle sessions after 15 minutes.
>
> The supplier shall provide a named security contact. The supplier shall report incidents within 24 hours. The supplier shall retain access logs for 12 months.
>
> WARNING: Disconnect the mains supply before you open the rack. Fuses are replaced only by a qualified electrician.

**Expected finding:** `(No finding — return the text unchanged. "MUST NOT," "SHOULD," and "WARNING" are normative keywords and a callout label, not §2 capitals. The three "The supplier shall" sentences are separate requirements, not §7 openings. The one passive names its actor, so it is not a §11 tell.)`

---

### N4 — Literal senses and meaning-bearing verbs

**RED:**

> The architecture of the payments service has two layers: an API gateway and a ledger. Each line in the ledger represents one settled transaction, and the finance systems team maintains the reconciliation scripts. Monthly reporting uses the four key performance indicators set out in the service charter, and any failed settlement is highlighted in amber on the operations console. The language of the processing agreement caps fees at 0.4% per transaction.

**GREEN:**

> The architecture of the payments service has two layers: an API gateway and a ledger. Each line in the ledger represents one settled transaction, and the finance systems team maintains the reconciliation scripts. Monthly reporting uses the four key performance indicators set out in the service charter, and any failed settlement is highlighted in amber on the operations console. The language of the processing agreement caps fees at 0.4% per transaction.

**Expected finding:** `(No finding — return the text unchanged. "The architecture of" and "The language of" are literal, not §3 sayings. "represents" and "maintains" carry meaning that "is" and "has" would lose (§18). "key performance indicators" is a fixed term and "highlighted in amber" is literal (§12). With no company, the passive "is highlighted" is §11 *weak alone*.)`

---

### N5 — Direct quotation and inline code in pasted text

**RED:**

> The upgrade to version 4.2 finished on Sunday night. Operators should set `max-retry-count: 5` in `config/long-term-store.yaml` before restarting the collector. In the release note, the platform lead wrote: "We cut it. We tested it. We shipped it — two days early. No drama." Rollback instructions are on the wiki page for the collector.

**GREEN:**

> The upgrade to version 4.2 finished on Sunday night. Operators should set `max-retry-count: 5` in `config/long-term-store.yaml` before restarting the collector. In the release note, the platform lead wrote: "We cut it. We tested it. We shipped it — two days early. No drama." Rollback instructions are on the wiki page for the collector.

**Expected finding:** `(No finding — return the text unchanged. The fragments, repeated openings, and dash sit inside a direct quotation, which stays verbatim in every mode. The hyphenated pair "long-term" sits inside inline code, which stays unchanged in pasted mode as well as file mode. Outside those, nothing clears a gate.)`

---

## Tests dropped at the v3.0.0 upgrade

Two tests were removed because v3.0.0 has no rule they map to. They are recorded here so the lost coverage is visible rather than silent.

| Old test                     | Was                                                                           | Status in v3.0.0                                                                                  |
| ---------------------------- | ----------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------- |
| §12 False from X to Y ranges | Flagged "spans everything from X to Y" pairs that are not real ranges         | No equivalent pattern. Dropped.                                                                   |
| §23 Filler phrases           | Flagged "in order to," "it is important to note that," "due to the fact that" | No equivalent pattern; filler phrases belong to `no-ai-slop`. Dropped.                           |

## Verification Log

**Verified 2026-10-22.** Result: **33/33 passed.** Graded by an Opus agent reading `SKILL.md` and `TESTS.md`, with no edit to either file afterwards. `python3 scripts/validate-package.py` run in the same pass: `Humanizer package v3.0.0 is valid`, exit 0. Every `SKILL.md` worked example was also checked against the skill's own rules (no added facts, no lost claims) and none breaks them. For N1 to N5, "RED flags" means the skill correctly stays quiet and "GREEN clean" means the unchanged text is what the skill would return.

Produced against `TESTS.md` body sha256 `b389efa1a4bd58aa` and `SKILL.md` sha256 `881d1697e5f7d353`. The body hash covers everything above this heading, so it survives this table being written. Recompute both before trusting the rows: any later edit invalidates them, and a log that certifies rather than records hides the defects it exists to surface.

| Test | RED flags | GREEN clean | Pass |
|------|-----------|-------------|------|
| 1 — Not X but Y | ✓ | ✓ | PASS |
| 2 — One-line closers and dramatic fragments | ✓ | ✓ | PASS |
| 3 — Sayings that sound deep | ✓ | ✓ | PASS |
| 4 — Staged run-up before the point | ✓ | ✓ | PASS |
| 4 — Staged run-up before the point (staged candor) | ✓ | ✓ | PASS |
| 6 — Forced triads | ✓ | ✓ | PASS |
| 7 — Repeated sentence openings | ✓ | ✓ | PASS |
| 8 — Dashes as the universal connector | ✓ | ✓ | PASS |
| 9 — Stacked qualifiers | ✓ | ✓ | PASS |
| 11 — Passive voice and missing subjects | ✓ | ✓ | PASS |
| 12 — Overused AI words | ✓ | ✓ | PASS |
| 13 — Inflated significance | ✓ | ✓ | PASS |
| 13 — Inflated significance (challenges and outlook section) | ✓ | ✓ | PASS |
| 13 — Inflated significance (send-off paragraph) | ✓ | ✓ | PASS |
| 14 — Vague connection or association | ✓ | ✓ | PASS |
| 15 — Shallow -ing riders | ✓ | ✓ | PASS |
| 16 — Sales language | ✓ | ✓ | PASS |
| 17 — Borrowed authority (unnamed authority) | ✓ | ✓ | PASS |
| 17 — Borrowed authority (prestige list) | ✓ | ✓ | PASS |
| 17 — Borrowed authority (source named in a footnote) | ✓ | ✓ | PASS |
| 18 — Avoiding is, are, and has | ✓ | ✓ | PASS |
| 19 — Bold as decoration | ✓ | ✓ | PASS |
| 19 — Bold as decoration (labeled list) | ✓ | ✓ | PASS |
| 20 — Decorative headings | ✓ | ✓ | PASS |
| 20 — Decorative headings (emoji and arrow decoration) | ✓ | ✓ | PASS |
| 22 — Chatbot residue | ✓ | ✓ | PASS |
| 22 — Chatbot residue (praise before the answer) | ✓ | ✓ | PASS |
| 23 — Knowledge-limit disclaimers and guesses | ✓ | ✓ | PASS |
| N1 — Clean note with one dash and a numeric range | ✓ | ✓ | PASS |
| N2 — Status email with a dated figure, a table, and a real request | ✓ | ✓ | PASS |
| N3 — Requirements with normative keywords and a warning | ✓ | ✓ | PASS |
| N4 — Literal senses and meaning-bearing verbs | ✓ | ✓ | PASS |
| N5 — Direct quotation and inline code in pasted text | ✓ | ✓ | PASS |

Counts: 28 pattern tests and 5 must-stay-unflagged tests; 33 PASS, 0 PASS with discrepancy, 0 FAIL.

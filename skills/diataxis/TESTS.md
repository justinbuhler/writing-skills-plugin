# Diátaxis Skill: Red/Green Test Suite

Each test has:

- **RED:** text the skill should act on
- **GREEN:** the corrected text, which should pass
- **Expected finding:** what the skill should report for the RED

Tests 1 to 5 cover the four Diátaxis types and the seams between them, including a report's recommendation to a third party, which stays whole with its reasons, beside a policy, which is Reference. Tests 6 to 9 and 12 check the split-in-place rewrite: a new section, an existing section, no empty sections, verbatim text, and the link line for a lesson. Tests 10 and 11 check the review contract: a request not to change the text, and the priority list. Tests N1 to N9 must stay unflagged; their GREEN is the RED unchanged. N5 to N7 cover a limit that says "must", a summary and a Record under a rewrite request, and text that is already split. N8 and N9 cover an obligation on a named party in a section of rules, and a report's recommendation to a third party. 21 tests in all.

GREEN texts add no fact, name, number, date, or actor that is absent from their RED. The only new text in a GREEN is a section heading built from the RED's own words and a one-line link where a passage left.

Grading notes. Every RED has a context line saying what the user asked. A request to split, separate, or restructure runs Rewrite; anything else runs Review, the default. Heading wording in a GREEN or an Expected finding is illustrative: any heading the skill's naming rule allows passes. A `[needs: …]` already in a GREEN may or may not be listed again under Gaps; either is clean. Tags such as `[Split]` are test labels, not skill output.

---

## A. Types and seams

### 1. How-to with an Explanation seam

**RED:**

> Context: the user requests a Diátaxis review of this section.
>
> ## Reset a student's MFA
>
> 1. Open the student's record in the Entra admin center.
> 2. Select **Authentication methods** and choose **Require re-register MFA**.
>
> Authenticator replaced text-message codes after the 2024 pilot term, where SIM swaps let attackers take over two student accounts. Push approvals with number matching resist that attack, and every campus building has reliable data coverage.
>
> 3. Tell the student to sign in again and register Authenticator.

**GREEN:**

> ## Reset a student's MFA
>
> 1. Open the student's record in the Entra admin center.
> 2. Select **Authentication methods** and choose **Require re-register MFA**.
>
> Why: see "About Authenticator".
>
> 3. Tell the student to sign in again and register Authenticator.
>
> ## About Authenticator
>
> Authenticator replaced text-message codes after the 2024 pilot term, where SIM swaps let attackers take over two student accounts. Push approvals with number matching resist that attack, and every campus building has reliable data coverage.

**Expected finding:** `[Review] type map: "Reset a student's MFA" is How-to, with an Explanation seam. [Seam] "Authenticator replaced text-message codes … reliable data coverage." is Explanation inside How-to → move it to a new section titled from its own words, such as "About Authenticator", and leave "Why: see …" where it was. The section is not rewritten in the response.`

---

### 2. Tutorial with a Reference seam

**RED:**

> Context: the user requests a Diátaxis review of this section.
>
> ## Your first goods-in scan
>
> In this lesson you will receive two practice parcels at the training scanner. Start by tapping **Begin session** and scanning the first practice label. The screen turns green and shows the parcel's order number.
>
> | Code | Meaning |
> |---|---|
> | E01 | Label not found |
> | E02 | Order closed |
> | E03 | Bay not assigned |
> | E04 | Scanner offline |
>
> Now scan the second practice label. You will see code E02; that is expected, because this label belongs to a closed order. Tap **Done** to finish the lesson.

**GREEN:**

> ## Your first goods-in scan
>
> In this lesson you will receive two practice parcels at the training scanner. Start by tapping **Begin session** and scanning the first practice label. The screen turns green and shows the parcel's order number.
>
> Details: see "Scan code reference".
>
> Now scan the second practice label. You will see code E02; that is expected, because this label belongs to a closed order. Tap **Done** to finish the lesson.
>
> ## Scan code reference
>
> | Code | Meaning |
> |---|---|
> | E01 | Label not found |
> | E02 | Order closed |
> | E03 | Bay not assigned |
> | E04 | Scanner offline |

**Expected finding:** `[Review] type map: "Your first goods-in scan" is Tutorial, with a Reference seam. [Seam] the code table is Reference inside Tutorial → move it to a new section such as "Scan code reference" and leave "Details: see …" where it was. The sentence about code E02 stays in the lesson: its reason is part of a step, not a passage of its own.`

---

### 3. Reference with a How-to seam

**RED:**

> Context: the user requests a Diátaxis review of this section.
>
> ## Tier entitlements
>
> | Tier | Identity | Devices |
> |---|---|---|
> | A1 | None | None |
> | A2 | Guest account | Personal phone |
> | A3 | Member account | Issued laptop |
>
> Ward managers should request A3 laptops at least ten days before the agency worker's first shift. To request one, open a ServiceNow catalog item, choose **Agency laptop**, and enter the role code.

**GREEN:**

> ## Tier entitlements
>
> | Tier | Identity | Devices |
> |---|---|---|
> | A1 | None | None |
> | A2 | Guest account | Personal phone |
> | A3 | Member account | Issued laptop |
>
> Steps: see "How to request an A3 laptop".
>
> ## How to request an A3 laptop
>
> Ward managers should request A3 laptops at least ten days before the agency worker's first shift. To request one, open a ServiceNow catalog item, choose **Agency laptop**, and enter the role code.

**Expected finding:** `[Review] type map: "Tier entitlements" is Reference, with a How-to seam. [Seam] "Ward managers should request A3 laptops … enter the role code." is How-to inside Reference (advice and steps in a table section) → move both sentences to a new section such as "How to request an A3 laptop" and leave "Steps: see …" where they were.`

---

### 4. Explanation with a How-to seam

**RED:**

> Context: the user requests a Diátaxis review of this section.
>
> ## Why Tier A2 uses guest accounts
>
> Guest accounts give A2 agency workers the rostering app without a paid licence, and they lapse when the sponsor removes them. The trade-off is that guests cannot use Teams Phone or shared mailboxes.
>
> To invite a guest, sign in to the Entra admin center, select **Users** > **Invite external user**, and enter the agency worker's personal email address.

**GREEN:**

> ## Why Tier A2 uses guest accounts
>
> Guest accounts give A2 agency workers the rostering app without a paid licence, and they lapse when the sponsor removes them. The trade-off is that guests cannot use Teams Phone or shared mailboxes.
>
> Steps: see "How to invite a guest".
>
> ## How to invite a guest
>
> To invite a guest, sign in to the Entra admin center, select **Users** > **Invite external user**, and enter the agency worker's personal email address.

**Expected finding:** `[Review] type map: "Why Tier A2 uses guest accounts" is Explanation, with a How-to seam. [Seam] "To invite a guest, … personal email address." is How-to inside Explanation → move it to a new section such as "How to invite a guest" and leave "Steps: see …" where it was. The trade-off sentence stays: discussing trade-offs is what Explanation is for.`

---

### 5. A report's recommendation to a third party stays whole; a policy is Reference

**RED:**

> Context: the user requests a Diátaxis review of these two sections of a report.
>
> ## Policies
>
> P3. IT allocates no licence until HR confirms the role assignment.
> P6. Only the IT Service Manager assigns F3 licences.
>
> ## Recommendation
>
> HR should adopt the three-tier agency staff model before the winter intake. At the sister hospital, agency workers were provisioned in one bulk upload months before their roles were known; a third of the accounts were never used, and the licence budget ran out in the final quarter.

**GREEN:**

> ## Policies
>
> P3. IT allocates no licence until HR confirms the role assignment.
> P6. Only the IT Service Manager assigns F3 licences.
>
> ## Recommendation
>
> HR should adopt the three-tier agency staff model before the winter intake. At the sister hospital, agency workers were provisioned in one bulk upload months before their roles were known; a third of the accounts were never used, and the licence budget ran out in the final quarter.

**Expected finding:** `[Review] type map: "Policies" is Reference; "Recommendation" is Explanation. Neither section has a seam, so nothing moves. The opening sentence of "Recommendation" recommends an action to a third party, HR, and the next sentence gives its reasons, so both are part of the report's argument: the section is not typed How-to, although its heading and its "should" read like advice, and "At the sister hospital, … the final quarter." is not an Explanation seam. No "About …" section and no "Why: see …" line is proposed. The rules a reader looks up are Reference.`

---

## B. Split in place

### 6. Split into a new section

**RED:**

> Context: the user asks, "Split this by Diátaxis type."
>
> ## Offboard an agency worker
>
> 1. Remove the agency worker from the A3 group in Entra ID.
> 2. Wait for the F3 licence to drop, then block sign-in.
>
> Removing the group drops the licence because licences are assigned to the group, not the person. This is group-based licensing, and it means nobody has to remember a manual step.
>
> 3. Collect the laptop at the agency worker's last shift.

**GREEN:**

> ## Offboard an agency worker
>
> 1. Remove the agency worker from the A3 group in Entra ID.
> 2. Wait for the F3 licence to drop, then block sign-in.
>
> Why: see "About group-based licensing".
>
> 3. Collect the laptop at the agency worker's last shift.
>
> ## About group-based licensing
>
> Removing the group drops the licence because licences are assigned to the group, not the person. This is group-based licensing, and it means nobody has to remember a manual step.

**Expected finding:** `[Split] the two Explanation sentences move word for word to a new section placed right after "Offboard an agency worker" at the same heading level, titled from their own words, such as "About group-based licensing"; "Why: see …" stays where they were; the steps keep their wording, order, and numbers; no other sentence is added, reworded, or removed. The response lists the move.`

---

### 7. Split into an existing section

**RED:**

> Context: the user asks, "Split this by Diátaxis type."
>
> ## Request a shared mailbox
>
> 1. Open the ServiceNow catalog and choose **Shared mailbox**.
> 2. Name the mailbox after the site and function, such as NORTH-Pharmacy.
>
> Shared mailboxes need no licence of their own, which is why wards use them instead of extra accounts.
>
> ## About mailboxes and licences
>
> The hospital avoids creating accounts only to get a mailbox, because each member account with a mailbox uses an F3 licence and Finance caps the number of licences each quarter.

**GREEN:**

> ## Request a shared mailbox
>
> 1. Open the ServiceNow catalog and choose **Shared mailbox**.
> 2. Name the mailbox after the site and function, such as NORTH-Pharmacy.
>
> Why: see "About mailboxes and licences".
>
> ## About mailboxes and licences
>
> The hospital avoids creating accounts only to get a mailbox, because each member account with a mailbox uses an F3 licence and Finance caps the number of licences each quarter.
>
> Shared mailboxes need no licence of their own, which is why wards use them instead of extra accounts.

**Expected finding:** `[Split] the sentence under the steps states a fact with its result ("which is why"), so it is Explanation, not Reference. The document already has an Explanation section on the same topic, so the sentence moves word for word to the end of "About mailboxes and licences" and no new section is created; "Why: see "About mailboxes and licences"." stays where it was.`

---

### 8. No empty sections, even when asked

**RED:**

> Context: the user asks, "Restructure this page with Diátaxis so it has all four types."
>
> ## Receive a delivery
>
> 1. Scan the delivery label.
> 2. If the screen shows E03, send the driver to the goods-in office.
> 3. Otherwise, sign for the delivery.

**GREEN:**

> ## Receive a delivery
>
> 1. Scan the delivery label.
> 2. If the screen shows E03, send the driver to the goods-in office.
> 3. Otherwise, sign for the delivery.

**Expected finding:** `[Split] nothing to move: the page is one How-to. The page comes back unchanged, and the response says why the other three types are not added: a section of a type exists only when there is content of that type to put in it. No empty, placeholder, or [needs: …] section is created for Tutorial, Reference, or Explanation, and no new content is written to fill one.`

---

### 9. Moved text stays verbatim, markers included

**RED:**

> Context: the user asks, "Split this by Diátaxis type."
>
> ## Approve a device exception
>
> 1. Open the exception in ServiceNow and read the `justification` field.
> 2. Approve it if the position's tier allows the device; otherwise select **Refer to Change Board**.
>
> Exceptions exist because tiers describe typical roles, not every role. When Pharmacy needed tablets that no tier provided, the `justification` field was added so reviewers could see why. [needs: owner for exception reviews]
>
> 3. Record the outcome in the exception log.

**GREEN:**

> ## Approve a device exception
>
> 1. Open the exception in ServiceNow and read the `justification` field.
> 2. Approve it if the position's tier allows the device; otherwise select **Refer to Change Board**.
>
> Why: see "About device exceptions".
>
> 3. Record the outcome in the exception log.
>
> ## About device exceptions
>
> Exceptions exist because tiers describe typical roles, not every role. When Pharmacy needed tablets that no tier provided, the `justification` field was added so reviewers could see why. [needs: owner for exception reviews]

**Expected finding:** `[Split] the Explanation passage moves word for word, keeping the field name `justification` in code format, the passive "was added" as written, and the existing "[needs: owner for exception reviews]" at the end of the moved text; the UI label **Refer to Change Board** in step 2 stays as written; the new heading and the link line are the only added text. Listing the existing marker under Gaps is optional.`

---

### 12. A lesson inside a Reference section gets a Lesson link

**RED:**

> Context: the user asks, "Separate this page by Diátaxis type."
>
> ## Label printer settings
>
> | Setting | Value |
> |---|---|
> | Roll width | 62 mm |
> | Print density | 3 |
> | Cut | After every label |
>
> This exercise teaches you the printer's two buttons before your first shift: you will print one sample label. Press **Feed** until the roll edge shows at the slot. Then press **Test**. A label that reads SAMPLE comes out.

**GREEN:**

> ## Label printer settings
>
> | Setting | Value |
> |---|---|
> | Roll width | 62 mm |
> | Print density | 3 |
> | Cut | After every label |
>
> Lesson: see "Lesson: print one sample label".
>
> ## Lesson: print one sample label
>
> This exercise teaches you the printer's two buttons before your first shift: you will print one sample label. Press **Feed** until the roll edge shows at the slot. Then press **Test**. A label that reads SAMPLE comes out.

**Expected finding:** `[Split] the four Tutorial sentences ("This exercise teaches you … comes out.") move word for word to a new section placed right after "Label printer settings" at the same heading level, titled "Lesson: …" from their own words, such as "Lesson: print one sample label". The line left under the table is "Lesson: see "<that heading>"."; a "Steps: see", "Details: see", or "Why: see" line there fails. The table keeps its rows and wording. The response lists the move.`

---

## C. Review contract

### 10. A request not to change the text keeps it a review

**RED:**

> Context: the user asks, "Split this by Diátaxis type, but show me what would move first. Don't change anything yet."
>
> ## Return a loan laptop
>
> 1. Sign out of every app and shut the laptop down.
> 2. Hand it to the library IT desk with its charger.
>
> Laptops are wiped and reissued within the same term, so a missing charger delays the next student.

**GREEN:**

> ## Return a loan laptop
>
> 1. Sign out of every app and shut the laptop down.
> 2. Hand it to the library IT desk with its charger.
>
> Why: see "About laptop reissue".
>
> ## About laptop reissue
>
> Laptops are wiped and reissued within the same term, so a missing charger delays the next student.

**Expected finding:** `[Review] "Don't change anything yet" overrides "Split this", so the response is a review and returns no rewritten section. Type map: "Return a loan laptop" is How-to, with an Explanation seam. [Seam] "Laptops are wiped … delays the next student." is Explanation inside How-to → move it to a new section titled from its own words, such as "About laptop reissue", and leave "Why: see …" where it was.`

---

### 11. The priority list puts task seams first

**RED:**

> Context: the user requests a Diátaxis audit of this page.
>
> ## Kiosk models
>
> | Model | Screen |
> |---|---|
> | K10 | 10 inch |
> | K15 | 15 inch |
>
> Order the K15 for any branch with more than 30 visitors per hour.
>
> ## Why kiosks run in single-app mode
>
> Single-app mode stops visitors opening a browser on a shared device. To turn on single-app mode, open the kiosk profile in Intune and set **Kiosk mode** to **Single app**.
>
> ## Restart a frozen kiosk
>
> 1. Hold the power button for ten seconds.
> 2. Wait for the checkout screen.
>
> Kiosks freeze when the branch network drops for more than a minute, because the app waits for a token refresh that never arrives.
>
> 3. If the screen stays blank, call the IT service desk.
>
> ## Lesson: check out your first book
>
> In this lesson you will check out one practice book. Tap **Begin session**, then scan the practice library card.
>
> | Light | Meaning |
> |---|---|
> | Green | Checked out |
> | Red | Card blocked |
>
> The light turns green. You have checked out your first book.

**GREEN:**

> ## Kiosk models
>
> | Model | Screen |
> |---|---|
> | K10 | 10 inch |
> | K15 | 15 inch |
>
> Steps: see "How to order kiosks".
>
> ## How to order kiosks
>
> Order the K15 for any branch with more than 30 visitors per hour.
>
> ## Why kiosks run in single-app mode
>
> Single-app mode stops visitors opening a browser on a shared device.
>
> Steps: see "How to turn on single-app mode".
>
> ## How to turn on single-app mode
>
> To turn on single-app mode, open the kiosk profile in Intune and set **Kiosk mode** to **Single app**.
>
> ## Restart a frozen kiosk
>
> 1. Hold the power button for ten seconds.
> 2. Wait for the checkout screen.
>
> Why: see "About kiosk freezes".
>
> 3. If the screen stays blank, call the IT service desk.
>
> ## About kiosk freezes
>
> Kiosks freeze when the branch network drops for more than a minute, because the app waits for a token refresh that never arrives.
>
> ## Lesson: check out your first book
>
> In this lesson you will check out one practice book. Tap **Begin session**, then scan the practice library card.
>
> Details: see "Kiosk light reference".
>
> The light turns green. You have checked out your first book.
>
> ## Kiosk light reference
>
> | Light | Meaning |
> |---|---|
> | Green | Checked out |
> | Red | Card blocked |

**Expected finding:** `[Review] four seams, each with its own [Seam] line: How-to in "Kiosk models" (the ordering advice), How-to in "Why kiosks run in single-app mode" (the Intune steps), Explanation in "Restart a frozen kiosk" (why kiosks freeze), and Reference in "Lesson: check out your first book" (the light table). The Priority list has exactly three splits in this order: the Explanation in "Restart a frozen kiosk", then the table in the lesson, because both interrupt a reader in the middle of a task; then the advice in "Kiosk models", the first of the rest in document order. The single-app seam is reported but not in the Priority list. Nothing is rewritten.`

---

## D. Must stay unflagged

### N1. A Record stays whole

**RED:**

> Context: the user requests a Diátaxis review of this section.
>
> ## Decision register
>
> | ID | Decision | Rationale | Approved |
> |---|---|---|---|
> | D5 | A2 agency workers use guest accounts | Avoids a paid licence for short-term users | HR, 12 March 2026 |
> | D13 | No loaner phones for MFA | Budget and supply constraints | Change Board, 2 April 2026 |

**GREEN:**

> ## Decision register
>
> | ID | Decision | Rationale | Approved |
> |---|---|---|---|
> | D5 | A2 agency workers use guest accounts | Avoids a paid licence for short-term users | HR, 12 March 2026 |
> | D13 | No loaner phones for MFA | Budget and supply constraints | Change Board, 2 April 2026 |

**Expected finding:** `(No seam: "Decision register" is a Record, which is not a Diátaxis type and is never split. The Rationale column is part of each decision, not an Explanation seam.)`

---

### N2. An executive summary stays put

**RED:**

> Context: the user requests a Diátaxis review of the opening of a recommendations report.
>
> ## Executive summary
>
> HR should adopt a three-tier agency staff model before the winter intake. Tiering by role avoids paying for accounts that are never used, which drained the licence budget at the sister hospital. IT can build the model in six weeks once roles are confirmed.

**GREEN:**

> ## Executive summary
>
> HR should adopt a three-tier agency staff model before the winter intake. Tiering by role avoids paying for accounts that are never used, which drained the licence budget at the sister hospital. IT can build the model in six weeks once roles are confirmed.

**Expected finding:** `(No seam: an executive summary keeps its answer and its reasons together, so nothing in it moves, even though the second sentence explains. The type map marks it Explanation from its opening sentence, a recommendation to a third party in a report stated with its reasons, and as a summary that stays put.)`

---

### N3. A single-type section

**RED:**

> Context: the user requests a Diátaxis review of this section.
>
> ## Key terms
>
> **Guest account:** an Entra ID account for a user from outside the tenant.
> **Member account:** an Entra ID account created in the hospital's tenant.
> **TAP:** Temporary Access Pass, a time-limited passcode for first sign-in.

**GREEN:**

> ## Key terms
>
> **Guest account:** an Entra ID account for a user from outside the tenant.
> **Member account:** an Entra ID account created in the hospital's tenant.
> **TAP:** Temporary Access Pass, a time-limited passcode for first sign-in.

**Expected finding:** `(No seam: "Key terms" is Reference throughout. The response says so and suggests no new section for another type.)`

---

### N4. A reason inside a step

**RED:**

> Context: the user requests a Diátaxis review of this section.
>
> ## Issue a Temporary Access Pass
>
> 1. In the Entra admin center, open the agency worker's record and select **Add authentication method**.
> 2. Choose **Temporary Access Pass** and set it to expire after one hour, because a longer pass could be reused if the badge is lost.
> 3. Read the pass to the agency worker in person.

**GREEN:**

> ## Issue a Temporary Access Pass
>
> 1. In the Entra admin center, open the agency worker's record and select **Add authentication method**.
> 2. Choose **Temporary Access Pass** and set it to expire after one hour, because a longer pass could be reused if the badge is lost.
> 3. Read the pass to the agency worker in person.

**Expected finding:** `(No seam: the "because" clause in step 2 is part of a step, not a passage of its own. A seam is at least one whole sentence, list, or table, so the section is How-to throughout.)`

---

### N5. A limit that says "must" stays in its Reference section

**RED:**

> Context: the user asks which Diátaxis type this section is.
>
> ## Delivery driver hours
>
> | Shift | Longest time at the wheel |
> |---|---|
> | Day | 9 hours |
> | Night | 7 hours |
>
> A driver must take a 45-minute break after 4.5 hours at the wheel. Dispatch must not roster a driver for more than six days in a row.

**GREEN:**

> ## Delivery driver hours
>
> | Shift | Longest time at the wheel |
> |---|---|
> | Day | 9 hours |
> | Night | 7 hours |
>
> A driver must take a 45-minute break after 4.5 hours at the wheel. Dispatch must not roster a driver for more than six days in a row.

**Expected finding:** `(No seam: "Delivery driver hours" is Reference throughout. The two "must" sentences are limits stated as facts that a reader looks up, so they are Reference, not How-to advice, and they stay under the table. No "How to …" section and no "Steps: see …" line is proposed.)`

---

### N6. A summary and a Record stay whole under a rewrite request

**RED:**

> Context: the user asks, "Separate this report extract by Diátaxis type."
>
> ## Conclusion
>
> The council should move depot Wi-Fi onboarding to certificates before the next financial year. Shared passwords leaked at two depots last year, and each leak forced a depot-wide reset.
>
> ## Change log
>
> **3 June 2026.** Guest Wi-Fi moved to its own VLAN. Guests could reach the print servers on the shared one.
>
> **17 June 2026.** Password rotation changed from 90 days to 30. An audit found three passwords older than a year.

**GREEN:**

> ## Conclusion
>
> The council should move depot Wi-Fi onboarding to certificates before the next financial year. Shared passwords leaked at two depots last year, and each leak forced a depot-wide reset.
>
> ## Change log
>
> **3 June 2026.** Guest Wi-Fi moved to its own VLAN. Guests could reach the print servers on the shared one.
>
> **17 June 2026.** Password rotation changed from 90 days to 30. An audit found three passwords older than a year.

**Expected finding:** `(Nothing moves, although the request is a rewrite. "Conclusion" is a summary: its type is Explanation from its opening sentence, a recommendation to a third party stated with its reason, it is marked as a summary that stays put, and its second sentence, the reason, stays with it. "Change log" is a Record: the reason sentence in each entry is part of the entry, not an Explanation seam. The response says no section has a seam, names each section's type, and returns the text unchanged, with no "About …" section and no link line.)`

---

### N7. Text that is already split comes back unchanged

**RED:**

> Context: the user asks, "Split this by Diátaxis type."
>
> ## Why badges expire each night
>
> Badges stop working at midnight so that a lost badge is useless the next day. The cost is a reprint queue every morning.
>
> Steps: see "How to reprint a badge".
>
> ## How to reprint a badge
>
> 1. Scan the visitor's QR code at the reception desk.
>
> Details: see "Badge stock reference".
>
> 2. Select **Reprint** and hand over the new badge.
>
> ## Badge stock reference
>
> | Stock | Used for |
> |---|---|
> | White | Visitors |
> | Blue | Contractors |

**GREEN:**

> ## Why badges expire each night
>
> Badges stop working at midnight so that a lost badge is useless the next day. The cost is a reprint queue every morning.
>
> Steps: see "How to reprint a badge".
>
> ## How to reprint a badge
>
> 1. Scan the visitor's QR code at the reception desk.
>
> Details: see "Badge stock reference".
>
> 2. Select **Reprint** and hand over the new badge.
>
> ## Badge stock reference
>
> | Stock | Used for |
> |---|---|
> | White | Visitors |
> | Blue | Contractors |

**Expected finding:** `(No seam: the page is already split. "Why badges expire each night" is Explanation, "How to reprint a badge" is How-to, and "Badge stock reference" is Reference. The lines "Steps: see "How to reprint a badge"." and "Details: see "Badge stock reference"." are link lines, not seams: neither is typed, moved, removed, or replaced by another link line, and the first is not a How-to seam although it tells the reader to see something. The text comes back unchanged.)`

---

### N8. An obligation on a named party stays in its rules section

**RED:**

> Context: the user requests a Diátaxis audit of this section.
>
> ## Licence rules
>
> - Each member account uses one F3 licence.
> - Finance sets the licence cap each quarter.
> - The IT Service Manager must now confirm the licence count with Finance and must report any shortfall to the Change Board this week.

**GREEN:**

> ## Licence rules
>
> - Each member account uses one F3 licence.
> - Finance sets the licence cap each quarter.
> - The IT Service Manager must now confirm the licence count with Finance and must report any shortfall to the Change Board this week.

**Expected finding:** `(No seam: "Licence rules" is Reference throughout. The third bullet places an obligation on a named party, the IT Service Manager, so it is a rule a reader looks up, not How-to advice, although "now" and "this week" make it read like a task. No "How to …" section and no "Steps: see …" line is proposed.)`

---

### N9. A report's recommendation to a third party stays with its reasons

**RED:**

> Context: the user asks, "Separate this section of a consulting report by Diátaxis type."
>
> ## 4.2 Badge printing capacity
>
> One badge printer per large site is too few, because nothing covers a failure. Last spring the printer failed at two sites, and reprints stopped for more than three hours each time. A second printer costs less than one lost morning of check-in. The Facilities lead should therefore approve a second printer for each large site, so that a failure no longer stops check-in.

**GREEN:**

> ## 4.2 Badge printing capacity
>
> One badge printer per large site is too few, because nothing covers a failure. Last spring the printer failed at two sites, and reprints stopped for more than three hours each time. A second printer costs less than one lost morning of check-in. The Facilities lead should therefore approve a second printer for each large site, so that a failure no longer stops check-in.

**Expected finding:** `(Nothing moves, although the request is a rewrite. "4.2 Badge printing capacity" is Explanation: it argues that one printer per large site is too few. The last sentence recommends an action to a third party, the Facilities lead, and gives its reason, so it is part of the argument and not a How-to seam. The response names the section's type and returns the text unchanged, with no "How to …" section and no link line.)`

---

## Verification Log

**Verified 2026-10-22.** Result: **21/21 passed.** Graded by an Opus agent reading `SKILL.md` and `TESTS.md` after the tests were rewritten into neutral scenarios, with no edit to either file afterwards.

Produced against `TESTS.md` body sha256 `4b35d16ae5e3f744` and `SKILL.md` sha256 `56d47c5fd518abcc`. The body hash covers everything above this heading, so it survives this table being written. Recompute both before trusting the rows: any later edit invalidates them.

| Test                                                                             | Finding matches Expected | Pass |
|----------------------------------------------------------------------------------|--------------------------|------|
| 1. How-to with an Explanation seam                                               | ✓                        | PASS |
| 2. Tutorial with a Reference seam                                                | ✓                        | PASS |
| 3. Reference with a How-to seam                                                  | ✓                        | PASS |
| 4. Explanation with a How-to seam                                                | ✓                        | PASS |
| 5. A report's recommendation to a third party stays whole; a policy is Reference | ✓                        | PASS |
| 6. Split into a new section                                                      | ✓                        | PASS |
| 7. Split into an existing section                                                | ✓                        | PASS |
| 8. No empty sections, even when asked                                            | ✓                        | PASS |
| 9. Moved text stays verbatim, markers included                                   | ✓                        | PASS |
| 12. A lesson inside a Reference section gets a Lesson link                       | ✓                        | PASS |
| 10. A request not to change the text keeps it a review                           | ✓                        | PASS |
| 11. The priority list puts task seams first                                      | ✓                        | PASS |
| N1. A Record stays whole                                                         | ✓                        | PASS |
| N2. An executive summary stays put                                               | ✓                        | PASS |
| N3. A single-type section                                                        | ✓                        | PASS |
| N4. A reason inside a step                                                       | ✓                        | PASS |
| N5. A limit that says "must" stays in its Reference section                      | ✓                        | PASS |
| N6. A summary and a Record stay whole under a rewrite request                    | ✓                        | PASS |
| N7. Text that is already split comes back unchanged                              | ✓                        | PASS |
| N8. An obligation on a named party stays in its rules section                    | ✓                        | PASS |
| N9. A report's recommendation to a third party stays with its reasons            | ✓                        | PASS |

21 tests: 21 PASS, 0 PASS with discrepancy, 0 FAIL; no `SKILL.md` example defect.

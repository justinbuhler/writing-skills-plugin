# Plain Language Skill — Red/Green Test Suite

Each test has:

- **RED:** text that violates the check (should be flagged)
- **GREEN:** text that passes the check (should be clean)
- **Expected finding:** what the skill should flag in the RED case

Unless a test states its own context, the writer of every RED is the agency that receives and decides the applications, so "we" and "us" in a GREEN mean that agency. The reader is the applicant, so "you" means the applicant.

---

## Area 1: Audience and Purpose

### 1.1 — Audience identified

**RED:**

> These rules govern how parties apply. Parties must complete Form 1040-X.

**GREEN (audience: public):**

> These rules govern how you apply. You must complete Form 1040-X.

**Expected finding:** `[audience] No clear indication of who the reader is — "parties" is vague. Identify the reader directly: "you" for the reader; "we" for the agency that writes. → "These rules govern how you apply. You must complete Form 1040-X."`

---

### 1.2 — Reader's goal stated

**RED:**

> This document describes the agency's procedures for reviewing and processing claims under Title IV of the Act, as amended in 1997, 2003, and 2014.

**GREEN:**

> This guide tells you what to expect when we review and process your claim. It covers claims under Title IV of the Act ([needs: name of the Act]), as amended in 1997, 2003, and 2014.
>
> **Gaps:** name of the Act

**Expected finding:**

- `[purpose] The document describes the agency's process, not the reader's goal. State the reader's goal (what to expect when we review their claim) instead of describing the agency's process. "We" is justified: the writer is the agency that reviews the claims.`
- `[pronouns] "the agency's procedures for reviewing and processing claims" → "when we review and process your claim"`
- `[jargon] "the Act" is never named, and a public reader cannot tell which law it is → "the Act ([needs: name of the Act])", listed under **Gaps**`

---

### 1.3 — Bottom-line-up-front

**RED (writer: a community clinic describing the Department's program, so "the Department" stays in the third person):**

> The Department of Health was established in 1953. Since then, it has administered benefits for over 60 million Americans. The program covers hospital visits, prescription drugs, and preventive care. In 2022, Congress expanded eligibility. **If you are over 65 or have a qualifying disability, you may be eligible for benefits.**

**GREEN:**

> **You may be eligible for benefits if you are over 65 or have a qualifying disability.**
>
> The program covers hospital visits, prescription drugs, and preventive care.
>
> The Department of Health was established in 1953. Since then, it has administered benefits for over 60 million Americans. In 2022, Congress expanded eligibility.

**Expected finding:** `[bottom-line-up-front] The eligibility statement is buried at the end of a long preamble. Move the key message — who qualifies — to the first sentence, in its own paragraph above the rest.` `[one idea per paragraph] The 5-sentence paragraph covers three topics: who qualifies, what the program covers, and background (the Department's history and the 2022 expansion). Give each its own paragraph, with who qualifies first and the background last.` No separate topic-sentence finding: the buried main point is the same defect, reported once as bottom-line-up-front. No passive finding for "was established": who established the Department does not matter to the reader (passive exception).

---

### 1.4 — Multiple audiences addressed separately

**RED:**

> Applicants must submit Form A by March 1. Reviewing officers must verify income documents within 14 business days of receipt. Applicants who have been denied may appeal within 30 days. Reviewing officers must notify the applicant of a denial in writing.

**GREEN:**

> **For applicants:** Send us Form A by March 1.
>
> If we deny your application, you may appeal within 30 days.
>
> **For reviewing officers:** Verify income documents within 14 business days of receipt. Notify the applicant in writing of any denial.

**Expected finding:**

- `[audience separation] Applicant requirements and officer requirements are mixed in the same section. Separate them under distinct labeled headings.`
- `[word choice] "submit" → "send"`
- `[pronouns] "Applicants must submit Form A" → "Send us Form A" (in the applicants' section, address the applicant as "you")`
- `[passive] "Applicants who have been denied may appeal" → "If we deny your application, you may appeal" ("we" is the agency that decides)`
- `[pronouns] "Reviewing officers must verify…" and "Reviewing officers must notify…" → "Verify…" and "Notify…" (in the officers' section the officer is the reader)`
- `[one idea per paragraph] Applying and appealing a denial are two topics. Give the appeal its own paragraph in the applicants' section.`
- No finding for "Notify the applicant" in the officers' section: there the applicant is a third party, not the reader. Verifying documents and notifying of a denial are stages of one review, so the officers' paragraph stays whole.

---

## Area 2: Sentence Structure

### 2.1 — Active voice

**RED:**

> The application must be submitted by the deadline. Incomplete forms will be rejected. The decision will be communicated to the applicant by the reviewing officer.

**GREEN:**

> Send us your application by the deadline. We will reject incomplete forms. The reviewing officer will notify you of the decision.

**Expected finding:**

- `[passive] "must be submitted by the deadline" → "Send us your application by the deadline"`
- `[word choice] "submitted" → "send"`
- `[passive] "will be rejected" → "We will reject incomplete forms"`
- `[passive] "will be communicated to the applicant by" → "The reviewing officer will notify you" ("the applicant" becomes "you")`

---

### 2.2 — Present tense

**RED:**

> Applicants would be required to provide documentation of income. This page would list the papers that would prove your income. The form would need to be completed in full.

**GREEN:**

> You must send us proof of your income. This page lists the papers that prove your income. Complete the form in full.

**Expected finding:**

- `[tense] "would be required to" → "must" (present tense)`
- `[pronouns] "Applicants" → "You"`
- `[hidden verb] "provide documentation of income" → "send us proof of your income" ("provide" is on the substitution list as "give"; "send" fits a document that goes to the agency, and "us" is the agency that receives it)`
- `[tense] "would list… would prove" → "lists… prove" (present tense)`
- `[tense] "would need to be completed" → "Complete the form in full" (present tense; also fixes the passive, and the reader is the actor because it is the reader's own form)`

---

### 2.3 — Sentence length (≤ 25 words)

**RED:**

> In order to ensure that all applicants receive fair and equal consideration under the applicable provisions of the law, the agency has established a comprehensive review process that takes into account all relevant factors.

**GREEN:**

> We have set up a comprehensive review process that considers all relevant factors. Its purpose is to make sure we consider all applicants fairly and equally under the applicable provisions of the law.

**Expected finding:**

- `[sentence length] 34-word sentence. Break it in two: "We have set up a comprehensive review process that considers all relevant factors. Its purpose is to make sure we consider all applicants fairly and equally under the applicable provisions of the law."`
- `[audience fit] Long subordinate clause before the main action: the 19-word "In order to ensure…" clause comes before "has established". Put the main action first.`
- `[word choice] "In order to ensure" → "to make sure"`
- `[pronouns] "the agency has established" → "We have set up"`
- `[hidden verb] "receive fair and equal consideration" → "we consider all applicants fairly and equally"`
- `[word choice] "takes into account" → "considers" (single word over circumlocution)`

---

### 2.4 — Hidden verbs (nominalizations)

**RED:**

> The committee will conduct an evaluation of the proposals and make a determination regarding eligibility. The agency is responsible for implementation of the program and oversight of compliance.

**GREEN:**

> The committee will evaluate the proposals and decide on eligibility. We are responsible for carrying out the program and overseeing compliance.

**Expected finding:**

- `[hidden verb] "conduct an evaluation of" → "evaluate"`
- `[hidden verb] "make a determination regarding" → "decide on"`
- `[hidden verb] "implementation of the program" → "carrying out the program"`
- `[hidden verb] "oversight of compliance" → "overseeing compliance"`
- `[pronouns] "The agency is responsible" → "We are responsible" (keep "responsible": "We carry out the program" would narrow a responsibility into a claim about who does the work)`

---

### 2.5 — Positive statements

**RED:**

> Do not forget to sign the last page. The agency will not process applications that do not include all required documents. You must not submit more than one form.

**GREEN:**

> Sign the last page. We will process only applications that include all required documents. You must not send more than one form.

**Expected finding:**

- `[negative] "Do not forget to sign the last page" → "Sign the last page"`
- `[negative] "will not process applications that do not include" → "will process only applications that include all required documents"`
- `[pronouns] "The agency will not process" → "We will process only"`
- `[word choice] "submit" → "send" ("You must not submit more than one form" stays a prohibition)`

---

### 2.6 — One idea per paragraph

**RED:**

> To qualify, you must be 18 years old and a U.S. citizen. Send us your application by March 1 each year. We process applications within 60 days. If we deny your application, you have 30 days to appeal. A separate panel reviews appeals. The panel will notify you of its decision within 45 days.

**GREEN:**

> **Who can apply:** To qualify, you must be 18 years old and a U.S. citizen.
>
> **Applying:** Send us your application by March 1 each year. We process applications within 60 days.
>
> **If we deny your application:** You have 30 days to appeal. A separate panel reviews appeals. The panel will notify you of its decision within 45 days.

**Expected finding:**

- `[one idea per paragraph] The paragraph covers three topics: who qualifies, applying (the deadline and processing time are stages of one process), and appeals. Split into paragraphs, each with one topic.`
- `[white space] 6-sentence paragraph, over the 5-sentence limit. The split above fixes it.`

---

### 2.7 — Topic sentences

**RED:**

> Check that your address is current. If you skip a section, we will return the form to you. **You must fill in every section of the form before you send it.**

**GREEN:**

> **You must fill in every section of the form before you send it.** Check that your address is current. If you skip a section, we will return the form to you.

**Expected finding:** `[topic sentence] The paragraph's main point ("fill in every section") is at the end, not the beginning. Open with the main instruction and keep the other two sentences in their original order.`

---

### 2.8 — "Must" replaces "shall"

**RED:**

> You shall send us Form A by March 1. We shall process applications within 60 days. The reviewing officer shall notify you in writing. Incomplete forms shall be rejected.

**GREEN:**

> You must send us Form A by March 1. We must process applications within 60 days. The reviewing officer must notify you in writing. We must reject incomplete forms.

**Expected finding:**

- `[shall] "shall send" → "must send"`
- `[shall] "shall process" → "must process" (an agency obligation stays an obligation; "will" would turn it into a prediction)`
- `[shall] "shall notify" → "must notify"`
- `[shall] "shall be rejected" → "We must reject incomplete forms" (also fixes the passive; "we" is the agency that decides)`

---

### 2.9 — "May" for permissions, "should" for recommendations

**RED:**

> You are permitted to send us extra documents to support your application. It is advisable to send the form early to avoid delays.

**GREEN:**

> You may send us extra documents to support your application. You should send the form early to avoid delays.

**Expected finding:**

- `[modal] "are permitted to send us" → "may send us"`
- `[modal] "it is advisable to" → "you should"`

---

### 2.10 — Active voice when the text names no actor

**RED (writer: a contractor reporting to the agency):**

> Our team has delivered the test plan. The security review must be finished before the system goes live.

**GREEN:**

> Our team has delivered the test plan. [needs: actor] must finish the security review before the system goes live.
>
> **Gaps:** actor for "must finish the security review"

**Expected finding:** `[passive] "must be finished" names no actor, and the text does not show that the writer does the review → "[needs: actor] must finish the security review before the system goes live", with the actor listed under **Gaps**. Do not write "We must finish".`

---

### 2.11 — Clean notice stays unflagged

**RED (input to review; writer: the library; audience: public):**

> **What the card does:** A free library card lets you borrow books, films, and museum passes.
>
> **Who qualifies:** If you are employed in the county, you qualify.
>
> **Getting your card:** Pick up your card at our main branch, which is located at 12 Elm Road. If you cannot visit a branch, call the number on our website and we will mail you the card.
>
> **Sharing your card:** You must not share your card.

**GREEN (expected output — returned unchanged):**

> **What the card does:** A free library card lets you borrow books, films, and museum passes.
>
> **Who qualifies:** If you are employed in the county, you qualify.
>
> **Getting your card:** Pick up your card at our main branch, which is located at 12 Elm Road. If you cannot visit a branch, call the number on our website and we will mail you the card.
>
> **Sharing your card:** You must not share your card.

**Expected finding:** `(No finding — "are employed" and "is located" describe states, not passive actions; "we will mail" is what happens after the reader acts; "If you cannot visit" is a negative condition and "must not share" a prohibition, so neither is a negative to flip; "books, films, and museum passes" is a short inline series of things, not steps or requirements; the "and" sentence is under 20 words; each labeled paragraph covers one topic and opens with its main point. Every area reports "✓ No issues found." and Top priority changes reads "None".)`

---

## Area 3: Word Choice

### 3.1 — Substitution list (common words)

**RED:**

> We shall endeavor to facilitate your utilization of the program. Prior to commencing your application, you must obtain the requisite documents. Subsequent to receiving your application, we will commence the review.

**GREEN:**

> We must try to help you use the program. Before you start your application, you must get the required documents. After we receive your application, we will start the review.

**Expected finding:**

- `[shall] "shall endeavor" → "must try"`
- `[word choice] "endeavor" → "try"`
- `[word choice] "facilitate" → "help"`
- `[word choice] "utilization" → "use"`
- `[word choice] "prior to" → "before"`
- `[word choice] "commencing" → "start"`
- `[word choice] "obtain" → "get"`
- `[word choice] "requisite" → "required"`
- `[word choice] "subsequent to" → "after"`
- `[word choice] "commence" → "start"`

---

### 3.2 — Noun strings

**RED:**

> Send the contractor contact information form for the flood repair assistance program with your application.

**GREEN:**

> With your application, send the form for the contractor's contact information for the program that helps with flood repairs.

**Expected finding:**

- `[noun string] "contractor contact information form" — three nouns stacked before "form". Rewrite: "the form for the contractor's contact information"`
- `[noun string] "flood repair assistance program" — three nouns stacked before "program". Rewrite: "the program that helps with flood repairs". "Assistance" is on the substitution list, so it becomes "helps"; the phrase is a lowercase description, not a program's official name, which would stay as written.`

---

### 3.3 — No jargon without definition

**RED:**

> The PII collected through this system of records is governed by the Privacy Act. FISMA compliance is required for all federal information systems. Your submission will be processed through our COTS software.

**GREEN (public audience):**

> The personally identifiable information collected through this system of records is governed by the Privacy Act. A system of records is [needs: plain definition of "system of records"].
>
> All federal information systems must comply with [needs: full name of "FISMA"]. [needs: plain definition of what FISMA requires]
>
> We will process your submission using our commercial off-the-shelf software.
>
> **Gaps:**
> - plain definition of "system of records"
> - full name of "FISMA"
> - plain definition of what FISMA requires

**Expected finding:**

- `[jargon] "PII" undefined for public audience → spell out "personally identifiable information"`
- `[jargon] "FISMA compliance" undefined for public audience, and "FISMA" appears once → its full name is uncertain, so mark it and what it requires: "must comply with [needs: full name of "FISMA"]. [needs: plain definition of what FISMA requires]"`
- `[jargon] "system of records" is a Privacy Act term undefined for public audience → keep the term and define it: "A system of records is [needs: plain definition of "system of records"]."`
- `[jargon] "COTS" undefined → spell out "commercial off-the-shelf software"`
- `[modal] "FISMA compliance is required for all federal information systems" → "All federal information systems must comply with…" ("must" for an obligation)`
- No passive finding for "is governed by the Privacy Act": the law is the actor (passive exception). Keep "collected" without an actor: the RED names no collector, so do not supply "we".
- `[passive] "will be processed" → "We will process"`
- No [one idea per paragraph] finding: the RED has 3 sentences, and the rule needs more than 3.
- The rewrite lists all three `[needs: …]` markers under **Gaps**.

---

### 3.4 — Legal archaisms

**RED:**

> Hereinafter, the applicant shall be referred to as "the party." The party hereby agrees to the terms set forth herein. Whereas the foregoing provisions apply, the party thereof must comply.

**GREEN:**

> From here on, "the party" means you, the applicant. You agree to the terms in this document. Because the rules above apply, you must comply.

**Expected finding:**

- `[archaism] "hereinafter" → "from here on" ("in this document" would also reach back over earlier text)`
- `[shall] "shall be referred to as" → "means" ("From here on, "the party" means you, the applicant")`
- `[pronouns] "the applicant" / "the party" → "you"`
- `[archaism] "hereby agrees" → "agrees"`
- `[archaism] "set forth herein" → "in this document" or "listed here"`
- `[archaism] "Whereas the foregoing provisions" → "Because the rules above"`
- `[archaism] "thereof" → delete or rephrase`

---

### 3.5 — Business jargon

**RED:**

> Going forward, we will leverage our core competencies to synergize our outreach efforts and move the needle on program uptake. We encourage you to reach out and circle back with your program manager.

**GREEN:**

> From now on, we will use our strengths to combine our outreach efforts and increase participation in the program. You should contact your program manager to follow up.

**Expected finding:**

- `[jargon] "going forward" → "from now on"`
- `[jargon] "leverage" (verb) → "use"`
- `[jargon] "core competencies" → "strengths"`
- `[jargon] "synergize" → "combine"`
- `[jargon] "move the needle on program uptake" → "increase participation in the program"`
- `[jargon] "reach out" → "contact" (keep the recommendation: "You should contact")`
- `[jargon] "circle back" → "follow up"`

---

### 3.6 — "You" and "we"

**RED:**

> Applicants must send Form A by March 1. The agency will review Form A within 60 days. Applicants who have been denied may appeal. The agency will respond to all appeals within 30 days.

**GREEN:**

> You must send Form A by March 1. We will review it within 60 days.
>
> If we deny your application, you may appeal. We will respond to all appeals within 30 days.

**Expected finding:**

- `[pronouns] "Applicants must send" → "You must send"`
- `[pronouns] "The agency will review" → "We will review"`
- `[pronouns] "Applicants who have been denied may appeal" → "If we deny your application, you may appeal" (also fixes the passive; "we" is the agency that decides)`
- `[pronouns] "The agency will respond" → "We will respond"`
- `[one idea per paragraph] The paragraph covers two topics: applying and appeals. Split it into two paragraphs.`

---

### 3.7 — Acronyms defined on first use

**RED:**

> The ADA requires agencies to make reasonable accommodations. Contact your EEO officer if you need ADA accommodations. HR will coordinate with the EEO officer to process your request.

**GREEN:**

> The Americans with Disabilities Act requires agencies to make reasonable accommodations. Contact your Equal Employment Opportunity officer if you need accommodations under the Americans with Disabilities Act. Human Resources will coordinate with the Equal Employment Opportunity officer to process your request.

**Expected finding:**

- `[acronym] "ADA" not defined, and used fewer than three times → spell out "Americans with Disabilities Act" both times (Acronyms rule: a fixed, well-known public expansion adds no fact)`
- `[acronym] "EEO" not defined, and used fewer than three times → spell out "Equal Employment Opportunity" both times (Acronyms rule: a fixed, well-known public expansion adds no fact)`
- `[acronym] "HR" not defined, and used once → "Human Resources" (Acronyms rule: a fixed, well-known public expansion adds no fact)`
- No hidden-verb finding: "make reasonable accommodations" is the Americans with Disabilities Act's legal term of art (Hidden verbs exception), so it stays.

---

### 3.8 — Verbatim text stays as written

**RED (audience: public):**

> To utilize the website, open **Records Requests** and select **Submit Request**. Set the field `REQUEST_TYPE` to `COPY`. Section 4(a) of the County Records Act reads: "Each requester shall submit a signed request form."

**GREEN:**

> To use the website, open **Records Requests** and select **Submit Request**. Set the field `REQUEST_TYPE` to `COPY`. Section 4(a) of the County Records Act reads: "Each requester shall submit a signed request form."

**Expected finding:** `[word choice] "To utilize the website" → "To use the website". No other finding: the quotation, the **Submit Request** label, and the REQUEST_TYPE and COPY code values are verbatim text, so "shall", "submit", and the capitals stay as written.`

---

### 3.9 — List entries apply only when the meaning survives

**RED (audience: backend developers):**

> The endpoint takes three parameters: `id`, `since`, and `format`. Whether or not the token has expired, the server returns HTTP 200, so check the `error` field. Prior to each retry, wait two seconds.

**GREEN:**

> The endpoint takes three parameters: `id`, `since`, and `format`. Whether or not the token has expired, the server returns HTTP 200, so check the `error` field. Before each retry, wait two seconds.

**Expected finding:** `[word choice] "Prior to each retry" → "Before each retry". No other finding: "parameters" → "limits" would change the meaning, "Whether or not" here means "regardless of whether", and HTTP is everyday vocabulary for this audience.`

---

### 3.10 — Acronyms defined by a glossary or a reverse parenthetical

**RED (audience: agency staff):**

> **Terms in this notice**
>
> | Term | Meaning                  |
> |------|--------------------------|
> | TMS  | Travel Management System |
>
> Book all work trips in TMS starting May 4. Sign in to TMS with SSO (single sign-on). Obtain approval from your supervisor prior to booking. Upload receipts to TMS as PDF files.

**GREEN:**

> **Terms in this notice**
>
> | Term | Meaning                  |
> |------|--------------------------|
> | TMS  | Travel Management System |
>
> Book all work trips in TMS starting May 4. Sign in to TMS with SSO (single sign-on). Get approval from your supervisor before you book. Upload receipts to TMS as PDF files.

**Expected finding:**

- `[word choice] "Obtain" → "Get"`
- `[word choice] "prior to booking" → "before you book"`
- No acronym finding: the glossary defines TMS before its first use, "SSO (single sign-on)" defines SSO in reverse order, and PDF is everyday vocabulary for staff.
- No [one idea per paragraph] finding: the four sentences cover one topic, how to use TMS for a work trip.

---

## Area 4: Structure and Design

### 4.1 — Descriptive headings

**RED:**

> ## Introduction
>
> The program pays part of your heating bill in winter.
>
> ## Overview
>
> The program serves low-income families.
>
> ## General
>
> Eligibility depends on income.

**GREEN:**

> ## What the program pays for
>
> The program pays part of your heating bill in winter.
>
> ## Who the program serves
>
> The program serves low-income families.
>
> ## Who qualifies?
>
> Eligibility depends on income.

**Expected finding:**

- `[heading] "Introduction" → rewrite as descriptive ("What the program pays for")`
- `[heading] "Overview" → rewrite as descriptive ("Who the program serves")`
- `[heading] "General" → always vague, rewrite ("Who qualifies?")`

---

### 4.2 — Lists for 3+ parallel items

**RED:**

> To apply, you must submit your completed Form A, a copy of your photo ID, proof of income for the past 12 months, two letters of reference, and a completed background check authorization.

**GREEN:**

> To apply, send us all of the following:
>
> - Completed Form A
> - Copy of your photo ID
> - Proof of income for the past 12 months
> - Two letters of reference
> - Completed authorization for a background check

**Expected finding:**

- `[list] Five items strung together with commas. Convert to a bulleted list.`
- `[sentence length] 33-word sentence. The bulleted list fixes it: the intro "To apply, send us all of the following:" is 8 words.`
- `[noun string] "background check authorization" → "authorization for a background check"`
- `[word choice] "submit" → "send"`

---

### 4.3 — If/then tables for complex conditionals

**RED:**

> If you are a veteran who served after 1990 or a surviving spouse of a veteran who served after 1990, and if your household income is below $45,000, you may qualify for the enhanced benefit. If you are a veteran who served before 1990, regardless of income, you qualify for the standard benefit only.

**GREEN:**

> **Which benefit do you qualify for?**
>
> | If you are...                                       | And your household income is... | Then...                                     |
> | --------------------------------------------------- | ------------------------------- | ------------------------------------------- |
> | Veteran who served after 1990                       | Below $45,000                   | You may qualify for the enhanced benefit    |
> | Surviving spouse of a veteran who served after 1990 | Below $45,000                   | You may qualify for the enhanced benefit    |
> | Veteran who served before 1990                      | Any amount                      | You qualify for the standard benefit only   |

**Expected finding:**

- `[conditional] Two "If" sentences stack four conditions into three cases. Convert to an if/then table with one row per case.`
- `[sentence length] The first sentence is 35 words. The table fixes it: each condition gets its own row.`

---

### 4.4 — Typography rules (no ALL CAPS)

**RED:**

> IMPORTANT: YOU MUST SUBMIT YOUR APPLICATION BY MARCH 1 OR YOUR REQUEST WILL BE DENIED. DO NOT SUBMIT INCOMPLETE FORMS.

**GREEN:**

> **Important:** Send us your application by March 1. If you do not send it by then, we will deny your request. Send complete forms only.

**Expected finding:**

- `[typography] ALL CAPS used for emphasis → use bold instead`
- `[passive] "YOUR REQUEST WILL BE DENIED" → "If you do not send it by then, we will deny your request" (keeps the RED's send deadline and every case it covers, including an application never sent; "If you do not send" is a negative condition, not a negative to flip)`
- `[negative] "DO NOT SUBMIT INCOMPLETE FORMS" → "Send complete forms only"`
- `[word choice] "SUBMIT" → "send" (both times)`

---

### 4.5 — White space / paragraph length

**RED:**

> You start by sending Form A to the regional office. The regional office logs it and assigns it to a reviewing officer. The reviewing officer has 14 business days to check your documents. If your documents are incomplete, the reviewing officer returns them to you with a list of what is missing. You then have 30 days to fix the problem and send them again. If what you send is still incomplete, we may deny your application. Once the reviewing officer has checked your documents, they send a recommendation to the district supervisor. The district supervisor reviews it and decides within 45 days.

**GREEN:**

> **Step 1: Sending Form A.** You start by sending Form A to the regional office. The regional office logs it and assigns it to a reviewing officer.
>
> **Step 2: Checking your documents.** The reviewing officer has 14 business days to check your documents.
>
> **Step 3: Fixing missing documents.** If your documents are incomplete, the reviewing officer returns them to you with a list of what is missing. You then have 30 days to fix the problem and send them again. If what you send is still incomplete, we may deny your application.
>
> **Step 4: Getting a decision.** Once the reviewing officer has checked your documents, they send a recommendation to the district supervisor. The district supervisor reviews it and decides within 45 days.

**Expected finding:** `[white space] 8-sentence paragraph covering 4 distinct process steps. Split into separate paragraphs or a numbered list.` No one-idea finding: the steps are stages of one process, so they are one topic and the split is for length. The sentences themselves stay as written under the step labels.

---

### 4.6 — Paragraph over five sentences

**RED:**

> Bring your completed form to any branch. Staff check that you filled in every section. They copy your photo ID and hand it back. They take your photo at the desk. They print your card while you wait. You can use it the same day.

**GREEN:**

> Bring your completed form to any branch. Staff check that you filled in every section. They copy your photo ID and hand it back.
>
> Staff take your photo at the desk. They print your card while you wait. You can use it the same day.

**Expected finding:** `[white space] 6-sentence paragraph, over the 5-sentence limit. Split it into two paragraphs.`

---

### 4.7 — Captions a required format mandates

**RED (writer: the Office, which receives the proposals; a Federal Register notice):**

> AGENCY: Office of Rural Water Grants.
>
> ACTION: Notice.
>
> SUMMARY: We offer grants to small water systems. Proposals must be received by June 30, 2027.

**GREEN:**

> AGENCY: Office of Rural Water Grants.
>
> ACTION: Notice.
>
> SUMMARY: We offer grants to small water systems. Your proposal must reach us by June 30, 2027.

**Expected finding:** `[passive] "Proposals must be received" → "Your proposal must reach us by June 30, 2027" ("us" is the Office that writes the notice and receives proposals; keep the receipt deadline, since "send by" would move it). No typography or heading finding: the ALL CAPS captions are required by the format; the review covers the prose under them.`

---

### 4.8 — Standard heading and named decision-maker stay unflagged

**RED (input to review; writer: the county transport office; audience: residents):**

> ## Decision needed
>
> The county board must approve the new route map by May 1.
>
> ## Background
>
> We run 42 bus routes.

**GREEN (expected output — returned unchanged):**

> ## Decision needed
>
> The county board must approve the new route map by May 1.
>
> ## Background
>
> We run 42 bus routes.

**Expected finding:** `(No finding — "Background" is a standard section name doing its job, so it is not a vague heading. "The county board" is a named decision-maker who is not the reader, so it stays named and does not become "you". "We" is the writer, the county transport office. No other finding.)`

---

## Area 5: Audience Fit

### 5.1 — First-time reader can act

**RED:**

> Per § 203(a)(1)(B) of the Act, as amended by Public Law 104-66, eligible entities as defined under 42 U.S.C. § 1437a(b)(3) who meet the criteria established pursuant to the implementing regulations at 24 CFR Part 5 may apply for assistance under this subpart.

**GREEN:**

> You may apply for help under this subpart ([needs: what "this subpart" refers to]) if you are an eligible entity. An eligible entity is [needs: plain definition of "eligible entities"], as defined in 42 U.S.C. § 1437a(b)(3). You also need to meet the criteria set by the regulations at 24 CFR Part 5.
>
> These regulations carry out the Act ([needs: name of the Act]). This rule comes from § 203(a)(1)(B) of the Act, as amended by Public Law 104-66.
>
> **Gaps:**
> - what "this subpart" refers to
> - plain definition of "eligible entities"
> - name of the Act

**Expected finding:**

- `[sentence length] 43-word sentence. Split it: the rewrite uses five sentences, none over 25 words.`
- `[word choice] "assistance" → "help"`
- `[jargon] "this subpart" is regulatory jargon for a public reader, and the RED does not say which subpart → keep it and add "([needs: what "this subpart" refers to])", listed under **Gaps**`
- `[pronouns] "eligible entities … may apply" → "You may apply … if you are an eligible entity"`
- `[word choice] "implementing regulations" → "These regulations carry out the Act". In a statutory citation, "implementing regulations" means the regulations that carry out the statute cited, here the Act, so this states the term's meaning rather than adding a claim.`
- `[legalese] "established pursuant to" → "set by"`
- `[jargon] "the Act" is never named, and a public reader cannot tell which law it is → "the Act ([needs: name of the Act])" at its first use in the rewrite, listed under **Gaps**`
- `[audience fit] Dense statutory citations with no plain explanation. A first-time reader cannot determine whether they qualify. Add a plain-language statement of who is eligible before citing the regulations.`
- `[audience fit] "eligible entities as defined under 42 U.S.C. § 1437a(b)(3)" — define what "eligible entities" means in plain terms. The RED does not give the definition, so the fix carries [needs: plain definition of "eligible entities"] and keeps the citation outside the marker, where it survives once the marker is filled: "An eligible entity is [needs: plain definition of "eligible entities"], as defined in 42 U.S.C. § 1437a(b)(3)." Acronyms inside a citation need no definition.`

---

### 5.2 — No conditional stacking

**RED:**

> If you are a full-time employee who has been continuously employed for at least one year, unless you are on a temporary contract or are in a probationary period, except if your probationary period was extended for documented performance reasons, in which case you may still qualify provided you obtain written approval from your supervisor, you may apply for the enhanced benefit.

**GREEN:**

> You may apply for the enhanced benefit if you meet all of these conditions:
>
> - You are a full-time employee.
> - You have been employed continuously for at least one year.
> - You are not on a temporary contract.
> - You are not in a probationary period, or you are in one extended for documented performance reasons and get written approval from your supervisor.

**Expected finding:**

- `[conditional stacking] Nested conditions with "unless", "except", and "provided" in a single sentence. Every condition must hold for the one outcome, so convert to a bulleted list of the conditions (an if/then table or labeled sections also works).`
- `[sentence length] 62-word sentence. The list fixes it: no sentence in the rewrite is over 25 words.`
- `[word choice] "obtain" → "get"`
- `[word choice] "provided" → "and" (the supervisor's approval joins the extended-period case in one either/or condition, so every listed condition must hold)`
- No passive finding for "was extended": the text names no actor, and who extended the period does not matter to the reader.

---

### 5.3 — Legalese → precise plain language

**RED:**

> Notwithstanding the foregoing, the aforementioned applicant shall be deemed to have waived any and all rights, claims, and causes of action arising hereunder in the event that the party fails to timely submit said documentation in accordance with the provisions hereof.

**GREEN:**

> You waive all rights, claims, and grounds to sue under this document if you do not send your documents on time. You also waive them if you send your documents in a way this document does not allow. Both rules apply even if something earlier in this document says otherwise.

**Expected finding:**

- `[sentence length] 41-word sentence. Split it into three sentences (21, 17, and 12 words): one per failure that triggers the waiver, then the override.`
- `[archaism] "Notwithstanding the foregoing" → "Both rules apply even if something earlier in this document says otherwise"`
- `[archaism] "the aforementioned applicant" → "you"`
- `[pronouns] "the party" → "you"`
- `[legalese] "shall be deemed to have waived" → "waive"`
- `[legalese] "any and all rights, claims, and causes of action" → "all rights, claims, and grounds to sue"`
- `[archaism] "arising hereunder" → "under this document"`
- `[legalese] "in the event that" → "if"`
- `[legalese] "fails to timely submit said documentation" → "do not send your documents on time" (covers late and never sent)`
- `[archaism] "in accordance with the provisions hereof" → a second trigger, "You also waive them if you send your documents in a way this document does not allow" (either failure triggers the waiver; deleting it narrows the waiver)`

---

## Verification Log

**Verified 2026-10-22.** Result: **36/36 passed.** Graded by an Opus agent reading `SKILL.md` and `TESTS.md`, with no edit to either file afterwards.

Produced against `TESTS.md` body sha256 `a6df8bcda26c251e` and `SKILL.md` sha256 `720e463c9cb7ac66`. The body hash covers everything above this heading, so it survives this table being written. Recompute both before trusting the rows: any later edit invalidates them, and a log that certifies rather than records hides the defects it exists to surface.

| Test                                                             | RED flags | GREEN clean | Pass |
|------------------------------------------------------------------|-----------|-------------|------|
| 1.1 — Audience identified                                        | ✓         | ✓           | PASS |
| 1.2 — Reader's goal stated                                       | ✓         | ✓           | PASS |
| 1.3 — Bottom-line-up-front                                       | ✓         | ✓           | PASS |
| 1.4 — Multiple audiences addressed separately                    | ✓         | ✓           | PASS |
| 2.1 — Active voice                                               | ✓         | ✓           | PASS |
| 2.2 — Present tense                                              | ✓         | ✓           | PASS |
| 2.3 — Sentence length (≤ 25 words)                               | ✓         | ✓           | PASS |
| 2.4 — Hidden verbs (nominalizations)                             | ✓         | ✓           | PASS |
| 2.5 — Positive statements                                        | ✓         | ✓           | PASS |
| 2.6 — One idea per paragraph                                     | ✓         | ✓           | PASS |
| 2.7 — Topic sentences                                            | ✓         | ✓           | PASS |
| 2.8 — "Must" replaces "shall"                                    | ✓         | ✓           | PASS |
| 2.9 — "May" for permissions, "should" for recommendations        | ✓         | ✓           | PASS |
| 2.10 — Active voice when the text names no actor                 | ✓         | ✓           | PASS |
| 2.11 — Clean notice stays unflagged                              | ✓         | ✓           | PASS |
| 3.1 — Substitution list (common words)                           | ✓         | ✓           | PASS |
| 3.2 — Noun strings                                               | ✓         | ✓           | PASS |
| 3.3 — No jargon without definition                               | ✓         | ✓           | PASS |
| 3.4 — Legal archaisms                                            | ✓         | ✓           | PASS |
| 3.5 — Business jargon                                            | ✓         | ✓           | PASS |
| 3.6 — "You" and "we"                                             | ✓         | ✓           | PASS |
| 3.7 — Acronyms defined on first use                              | ✓         | ✓           | PASS |
| 3.8 — Verbatim text stays as written                             | ✓         | ✓           | PASS |
| 3.9 — List entries apply only when the meaning survives          | ✓         | ✓           | PASS |
| 3.10 — Acronyms defined by a glossary or a reverse parenthetical | ✓         | ✓           | PASS |
| 4.1 — Descriptive headings                                       | ✓         | ✓           | PASS |
| 4.2 — Lists for 3+ parallel items                                | ✓         | ✓           | PASS |
| 4.3 — If/then tables for complex conditionals                    | ✓         | ✓           | PASS |
| 4.4 — Typography rules (no ALL CAPS)                             | ✓         | ✓           | PASS |
| 4.5 — White space / paragraph length                             | ✓         | ✓           | PASS |
| 4.6 — Paragraph over five sentences                              | ✓         | ✓           | PASS |
| 4.7 — Captions a required format mandates                        | ✓         | ✓           | PASS |
| 4.8 — Standard heading and named decision-maker stay unflagged   | ✓         | ✓           | PASS |
| 5.1 — First-time reader can act                                  | ✓         | ✓           | PASS |
| 5.2 — No conditional stacking                                    | ✓         | ✓           | PASS |
| 5.3 — Legalese → precise plain language                          | ✓         | ✓           | PASS |

Failures: none.

# BridgeIt

From “I need help” to “I’ve reached out,” one best-fit option at a time.

| Product | Role | Version | Status |
|---|---|---|---|
| BridgeIt | Product Manager, Designer & Developer | 0.2 · November 2026 | Prototype |

## 1 · TL;DR

- **What:** a mobile-friendly web guide that asks a few questions, recommends *one* best-fit mental health resource at a time, explains why it fits, and drafts the message to reach out.
- **Who:** UCLA students who need ongoing support beyond CAPS’s short-term care.
- **Why now:** CAPS offers 4 to 8 sessions a year, so students who need more must find off-campus care alone. Research suggests many referred students never connect, mostly because of cost and the effort of searching.
- **Goal:** 30% of students report initiating contact with a resource within 14 days (provisional pilot benchmark).

## 2 · Problem

**The pain.** UCLA’s counseling service (CAPS) is built for short-term care: 4 individual sessions per academic year, or 8 with UC SHIP. For ongoing care, CAPS refers students to off-campus providers. From there, the student does the work alone: a UC SHIP student needs a current CAPS referral, then every student searches a provider list, calls around to find someone taking new clients, works out cost and coverage, and follows up, often while struggling.

**The evidence.**

- **Hand-offs often fail.** In one study, 42% of students referred off campus by a university counseling center did not connect with a provider. Cost was the main barrier; follow-up and easy-to-use referral sources helped.¹
- **How the hand-off happens matters.** A study of 234 referred students found 55.6% of in-person referrals succeeded versus 39.2% of email referrals (not statistically significant).²
- **Getting a first CAPS appointment is relatively quick.** UC-wide in 2023–24, students waited an average of 7.6 days for a first counseling appointment.³ This suggests initial access is not the main delay, though it doesn’t show where students drop off.
- **Insurance varies widely.** UC-wide, 43% of students are on UC SHIP, 24% on employer plans, 7.5% on individual plans, and 7% on Medi-Cal, each with different rules.⁴

### Research approach

| Type                  | What it covers                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
|-----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Published research    | Referral studies and UC Regents data above. Not UCLA-specific; used to frame the problem.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| My resource directory | I built a directory of 54 LA support-group listings and checked each against organizer websites. **Verification:** 23 had a current published schedule, 10 were confirmed programs whose schedules still need checking, 18 were directory listings I couldn’t confirm, and 3 were inactive. **Audience:** 12 of the 23 scheduled listings are for family members or caregivers, so only 11 were both current and meant for the person seeking help. This shaped the matching rules and verification policy in section 5. For the prototype, I built a broader directory of 38 listings across CAPS, therapy and peer support, each checked on the organizer’s website: 29 are live and 9 are held back with the reason recorded. |
| Hypotheses to test    | That students struggle most at the hand-off, and that one guided recommendation plus outreach help increases contact. No student interviews yet; see the learning plan.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |

## 3 · Goal & metric

**North star: % of students who report initiating contact with a resource within 14 days.** “Initiating contact” means the student called, emailed or registered, as reported in the opt-in day-14 follow-up. Answers to the end-of-session “Did you reach out?” question count only as an early signal. Provisional pilot benchmark: **30%**.

| Supporting metric                              | What it tells us                                                                          | Provisional benchmark |
|------------------------------------------------|-------------------------------------------------------------------------------------------|-----------------------|
| Intake completion rate                         | Whether the questions are too many or confusing                                           | 60%                   |
| Students receiving at least one eligible match | Whether the directory is deep enough                                                      | 80%                   |
| First-option acceptance (diagnostic)             | How good the first recommendation is                                                      | 40%                   |
| Ease rating (diagnostic)                         | Whether getting help feels less overwhelming (post-task question in usability tests, 1–5) | 4 or higher           |

All figures are provisional pilot benchmarks, not measured results, and will be reset after beta testing.

## 4 · Scope

**Users.** Primary: UCLA students (18+) who need ongoing support after using or being referred by CAPS. Secondary: UCLA students who are struggling but haven’t reached out and aren’t sure what help fits.

| In (MVP) | Later | Explicitly out |
|---|---|---|
| Crisis resources on every screen | Voice input | Clinical advice, diagnosis or therapy |
| Guided intake (section 5) | Automated follow-up emails | Crisis counseling (routes to crisis services) |
| Rule-based matching with hard filters | Saved profiles or accounts | Replacing CAPS (works alongside it) |
| One recommendation at a time, with reasons | “See all matches” view | Contacting providers for the student |
| “Show me another” with a one-tap reason | Advanced adaptive ranking | |
| Editable outreach email and call script | Live availability and booking | |
| CAPS referral reminder (UC SHIP) | Automated directory upkeep; a “report a problem” button on each listing | |
| “Did you reach out?” question at the end of the session | Other LA campuses | |
| Opt-in day-14 follow-up email, sent manually during beta | | |
| Verified directory: 20–30 listings across CAPS, therapy and peer support | | |

## 5 · Solution sketch

### Why this approach

Students already have lists: CAPS’s provider database, insurance directories, Google. A list leaves the hardest work to the student. BridgeIt narrows the choice to one explained option and helps with the outreach. **Tradeoff:** one option at a time may reduce overwhelm, but it can make students feel they have less choice. This is a hypothesis; beta testing will compare one recommendation against a short list.

### Persona and user stories

Based on a hypothetical persona, to be validated in research.

**Maya**, a third-year on UC SHIP, has used her 8 CAPS sessions. CAPS referred her off campus, but the first three therapists she called never called back. During midterms, she stopped trying.

- As a UCLA student who needs ongoing support, I want resources that fit my insurance and budget, so I don’t waste time contacting providers I can’t use.
- As a student unfamiliar with support services, I want to see why a resource was recommended, so I can decide if it’s right for me.
- As a student who finds reaching out intimidating, I want an editable message I can send, so starting contact feels easier.

### Flow

Crisis resources always visible → intake → review answers → one recommendation → “Contact them” or “Show me another” (with a reason) → outreach draft → “Did you reach out?” → opt-in day-14 follow-up (sent manually during beta). If nothing fits, BridgeIt says so honestly and points to CAPS.

### Intake questions

These are the most important input for finding the best fit. The wording will be refined after the prototype is tested.

| \#  | Question                                                | Why we ask                                                                                                           |
|-----|---------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------|
| 1   | What’s your student status?                             | Eligibility; which CAPS rules apply                                                                                  |
| 2   | What kind of help are you looking for? (or “Not sure”)  | Type of resource to match                                                                                            |
| 3   | Have you been to CAPS this year? What did they suggest? | Avoid repeating CAPS; spot off-campus referrals                                                                      |
| 4   | What insurance do you have?                             | Cost and which providers are covered                                                                                 |
| 4a  | (UC SHIP only) Do you have a current CAPS referral?     | UC SHIP needs one for off-campus care                                                                                |
| 5   | What can you afford per session?                        | Budget filter                                                                                                        |
| 6   | In person, online, or either? Where are you based?      | Format and distance                                                                                                  |
| 7   | When are you usually free?                              | Schedule fit                                                                                                         |
| 8   | What matters most to you? (pick up to two)              | Ranking order. Includes an optional LGBTQ+-affirming priority; LGBTQ+-specific services appear only when it’s chosen |

No question asks about symptoms or diagnoses.

### Matching rules

1.  **Hard filters:** the listing’s verification is current (see Verification policy); the student is eligible; the resource is meant for the person seeking help (not family or caregivers); the support type matches what they asked for. Resource types (therapy, peer support, groups) are never treated as interchangeable.
2.  **Ranking:** among eligible options, rank by insurance and budget fit, format and location, schedule, and the student’s top priorities. If priorities are skipped: cost, then availability, then distance.
3.  **“Show me another”:** the reason given (too expensive, too far, wrong type, wrong times, other) re-ranks the remaining options for the session.
4.  **Missing information:** if cost, insurance or eligibility is unknown, BridgeIt says so and never presents it as confirmed. If the gap prevents a reliable match, the listing is held back.
5.  **Cost and hours:** the budget is compared with the listed per-session price, and upfront fees (such as an intake fee or a membership) are shown separately. With a \$0 budget, BridgeIt only recommends options that are free or that the organizer says can be free. Posted hours are never presented as open appointments.

### Verification policy

- **What counts as verified:** the schedule, cost, audience and how to join are confirmed on the organizer’s own website or directly with the organizer, and the date is recorded. A published schedule doesn’t confirm open spots, so cards say “Confirm a spot with the organizer.”
- **How often to recheck (proposed):** recurring groups every 60 days; clinics and therapy entry points every 90 days; courses and cohorts before each new start date; CAPS information once a quarter.
- **When verification expires:** the listing is hidden from recommendations, not deleted, and goes on a recheck list. If a student reports a problem, the listing is hidden right away until it’s rechecked.

### Acceptance criteria: the recommendation card

- Only shows a resource that passes every hard filter.
- States the resource type, format, location, hours and how to reach it.
- Displays the published cost and relevant insurance information when verified. Otherwise, clearly states that the student must confirm their coverage and out-of-pocket cost.
- Lists at least two reasons it fits, drawn from the student’s answers.
- Labels unknown availability as “confirm a spot with the organizer,” never as fact.
- Offers “Contact them” and “Show me another” on every card.
- Shows the listed price, any upfront fee and the student’s budget separately.
- Keeps posted hours separate from confirmed openings.
- Labels the result “Your top match based on your preferences,” not as a definitive best fit.

### Safety and privacy

- 988 and the CAPS 24/7 crisis line are visible on every screen. The crisis wording and flow must be reviewed by someone with clinical or crisis-line experience before any real student uses BridgeIt.
- No accounts and no stored intake answers. Outreach drafts share only the type of help, insurance and availability, never symptoms. An email is collected only if the student opts in to follow-up.

## 6 · Release plan

*\[Release plan diagram: see BridgeIt_PRD.pdf\]*

| Phase                   | Purpose                                                   | Gate to move on                                                                                                      |
|-------------------------|-----------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------|
| Prototype               | Clickable demo of the core flow on a small seed directory | Core flow works end to end; labeled as a demo                                                                        |
| Beta release            | A small invited group of UCLA students uses BridgeIt      | Before launch: directory verified, crisis flow reviewed, no personal data stored, matching tested on sample profiles |
| User testing & research | Interviews and usability tests with beta users            | Enough sessions to see clear patterns                                                                                |
| Iterate                 | Revise questions, matching and outreach based on findings | Intake completion and match benchmarks met in testing                                                                |
| UCLA pilot              | Open to UCLA students more widely                         | North star reviewed alongside safety, accuracy and feedback before any expansion                                     |

### Learning plan

- **Discovery interviews** with UCLA students who have looked for support, to refine the persona and the intake questions.
- **One versus several:** compare a single recommendation with a short list of three.
- **Usability tests** of the intake and outreach steps: time to complete and ease rating.
- **Topic question:** in interviews, test whether students want to share what they need support with, and whether it would change which resource fits. Add it only once listings are tagged with verified specialties.
- **Outcome check:** measure whether students actually initiate contact, then revise this PRD with what we learn.

## 7 · Open questions

| Area             | Decision needed                                                                                                                                                                                                                                                                                                          |
|------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Data accuracy    | How can the directory stay verified at about 5–10 hours of upkeep a week, and what is the minimum size for a useful beta?                                                                                                                                                                                                |
| Safety review    | Who reviews the crisis wording and flow before the beta, and what must they approve?                                                                                                                                                                                                                                     |
| Matching quality | Which intake questions most improve the match, and which can be dropped or made optional?                                                                                                                                                                                                                                |
| Topic question   | Would an optional, non-diagnostic question about what students want support with (for example, stress, grief or relationships) improve match quality enough to justify the privacy and safety tradeoff? If added, it would only rank results, never filter them, and would never appear in outreach drafts or be stored. |
| User preference  | Do students prefer one recommendation or a short list?                                                                                                                                                                                                                                                                   |
| Privacy          | Where is a follow-up email address stored, and is it deleted right after the day-14 check-in?                                                                                                                                                                                                                            |

## 8 · Changelog

- **0.2 · November 2026 (after building the prototype).** Renamed the card button “Contact them.” Added rules to show the listed price, upfront fees and budget separately, keep posted hours separate from confirmed openings, and recommend only free or possibly free options for a \$0 budget, after a review found a \$30 budget matched to a clinic with a \$40 intake fee. Labeled results “Your top match based on your preferences.” Added an optional LGBTQ+-affirming priority. Reworded the directory scope to 20–30 verified listings across CAPS, therapy and peer support (29 live in the prototype). Added a “report a problem” button to Later.
- **0.1 · November 2026.** First draft.

### Sources

1.  Off-campus referral study, *Journal of College Student Psychotherapy*, vol. 22, no. 2. doi:10.1300/J035v22n02_03
2.  Mehr, Daltry & Silbert, “Clinical case management & referral success outcomes,” *Journal of American College Health*, 73(1), 2025. doi:10.1080/07448481.2023.2182601
3.  UC Regents, Annual Report on Student Health and Counseling Centers and UC SHIP, March 2025.
4.  UC Regents Health Services Committee, item H4, “Student Health Services at a Crossroads,” March 18, 2025.
5.  UCLA CAPS: counseling.ucla.edu (session limits, UC SHIP referral rules, fees), checked November 2026.

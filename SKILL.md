Markdown · SKILL.md

# Screener Builder

---

## name: screener-builder description: Draft professional recruitment screeners for consumer (B2C) market research and UX research studies, in English and the local languages of 11 markets (US, Canada, UK, France, Germany, Australia, India, China, Brazil, Japan, South Korea). Applies quota notation, terminate logic, industry security screens, disguise techniques, and country-specific demographic and income banks. The user can paste their recruitment criteria and get a complete draft (15 questions max) in one pass. Use whenever the user asks to create, draft, review, revise, or translate a screener, recruitment questionnaire, participant qualification survey, or the screening section of a survey — for interviews, focus groups, usability tests, in-home visits, diary studies, or quant surveys. Also use when the user mentions quotas, terminates, incidence, panel recruitment, or qualifying respondents, even without the word "screener". Output is a Word (.docx) document unless the user asks otherwise.

Drafts recruitment screeners with a consistent, programmer-ready structure: a Specification block, a funnel-structured question flow, routing notes on every option, and built-in data-quality and disguise techniques.

**Best fit:** consumer (B2C) studies — people screened on demographics, household, product ownership, brand use, and purchase behavior. For B2B studies, the job, industry, and seniority questions still work, but the bank has no firmographics (company size, revenue, purchase authority). Tell the user and draft those questions with them.

**Markets:** US, Canada, UK, France, Germany, Australia, India, China, Brazil, Japan, South Korea. Each has its own income question, geography unit, and language conventions in the reference files.

## Appendices in this file

Everything this skill needs is in this one file:

- **Appendix A — Question Bank:** standard questions for every section, including market-specific versions of ethnicity, education, and income. Always pull standard questions from here instead of writing new ones.
- **Appendix B — Localization Guide:** read for any non-US or multi-language study. Covers translation workflow, market conventions, privacy laws, and a glossary of standard strings.
- **Appendix C — QA Checklist:** run before delivery.

## Boundaries

Check every request against these before drafting.

### Never do — rewrite or decline that part, and tell the user why

1. **No selling under the guise of research.** A screener recruits research participants only. Do not build one that collects leads, sells, or promotes a product. This is prohibited by research industry codes such as ESOMAR, the Insights Association, and the MRS.
2. **No misleading respondents about what taking part involves.** Hiding the sponsor is fine. Hiding recording, a home visit, a pre-task, sharing data with a third party, or the time required is not.
3. **No requirement to buy anything** in order to qualify or take part.
4. **No incentive tied to giving a particular opinion.** Incentives depend on qualifying and completing, never on what the respondent says.
5. **No unneeded sensitive or identifying data.** Never ask for government ID numbers, bank or card details, passwords, or a full home address before the respondent qualifies. Ask health, religion, sexual orientation, political views, or ethnicity only when the brief needs it as a quota or study topic, with "Prefer not to answer" and a consent line. Never ask ethnicity in France.
6. **No exclusion based on protected characteristics without a research reason.** Quotas for a balanced or representative sample are fine. An instruction like "exclude \[ethnic group / religion / disability\]" with no study rationale is not. Ask for the reason. Where possible, screen on what the study really needs (e.g., "Can you join a 60-minute video call?") instead of on the characteristic.
7. **No minors as direct respondents.** The skill always terminates under-18s (under-19s in South Korea). If the study involves children, screen the parent or guardian, add a guardian-consent step, and flag that the study needs ethics review and a child-research protocol.

### Flag and ask — draft anyway, but raise it with the user

- **Vulnerable groups** (patients, people in financial hardship, people who are recently bereaved, people with cognitive impairment): add sensitive wording and flag that extra ethics review may be needed.
- **Very low incidence** (e.g., owners of one new device model in one city): warn the user that recruitment may be slow or costly, and suggest which criteria could be relaxed.
- **Criteria that conflict** (e.g., "heavy users" and "used less than once a month"): list the conflict and draft the most likely reading.
- **A brief that reveals the sponsor** if asked as written: rewrite the question to disguise the sponsor, and explain the change.

### Out of scope — say so if asked

- Clinical trial or medical eligibility screening (regulated, and needs IRB-approved, medically reviewed criteria).
- Employment, housing, credit, or insurance decisions about people.
- Programming the screener in a survey platform, or managing live quotas.
- B2B firmographic screening beyond job, industry, and seniority (see Best fit above).

## Step 1 — Read the recruitment criteria and draft immediately

The user should be able to paste their recruitment criteria and get a complete screener back. **Do not stop to ask questions before drafting.** Fill any gaps with the defaults below, and list every assumption in an "Assumptions and open items" box at the top of the Specification block and in the chat reply. Ask before drafting only when there are no target criteria at all, or when the request crosses a "Never do" boundary.

Extract these from the criteria:

| Item | What to look for | Default if missing |
| --- | --- | --- |
| Method | Interview, focus group, usability test, in-home, diary, quant | Remote 1:1 interview, 60 minutes |
| Market and language | Countries, regions, cities; respondent language | Infer from the request (e.g., a US city → US); otherwise US, English. Language per Appendix B |
| Sample | Total N, groups, N per group, quotas | `[TBC: N]`; no quotas except a natural mix |
| Target profile | Ownership, usage frequency, purchase recency, brand or model, decision role, behaviors | Required — ask if there is none |
| Exclusions | Industries, competitor employees | Standard security screen (market research, advertising/PR, media, client's industry) |
| Incidence | How narrow the profile is | Add authenticity checks if the target is a specific product or model owner |
| Incentive and commitment | Amount, pre-tasks, recording | `[INCENTIVE]` placeholder; recording disclosed |
| Recruitment channel | Platform or panel | General panel: ask the needed demographics in the screener |

Notes:

- **Sponsor:** never reveal the sponsor brand or make it guessable.
- **Past participation:** recruitment panels usually enforce their own limits. Add a past-participation question only if the user asks for one.
- **Platforms with profile data** (e.g., User Interviews, Respondent, Prolific, panel vendors): if the user names one, do not re-ask demographics the platform can filter. Check which profile fields that platform currently offers rather than assuming. Move those quotas into the Specification block as platform-side targeting notes (e.g., "Set on platform: 60% female; household income $75,000+"). Keep only questions the platform can't filter: category behavior, brand, frequency, security screen, authenticity checks.

## Step 2 — Screener architecture

**Question budget: target 8-12 questions; hard maximum 15.** About 3 minutes to complete. A screener only filters; it is not the main survey. Count every numbered question, including commitment and consent questions. The contact-details block does not count.

Before writing questions, map each criterion to the question that enforces it. If the plan goes over 15, cut in this order until it fits:

1. Drop profiling questions that don't screen anyone out and aren't quota'd (e.g., education or marital status "for context").
2. Move demographics to platform-side targeting if the recruitment platform can filter them.
3. Merge questions that can share one list (e.g., category ownership and brand in one multi-select, when the brief allows).
4. Drop the optional articulation check.
5. Move "nice to know" questions into the main survey or discussion guide.

Never cut the security screen, a must-have criterion, or a required consent question. If the screener still can't fit in 15, deliver the 15-question version and list the criteria that didn't fit, with a suggestion for where each should go.

**Sensitivity funnel:** start with broad, low-sensitivity questions. Put the core behavior filters in the middle. Put private questions (income, and only if a quota needs it) and contact details at the very end.

**Simplicity rules:**

- **Single select or multi-select only.** No grids, rankings, rating scales, or essay questions. Open fields are allowed only for contact details and short verification answers (purchase date, price paid).
- **No skip logic unless a screening condition requires it.** Default to a linear flow where everyone sees every question. Use `→ [Terminate]` and `→ [Must Select]` instead of `→ [Jump to QN]`. Group-conditional questions in multi-group designs are the accepted exception. Because of this rule, every question must have an option everyone can choose (e.g., "I am not currently working").

**Document order** (skip sections that don't apply):

1. **Specification block** — titled "Specification", marked as not shown to respondents:
   - Target markets and sample size per market or group, with the total in bold
   - Demographics and quotas
   - Key respondent profile, with question references (e.g., "Q9 = Target brand")
   - Exclusion criteria
   - Platform-side targeting notes, if any
2. **Welcome / consent intro** — neutral study purpose (never the sponsor), about 3 minutes, confidentiality, incentive eligibility. Template in Appendix A.
3. **Geography** — country, then the market's region unit if the brief restricts location. Bold target locations; terminate the rest.
4. **Demographics** — gender → age → ethnicity (only if quota'd, and only in markets where it is allowed) → education, employment, household as needed.
   - **Gender:** use the inclusive option set from the bank. Do not terminate any gender option by default. Terminate only for a hard quota the brief requires, and state the reason in the Specification block.
   - **Age:** use the bank's bands. Terminate out-of-range bands, "Under 18" (Under 19 in South Korea), and "Prefer not to answer".
   - Attach quotas at option level: `→ [Hard Quota: 60%]`, `→ [Soft Quota: at least 35%]`.
5. **Security screen** — multi-select. Respondent, household, family, or close friends; now or in the past 2 years. Always terminate market research, advertising/marketing/PR, media, and the client's industry plus adjacent categories. Always include 3-5 decoy industries that do not terminate, plus "None of the above".
6. **Category behavior funnel** — broad to specific, with the target hidden.
   - Never ask a transparent yes/no qualifying question ("Have you used \[our app\] in the past month?"). The right answer is obvious and invites faking. Use multi-select lists instead.
   - Category ownership or behavior (Select all that apply), target marked `→ [Must Select]`, "None of the above → \[Terminate\]".
   - Brand list with all major competitors in that market, target `→ [Must Select]`.
   - Model or variant if relevant.
   - Mark brand and category lists `[Randomize]`, anchoring "None", "Other", and "Not sure" at the bottom.
   - Insert a gateway note when logic shifts: "THE FOLLOWING IS ONLY FOR PEOPLE WHO PASS THE ABOVE QUESTIONS".
7. **Authenticity checks** (low-incidence or device-owner studies) — how acquired (terminate gifts, review units, employer-provided), when acquired, price paid, and usage frequency (terminate "Less than once a month" and "Not currently using" if the brief needs active users).
8. **Trap questions — propose, don't auto-add.** For each new project, design 1-2 candidate traps and present them to the user separately from the draft, asking whether to add them. Insert only after the user confirms. Candidate types: an impossible-behavior item ("I have used all of the above every day"), a low-plausibility frequency claim, or an attention instruction ("For this question, please select 'Other'"). Keep traps in the same tone as real options.
9. **Attitude or segmentation question** — only if the brief requires a mindset filter.
10. **Articulation check** (qualitative only, optional) — one open question, e.g., "In 2-3 sentences, describe the last time you \[target behavior\]." It screens out low-effort and AI-generated answers. Propose it and include only if the user confirms.
11. **Commitment and consent** (qualitative) — describe the session, recording, pre-task, and incentive, each with `No → [Terminate]`.
12. **Household income** — only if a quota requires it. Use the market's own version from Appendix A.
13. **Contact details and close** — name, email, phone (with country code); next steps and timeline; thank both qualified and terminated respondents. Add a privacy notice line in markets that require it.

## Step 3 — Notation and formatting conventions

- **Plain survey English:** short, direct questions with one idea each, everyday words, and no preamble.
  - ✓ "How old are you?" / "Which of these brands do you currently use?"
  - ✗ "We would like to know a little bit about you. Could you please indicate which of the following age categories you fall into?"
  - Cut every word that doesn't change the answer.
- **Question text** in bold, followed by a format tag: `[Single select]`, `(Select all that apply)`, or an open field `______`.
- **Options** as plain bullets. Routing and quotas are appended with an arrow: `→ [Terminate]`, `→ [Must Select]`, `→ [Hard Quota: 60%]`, `→ [Soft Quota: 50%]`.
- **Programmer notes** go in square brackets on their own line: `[Question for Group 1 only]`, `[Randomize]`, `(US and Canada only)`.
- **Bold the qualifying options** inside lists. This is a cue for the programmer; note in the Specification block that bold must not appear in the programmed survey.
- **Flat numbering only:** 1, 2, 3... Never sub-numbers such as 1.2. A follow-up question gets its own number.
- **Section headers** in bold italics: ***Geography***, ***Demographics***, ***Sensitive industries***, ***\[Category\] behavior***.
- **"Other (please specify): \_\_\_\_\_\_"** and **"Prefer not to answer"** where appropriate. In screeners, "Prefer not to answer" on age terminates; on gender it does not.
- **MECE options:** ranges must not overlap ("1-3 years / 3-5 years" ✗) or leave gaps. Write numeric ranges in compact form: "18-24 / 25-34", "$25,000-$49,999". Never use wordy boundaries such as "18 (inclusive) to under 39". For continuous amounts, use "Under 1 year / 1-2 years / 3-5 years / More than 5 years". For non-universal behaviors, include "None of the above" or "Not sure".
- **Neutral wording:** never put the desired answer or the research motive in the question.
  - ✗ "To improve our investing features, do you like managing money on your phone?"
  - ✓ "Which of the following do you currently use to manage your personal finances? (Select all that apply)"

## Step 4 — Localization (non-US or multi-language studies)

Follow Appendix B:

1. Draft and confirm the English master.
2. Swap in market versions of income, geography, education, ethnicity, and brand lists.
3. Translate respondent-facing text into the market language. Keep programmer notes in English unless the user asks otherwise.
4. Keep question numbers identical across languages.
5. Deliver one file per language, each with a note asking for review by a native-speaking researcher before fielding.

## Step 5 — QA before delivery

Run Appendix C. Minimum bar:

- every path ends in qualify or terminate;
- no question reveals the sponsor;
- quotas add up;
- terminates match the Specification block;
- numbering is sequential;
- every question has a format tag;
- no respondent is stuck on a question that doesn't apply to them.

## Step 6 — Output

Produce a .docx file (use a docx skill or the docx library if available; otherwise deliver Markdown in the same notation and say so):

- US Letter (or A4 for markets outside North America if the user prefers), Arial, 11-12pt body
- Title: "\[Project\] — Screener V1" (version per brief). Use a project codename if the file goes to vendors who should not know the client.
- Specification block first, then the screener questions
- Bold runs for question text and qualifying options; real Word bullets, never typed bullet characters
- File name: `{Project}_Screener_V{n}.docx`, or `{Project}_Screener_{LANG}_V{n}.docx` for language versions

After delivering, give the user a short reply listing:

- the assumptions made, and any `[TBC]` items;
- criteria that didn't fit the 15-question budget, if any, and where they could go;
- anything flagged under Boundaries;
- the proposed trap questions, and the articulation check for qualitative studies, for the user to accept or decline.

---

## Appendix A — Question Bank

Standard, ready-to-use screener questions for consumer (B2C) studies. Always pull demographic and standard screening questions from this appendix instead of writing them from scratch, then adapt the placeholders to the study.

**Markets covered:** United States, Canada, United Kingdom, France, Germany, Australia, India, China, Brazil, Japan, South Korea. Market-specific versions are labeled (e.g., *US*, *UK*). For language, geography units, and local conventions, see Appendix B.

**Placeholders:** `[CATEGORY]` product or service category · `[PRODUCT]` specific product · `[N]` a number · `[DATES]` fieldwork dates · `[INCENTIVE]` amount and currency · `[CITY A]` a target location. Replace every placeholder before delivery.

**Notation:** question text in bold, followed by a format tag. Routing is appended to options with an arrow: `→ [Terminate]`, `→ [Must Select]`, `→ [Hard Quota: 50%]`. Programmer-only notes sit in square brackets on their own line.

---

### 1. Welcome / consent intro

> Thank you for your interest in this study. We are looking for people to take part in a research study about \[neutral topic, e.g., "everyday household routines"\]. This short questionnaire takes about 3 minutes. Your answers are confidential and will only be used to check whether you are a good fit for the study. If you qualify and complete the study, you will receive \[INCENTIVE\].

Never name the sponsor, the brand, or the exact product in the intro.

---

### 2. Geography

**Which country do you live in?** \[Single select\]

- \[Target country A\]
- \[Target country B\]
- Other country → \[Terminate\]

**Which \[state / province / region / city\] do you live in?** \[Single select\]

\[Use the geography unit for the market from Appendix B. List target locations in bold; terminate non-target locations.\]

- **\[CITY A\]**
- **\[CITY B\]**
- \[Non-target location\] → \[Terminate\]
- Other → \[Terminate\]

---

### 3. Gender

**What is your gender?** \[Single select\]

- Male
- Female
- Non-binary
- Prefer to self-describe: \_\_\_\_\_\_
- Prefer not to answer

\[Do not terminate any option by default. If the study has a hard gender quota, state in the Specification block how options outside the quota are handled, and why.\]

---

### 4. Age

**How old are you?** \[Single select\]

- Under 18 → \[Terminate\]
- 18-24
- 25-34
- 35-44
- 45-54
- 55-64
- 65-74
- 75 or older
- Prefer not to answer → \[Terminate\]

\[Terminate bands outside the target range. If the study needs finer bands, use 5-year bands: 18-24 / 25-29 / 30-34 / ... South Korea: the age of majority is 19 — use "Under 19 → \[Terminate\]" and start the first band at 19.\]

---

### 5. Ethnicity (North America and Europe only)

Ask only when the study has an ethnicity quota or diversity requirement. Under GDPR / UK GDPR, ethnic origin is special-category data: collect it only with explicit consent and a clear purpose.

#### US

**Which of the following describe you? (Select all that apply)**

- American Indian or Alaska Native
- Asian
- Black or African American
- Hispanic or Latino
- Middle Eastern or North African
- Native Hawaiian or Pacific Islander
- White
- Other (please specify): \_\_\_\_\_\_
- Prefer not to answer

#### Canada

**Which of the following describe you? (Select all that apply)**

- White
- South Asian (e.g., East Indian, Pakistani, Sri Lankan)
- Chinese
- Black
- Filipino
- Arab
- Latin American
- Southeast Asian (e.g., Vietnamese, Cambodian, Thai)
- West Asian (e.g., Iranian, Afghan)
- Korean
- Japanese
- Indigenous (First Nations, Métis, or Inuk/Inuit)
- Other (please specify): \_\_\_\_\_\_
- Prefer not to answer

#### UK

**Which of the following best describes your ethnic group?** \[Single select\]

- Asian or Asian British
- Black, Black British, Caribbean or African
- Mixed or multiple ethnic groups
- White
- Other ethnic group (please specify): \_\_\_\_\_\_
- Prefer not to answer

#### France

Do not ask about ethnic or racial origin. French law strictly limits collecting this data. If the brief needs a diversity measure, ask about country of birth instead (below), and confirm with the client's legal or privacy team first.

#### Germany

Ethnicity is not a standard survey measure. If the brief needs a diversity measure, use migration background:

**Were you, or at least one of your parents, born outside Germany?** \[Single select\]

- Yes
- No
- Prefer not to answer

#### France (alternative) and other European countries

**In which country were you born?** \[Single select\]

- \[Survey country\]
- Another country in Europe
- A country outside Europe
- Prefer not to answer

---

### 6. Education

#### US

**What is the highest level of education you have completed?** \[Single select\]

- Less than high school
- High school diploma or equivalent
- Some college, no degree
- Associate degree
- Bachelor's degree
- Master's degree
- Doctorate or professional degree
- Prefer not to answer

#### International (all other markets)

**What is the highest level of education you have completed?** \[Single select\]

\[Localize labels to the national system — e.g., GCSE / A-level (UK), Baccalauréat (FR), Abitur / Ausbildung (DE), 高中 / 大专 (CN).\]

- Primary school or less
- Lower secondary school
- Upper secondary / high school
- Vocational or technical qualification
- Some university, no degree
- Bachelor's degree or equivalent
- Master's degree or equivalent
- Doctorate
- Prefer not to answer

---

### 7. Employment status

**Which of the following best describes your main current situation?** \[Single select\]

- Employed full-time
- Employed part-time
- Self-employed / business owner
- Student
- Homemaker or full-time caregiver
- Retired
- Not working, looking for work
- Not working, not looking for work
- Other (please specify): \_\_\_\_\_\_
- Prefer not to answer

\[US option if relevant: "Active-duty military". For questions 8-10, everyone answers — respondents not working choose the "not currently working" option instead of being skipped.\]

---

### 8. Industry

**Which industry do you mainly work in?** \[Single select\]

- Agriculture / farming
- Construction / engineering
- Education / training
- Energy / utilities
- Finance / banking / insurance
- Government / public sector
- Healthcare / medical services
- Hospitality / tourism / food service
- Manufacturing
- Media / entertainment
- Nonprofit / charity
- Professional services (legal, consulting, accounting)
- Real estate
- Retail / wholesale
- Technology / IT / telecommunications
- Transportation / logistics
- Other (please specify): \_\_\_\_\_\_
- I am not currently working (retired, student, homemaker, or between jobs)
- Prefer not to answer

\[This is a profiling question. For excluding sensitive industries, use the security screen in section 14.\]

---

### 9. Job function

**Which of the following best describes your main job function?** \[Single select\]

- Management / executive leadership
- Sales / business development
- Marketing / communications
- Operations / administration
- Customer service / support
- Engineering / technical
- IT / software development
- Product / design / creative
- Research / analytics
- Finance / accounting
- Human resources
- Legal / compliance
- Healthcare practitioner
- Teaching / education
- Skilled trade / manual work
- Other (please specify): \_\_\_\_\_\_
- I am not currently working
- Prefer not to answer

---

### 10. Seniority

**Which of the following best describes your current job level?** \[Single select\]

- Entry-level / junior
- Mid-level (experienced, no direct reports)
- Senior or expert individual contributor (no direct reports)
- Manager / supervisor (has direct reports)
- Senior manager / director
- Vice president / head of department
- C-level executive, owner, or partner
- Self-employed / freelancer
- I am not currently working
- Prefer not to answer

---

### 11. Marital status

**What is your marital status?** \[Single select\]

- Single, never married
- Married or in a civil partnership
- Living with a partner
- Separated or divorced
- Widowed
- Prefer not to answer

---

### 12. Household size

**How many people live in your household, including yourself?** \[Single select\]

- 1
- 2
- 3
- 4
- 5
- 6 or more

---

### 13. Children in household

**How many children under 18 live in your household?** \[Single select\]

- None
- 1
- 2
- 3
- 4 or more

---

### 14. Security screen (sensitive industries)

**Do you, or does anyone in your household, your family, or your close friends, work now or in the past 2 years in any of the following industries? (Select all that apply)**

\[Randomize. Anchor "None of the above" at the bottom.\]

- Market research, user research, or survey panels → \[Terminate\]
- Advertising, marketing, or public relations → \[Terminate\]
- Media, journalism, or publishing → \[Terminate\]
- \[Client's industry, e.g., "Manufacturing or selling \[CATEGORY\]"\] → \[Terminate\]
- \[Adjacent category, e.g., "Retail of \[CATEGORY\]"\] → \[Terminate\]
- Healthcare
- Education
- Banking or financial services
- Transportation or logistics
- Hospitality or food service
- None of the above

\[Keep 3-5 decoy industries that do not terminate, so the target industries are not obvious.\]

---

### 15. Category behavior

**Which of the following do you currently own or use? (Select all that apply)**

\[Randomize. Anchor "None of the above".\]

- **\[TARGET CATEGORY\]** → \[Must Select\]
- \[Other category\]
- \[Other category\]
- \[Other category\]
- None of the above → \[Terminate\]

**Which of the following brands of \[CATEGORY\] do you currently use? (Select all that apply)**

\[Randomize. Include all major competitors in the market — brand sets differ by country. Anchor "Other" and "Not sure".\]

- **\[TARGET BRAND\]** → \[Must Select\]
- \[Competitor A\]
- \[Competitor B\]
- \[Competitor C\]
- Other (please specify): \_\_\_\_\_\_
- Not sure → \[Terminate\]

**When did you last purchase \[CATEGORY\]?** \[Single select\]

- Within the past week
- 1-4 weeks ago
- 1-3 months ago
- 4-6 months ago
- More than 6 months ago
- Never → \[Terminate\]

\[Terminate options outside the target recency window.\]

**How often do you use \[CATEGORY\]?** \[Single select\]

- Every day
- Several times a week
- About once a week
- A few times a month
- About once a month
- Less than once a month → \[Terminate\]
- Not currently using → \[Terminate\]

**Which of the following best describes your role in choosing \[CATEGORY\] for your household?** \[Single select\]

- I make the decision myself
- I share the decision with someone else
- Someone else usually decides → \[Terminate\]
- I am not involved → \[Terminate\]

---

### 16. Authenticity checks (low-incidence or device-owner studies)

**How did you get your \[PRODUCT\]?** \[Single select\]

- I bought it myself
- Someone in my household bought it
- It was a gift → \[Terminate\]
- It was provided by my employer → \[Terminate\]
- I received it for free to review or test → \[Terminate\]
- Other (please specify): \_\_\_\_\_\_

**When did you get your \[PRODUCT\]? (Month and year)** \_\_\_\_\_\_

**About how much did you pay for it?** \_\_\_\_\_\_

---

### 17. Willingness for research activities

#### In-home visit

**This study involves a researcher visiting your home for about \[N\] minutes to talk about \[neutral topic\] and see how you \[activity\]. With your permission, photos or video of the relevant areas may be taken. Are you comfortable with this?** \[Single select\]

- Yes
- Maybe — I need more information → \[Terminate\]
- No → \[Terminate\]

#### Remote video session

**This study is a \[N\]-minute video call. You will need a computer or phone with a working camera and microphone, and a quiet place to talk. The session will be recorded for research purposes only. Are you comfortable with this?** \[Single select\]

- Yes
- No → \[Terminate\]

#### Pre-task

**Before the session, you will be asked to complete a short task: \[describe, e.g., "take 3 photos of where you store \[CATEGORY\]"\]. This takes about \[N\] minutes and adds \[INCENTIVE\] to your incentive. Are you willing to do this?** \[Single select\]

- Yes
- No → \[Terminate\]

---

### 18. Scheduling availability

**Which of the following times would you be available for a \[N\]-minute session between \[DATES\]? (Select all that apply)**

\[Provide time blocks in the respondent's local time zone.\]

- \[Day, date\] — \[time block\]
- \[Day, date\] — \[time block\]
- None of these times work for me → \[Terminate\]

---

### 19. Articulation check (qualitative, optional)

\[Propose to the user before including.\]

**In 2-3 sentences, please describe the last time you \[target behavior\].**

---

\[Programmer / recruiter note: Disqualify answers that are very short, off-topic, incoherent, or appear copied or AI-generated.\]

---

### 20. Household income (ask near the end, only if a quota requires it)

**What is your total annual household income before tax?** \[Single select\] — wording changes by market; use the version below.

All bands are suggested starting points anchored on recent national income levels. Check them against the latest national statistics for the quota you need before fielding. Always add "Prefer not to answer" as the last option.

#### US — annual, before tax (USD)

- Under $25,000
- $25,000-$49,999
- $50,000-$74,999
- $75,000-$99,999
- $100,000-$124,999
- $125,000-$149,999
- $150,000-$199,999
- $200,000-$249,999
- $250,000 or more

#### Canada — annual, before tax (CAD)

- Under $25,000
- $25,000-$49,999
- $50,000-$74,999
- $75,000-$99,999
- $100,000-$149,999
- $150,000-$199,999
- $200,000 or more

#### UK — annual, before tax (GBP)

- Under £15,000
- £15,000-£24,999
- £25,000-£34,999
- £35,000-£49,999
- £50,000-£74,999
- £75,000-£99,999
- £100,000-£149,999
- £150,000 or more

#### France — monthly, after tax (EUR)

Ask: **"What is your household's total monthly net income?"** — French surveys usually ask monthly net income.

- Under €1,500
- €1,500-€2,499
- €2,500-€3,499
- €3,500-€4,999
- €5,000-€6,999
- €7,000 or more

#### Germany — monthly, after tax (EUR)

Ask: **"What is your household's total monthly net income?"** (Haushaltsnettoeinkommen) — the German standard.

- Under €1,500
- €1,500-€2,499
- €2,500-€3,499
- €3,500-€4,499
- €4,500-€5,999
- €6,000 or more

#### Australia — annual, before tax (AUD)

- Under $40,000
- $40,000-$79,999
- $80,000-$119,999
- $120,000-$159,999
- $160,000-$199,999
- $200,000-$249,999
- $250,000 or more

#### India — annual (INR)

Many Indian consumer studies classify respondents with NCCS (New Consumer Classification System, based on the chief earner's education and household durables) instead of income. Ask the user which one the brief needs. Income version:

- Under ₹3,00,000
- ₹3,00,000-₹5,99,999
- ₹6,00,000-₹9,99,999
- ₹10,00,000-₹19,99,999
- ₹20,00,000-₹49,99,999
- ₹50,00,000 or more

#### China — monthly, after tax (RMB)

Ask: **"What is your household's total monthly income after tax?"** — the usual Chinese convention. Income levels vary widely by city tier; set quotas per tier.

- Under RMB 5,000
- RMB 5,000-9,999
- RMB 10,000-14,999
- RMB 15,000-19,999
- RMB 20,000-29,999
- RMB 30,000-49,999
- RMB 50,000 or more

#### Brazil — monthly (BRL)

Brazilian studies usually classify respondents with Critério Brasil (ABEP socioeconomic classes A, B1, B2, C1, C2, D-E) instead of income. Ask the user which one the brief needs. Income version:

- Under R$2,000
- R$2,000-R$3,999
- R$4,000-R$7,999
- R$8,000-R$14,999
- R$15,000-R$24,999
- R$25,000 or more

#### Japan — annual, before tax (JPY)

- Under ¥2,000,000
- ¥2,000,000-¥3,999,999
- ¥4,000,000-¥5,999,999
- ¥6,000,000-¥7,999,999
- ¥8,000,000-¥9,999,999
- ¥10,000,000-¥14,999,999
- ¥15,000,000 or more

\[In Japanese, write bands in 万円 units, e.g., 200万円未満 / 200万〜399万円.\]

#### South Korea — monthly, before tax (KRW)

Ask: **"What is your household's total monthly income before tax?"** — the usual Korean convention.

- Under ₩2,000,000
- ₩2,000,000-₩2,999,999
- ₩3,000,000-₩3,999,999
- ₩4,000,000-₩4,999,999
- ₩5,000,000-₩6,999,999
- ₩7,000,000-₩9,999,999
- ₩10,000,000 or more

\[In Korean, write bands in 만원 units, e.g., 200만원 미만 / 200만\~299만원.\]

---

### 21. Contact details and close

**Please share your contact details so we can schedule your session.**

- First name: \_\_\_\_\_\_
- Last name / family name: \_\_\_\_\_\_
- Email: \_\_\_\_\_\_
- Phone (with country code): \_\_\_\_\_\_

\[Collect only what the recruiter needs. In China, Japan, and South Korea, list family name first.\]

**Qualified close:**

> Thank you! You may be a good fit for this study. A member of our team will contact you within \[N\] business days to confirm a time.

**Terminate close:**

> Thank you for your time. Unfortunately, you do not match the profile we need for this study. We appreciate your interest.

---

## Appendix B — Localization Guide

Use this file when a screener runs outside the US, or in more than one market or language.

### Workflow

1. **Draft the master screener in English first.** Get the user to confirm the logic, quotas, and terminates on the English version.
2. **Localize, don't just translate.** Swap in the market's geography unit, income question, brand list, and education labels from Appendix A. A competitor set that works in the US is usually wrong in Japan or Brazil.
3. **Translate respondent-facing text** into the target language: intro, questions, options, format tags such as "Select all that apply", and closing messages.
4. **Keep programmer notes in English** by default: `→ [Terminate]`, `→ [Must Select]`, quotas, `[Randomize]`, and bracketed instructions. This lets one programming or QA team check every language version. Translate them only if the user asks.
5. **Keep question numbers identical** across languages so versions can be compared line by line.
6. **One file per language**, named `{Project}_Screener_{LANG}_V{n}.docx` (e.g., `_FR_`, `_JA_`).
7. **Flag for native-speaker review.** Add a note at the top of every translated file: "Translation drafted with AI — review by a native-speaking researcher before fielding."

### Market reference

| Market | Respondent language | Geography unit | Income convention | Privacy law to respect | Notes |
| --- | --- | --- | --- | --- | --- |
| United States | English (Spanish if the quota includes Spanish-dominant respondents) | State; metro area | Annual, before tax | State privacy laws (e.g., CCPA in California) | Ethnicity: US version in question bank |
| Canada | English; Canadian French for Quebec | Province / territory | Annual, before tax | PIPEDA; Quebec Law 25 | Ethnicity: Canada version |
| United Kingdom | English (UK spelling) | Nation (England, Scotland, Wales, Northern Ireland); English region | Annual, before tax | UK GDPR | Ethnicity: UK version |
| France | French (formal *vous*) | Région; Île-de-France vs. rest of France is a common split | Monthly, net | GDPR | Do not ask ethnicity |
| Germany | German (formal *Sie*) | Bundesland; Nielsen areas are common in market research | Monthly, net | GDPR | Use migration background, not ethnicity |
| Australia | English (Australian spelling) | State / territory; capital city vs. rest of state | Annual, before tax | Privacy Act 1988 |  |
| India | English for urban online panels; Hindi or regional languages if the sample needs them | City; metro / Tier 1 / Tier 2 | Annual; or NCCS classification | DPDP Act 2023 | Indian digit grouping (₹3,00,000) |
| China | Simplified Chinese | City and city tier (Tier 1, new Tier 1, Tier 2...) | Monthly, after tax | PIPL | Mobile number or WeChat ID for contact |
| Brazil | Brazilian Portuguese | State; region (Sudeste, Sul, Nordeste...) | Monthly; or Critério Brasil class | LGPD | Number format R$ 2.000,00 |
| Japan | Japanese (polite *desu/masu* form) | Prefecture; Kanto / Kansai area | Annual, before tax, in 万円 | APPI | Family name first |
| South Korea | Korean (formal polite register) | Metropolitan city / province (시/도) | Monthly, before tax, in 만원 | PIPA | Age of majority is 19; family name first |

### Writing rules for translated screeners

- **Keep the plain register.** The plain-language rule applies in every language. Use short, direct questions with everyday words. Use the polite or formal form the market expects (see table), without extra courtesy phrases.
- **Use local formats.** Follow local conventions for numbers (1,000 vs. 1.000 vs. 1 000), currency symbols, dates, and phone numbers with country code.
- **Keep ranges MECE after conversion.** Never convert currency bands mechanically. Use the market's own bands from Appendix A.
- **Names.** Ask for family name and given name in separate fields. Order follows local custom (family name first in China, Japan, and Korea).
- **Brand names.** Use the name consumers know locally. This can be a local-script or local-market name (e.g., a brand's Chinese name).
- **Consent wording.** Name the purpose of data collection in the intro. In GDPR markets (UK, France, Germany) and under PIPL, LGPD, APPI, PIPA, and DPDP, add a line linking to the recruiter's privacy notice before collecting contact details.

### Glossary of standard respondent-facing strings

Use these for consistency. India and English-speaking markets use the English strings.

| English | French | German | Simplified Chinese | Brazilian Portuguese | Japanese | Korean |
| --- | --- | --- | --- | --- | --- | --- |
| Single select | Une seule réponse possible | Bitte nur eine Antwort auswählen | 单选 | Selecione apenas uma opção | 1つだけお選びください | 하나만 선택해 주세요 |
| Select all that apply | Plusieurs réponses possibles | Mehrfachnennungen möglich | 多选（可选择多项） | Selecione todas as opções que se aplicam | 当てはまるものをすべてお選びください | 해당하는 것을 모두 선택해 주세요 |
| None of the above | Aucune de ces réponses | Nichts davon | 以上都没有 | Nenhuma das anteriores | 当てはまるものはない | 해당 사항 없음 |
| Other (please specify) | Autre (veuillez préciser) | Sonstiges, und zwar: | 其他（请注明） | Outro (especifique) | その他（具体的に） | 기타 (직접 입력) |
| Prefer not to answer | Je préfère ne pas répondre | Keine Angabe | 不愿透露 | Prefiro não responder | 答えたくない | 응답하지 않음 |
| Not sure | Je ne sais pas | Weiß nicht | 不确定 | Não sei | わからない | 잘 모르겠음 |
| Yes / No | Oui / Non | Ja / Nein | 是 / 否 | Sim / Não | はい / いいえ | 예 / 아니요 |

---

## Appendix C — QA Checklist

Run this before delivering any screener. Fix every failed item, or flag it to the user as `[TBC: ...]` if it needs their decision.

### 0. Boundaries

- [ ] Nothing in the screener sells, promotes, or collects sales leads.
- [ ] Recording, home visits, pre-tasks, data sharing, and time required are all disclosed before respondents agree.
- [ ] No purchase is required to qualify, and the incentive does not depend on the respondent's opinions.
- [ ] No government ID, bank or card details, passwords, or full address before qualification.
- [ ] Sensitive data (health, religion, sexual orientation, political views, ethnicity) is asked only if the brief needs it, with "Prefer not to answer".
- [ ] No exclusion on a protected characteristic without a stated research reason.
- [ ] Under-18s (under-19s in South Korea) are terminated. If the study involves children, the screener addresses the parent or guardian and the ethics flag is raised.

### 1. Structure and length

- [ ] Specification block comes first and is marked as not shown to respondents.
- [ ] Sections follow the order in Step 2. Income (if used) and contact details come last.
- [ ] 8-12 questions, about 3 minutes to complete. **No more than 15 numbered questions**, not counting the contact-details block. Every question beyond 12 has a clear screening job.
- [ ] Criteria that didn't fit the budget are listed for the user, with a suggested home (platform targeting, main survey, discussion guide).
- [ ] An "Assumptions and open items" box sits at the top of the Specification block.
- [ ] Flat numbering: 1, 2, 3... No sub-numbers such as 2.1.
- [ ] Every question has a format tag: `[Single select]`, `(Select all that apply)`, or an open field.

### 2. Logic and routing

- [ ] Every path ends in qualify or terminate. Nobody reaches a dead end.
- [ ] Every respondent can answer every question they see. Questions that don't apply to everyone (job, children, product ownership) include an exit option such as "I am not currently working" or "None".
- [ ] Each terminate matches a requirement or exclusion in the Specification block, and each spec requirement is enforced by at least one question.
- [ ] `→ [Must Select]` is used on multi-select qualifiers. Single-select qualifiers terminate the non-qualifying options.
- [ ] No skip logic unless a screening condition requires it. Group-conditional questions are labeled, e.g., `[Question for Group 1 only]`.
- [ ] A gateway note is added where logic shifts: "THE FOLLOWING IS ONLY FOR PEOPLE WHO PASS THE ABOVE QUESTIONS".

### 3. Quota math

- [ ] Quotas within each attribute sum to 100% or to the total N.
- [ ] Per-group counts add up to the bolded total N.
- [ ] Every quota is labeled hard or soft.
- [ ] Quotas set on the recruitment platform (not asked in the screener) are listed in the Specification block as platform-side targeting.
- [ ] Combined quotas are feasible. Flag low-incidence cells, e.g., "65+ AND owns \[new device model\]".

### 4. Option quality

- [ ] Options are MECE: no overlaps (1-3 / 3-5) and no gaps.
- [ ] Numeric ranges use the compact form: 18-24, $25,000-$49,999.
- [ ] Non-universal behaviors include "None of the above" or "Not sure".
- [ ] Sensitive questions include "Prefer not to answer".
- [ ] Lists are short enough to read on a phone (about 10 options; up to about 15 for industry or brand lists).
- [ ] Brand and category lists are marked `[Randomize]`, with "None", "Other", and "Not sure" anchored at the bottom.

### 5. Wording and bias

- [ ] Plain, short questions with one idea each and no preamble.
- [ ] No leading wording and no research motive in the question text.
- [ ] No transparent yes/no qualifying questions ("Do you use \[our product\]?"). Multi-select lists are used instead.
- [ ] Commitment questions describe the task neutrally and do not pressure respondents to say yes.

### 6. Disguise and sponsor protection

- [ ] The intro, question order, and option wording do not reveal the sponsor or the exact product.
- [ ] Brand lists include all major competitors in that market.
- [ ] The security screen includes 3-5 decoy industries that do not terminate.
- [ ] Bolded target options are marked as a programmer cue. They must not appear bold in the programmed survey.
- [ ] The document title uses a project codename if it will go to vendors or recruiters who should not know the client.

### 7. Data quality

- [ ] Low-incidence or device-owner studies include authenticity checks: how acquired, when, and price paid.
- [ ] Trap questions were proposed to the user separately and added only if they confirmed.
- [ ] The articulation check (qualitative) was included only if the user confirmed it.
- [ ] Open fields are limited to contact details and short verification answers.

### 8. Inclusivity and sensitivity

- [ ] Gender uses the inclusive option set and does not terminate by default. Any gender-based terminate is explained in the Specification block.
- [ ] Ethnicity is asked only where the brief requires it, in the right market version, and never in France.
- [ ] Income is asked only if a quota needs it, and it sits near the end.

### 9. Market and language

- [ ] The income question uses the market's own version (period, before/after tax, currency, bands) from Appendix A.
- [ ] Geography uses the market's unit (state, province, prefecture, city tier...).
- [ ] The age minimum matches the local age of majority (19 in South Korea).
- [ ] Brand lists are specific to each market.
- [ ] Translated files keep the same question numbers as the English master and carry the native-speaker review note.
- [ ] A privacy notice line appears before contact details in markets that require it.

### 10. Output

- [ ] .docx file: US Letter (A4 for markets outside North America if the user prefers), Arial 11-12pt, real Word bullets.
- [ ] Title: "\[Project\] — Screener V\[n\]". File name: `{Project}_Screener_{LANG}_V{n}.docx`.
- [ ] All placeholders such as `[CATEGORY]` and `[N]` are replaced, or are marked `[TBC]` and listed for the user.
# uxr-screener-builder

Paste your recruitment criteria, get a complete, programmer-ready screener: 15 questions max, 11 markets, local languages.

Built from real consumer research projects across North America, Europe, and Asia. The skill encodes the conventions an experienced researcher applies, while the researcher keeps every judgment call.

## Why use it

Recruitment screeners look simple, but small mistakes are costly: overlapping answer ranges, a question that gives away the sponsor, a yes/no qualifier that invites faking, or a respondent stuck on a question that doesn't apply to them. This skill drafts screeners that avoid these problems by default.

**What you get:**

- **One-pass drafting.** Paste the recruitment criteria. The skill fills gaps with sensible defaults and lists every assumption for you to confirm, instead of asking a round of questions first.
- **A strict question budget.** Target 8-12 questions, never more than 15. If the criteria don't fit, it tells you what was cut and where it could go instead.
- **Programmer-ready notation.** A Specification block, then questions with routing on every option: `→ [Terminate]`, `→ [Must Select]`, `→ [Hard Quota: 50%]`, `[Randomize]`.
- **Built-in quality and disguise techniques.** A security screen with decoy industries, brand lists that hide the target, authenticity checks for low-incidence profiles, and optional trap questions it proposes but never adds without your approval.
- **11 markets:** US, Canada, UK, France, Germany, Australia, India, China, Brazil, Japan, South Korea. Each has its own income question (period, tax basis, currency, bands), geography unit, ethnicity rules, privacy notes, and local-language output.
- **Clear boundaries.** It will not build a screener that sells under the guise of research, hides what taking part involves, asks for unneeded sensitive data, excludes people on protected characteristics without a research reason, or recruits minors directly.

**Best fit:** consumer (B2C) studies — interviews, focus groups, usability tests, in-home visits, diary studies, and the screening section of quant surveys.

## Example

**You paste:**

> Recruit 12 US adults aged 25-54 who currently subscribe to a meal-kit service and have ordered in the past 6 months. They should cook at home at least 3 times a week and be involved in choosing the service. Even gender split. 60-min remote interviews, $100 incentive.

**You get** a Word document that starts like this (excerpt):

> **Specification** *(not shown to respondents)*
>
> - Market: United States. Sample: **N = 12**, remote 1:1 interviews, 60 minutes
> - Quotas: gender 50% female / 50% male (soft); age 25-54, natural mix across bands
> - Key profile: currently subscribes to a meal-kit service (Q6); ordered in the past 6 months (Q7); cooks at home 3+ times a week (Q8); makes or shares the decision (Q9)
> - Exclusions: market research, advertising/PR, media, food delivery and meal-kit industry (Q5)
>
> **Assumptions and open items:** recruited through a general panel, so demographics are asked in the screener `[TBC: platform]` · incentive $100 as per brief
>
> ---
>
> **3. How old are you?** [Single select]
>
> - Under 18 → [Terminate]
> - 18-24 → [Terminate]
> - 25-34
> - 35-44
> - 45-54
> - 55-64 → [Terminate]
> - 65 or older → [Terminate]
> - Prefer not to answer → [Terminate]
>
> **6. Which of the following food services do you currently use? (Select all that apply)**
>
> [Randomize. Anchor "None of the above".]
>
> - Grocery delivery
> - Restaurant delivery app
> - **Meal-kit subscription** → [Must Select]
> - Prepared-meal delivery
> - Online grocery pickup
> - None of the above → [Terminate]

Then a short note from Claude covering the assumptions to confirm, anything flagged, and 1-2 proposed trap questions for you to accept or decline.

## Install

The whole skill is one file: [`SKILL.md`](./SKILL.md).

- **Claude apps (web and desktop):** download `SKILL.md`, put it in a folder named `screener-builder`, zip the folder, and upload it in Settings under Capabilities → Skills.
- **Claude Code:** save it as `~/.claude/skills/screener-builder/SKILL.md` (personal) or `.claude/skills/screener-builder/SKILL.md` in your project.

Then just ask: *"Draft a screener for…"* followed by your criteria.

## Before you field

- **Income bands** are suggested starting points anchored on recent national income levels. Check them against the latest national statistics for your quota.
- **Translations** are drafted by AI. Have a native-speaking researcher review every language version.
- The skill drafts the screener. It does not program it in a survey platform or manage live quotas.

## Author

Created by **Miranda Tan**, UX researcher with experience across agency and in-house research in North America and Asia.

[LinkedIn](https://www.linkedin.com/in/YOUR-PROFILE) · Feedback and suggestions are welcome — please open an issue.

## License

[MIT](./LICENSE)

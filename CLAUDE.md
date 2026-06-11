# Keystone — Product Brief

> Working name: **Keystone** (placeholder, easy to change). Refers to the moment that holds the Setup → Aha → Habit structure together.

## 1. Problem & Goal

Product teams know onboarding matters but rarely have time or budget to run a full UX audit. Keystone lets a team upload screenshots of their onboarding flow, answer a few questions about their product and users, and receive a structured analysis of where users get confused, lose motivation, or drop off — plus concrete recommendations to fix it.

The goal is **fast, structured insight**, not a replacement for full UX research.

## 2. Audience

- Product designers, PMs, founders, and growth teams
- Early-stage and mid-sized SaaS companies
- Users may have little to no formal UX research background — output must be understandable without jargon

## 3. Platform

Responsive web app. Designed desktop-first (screenshots and reports are easier to review on larger screens), but must remain usable on mobile (viewing reports, basic navigation).

## 4. Core Analysis Framework: Setup → Aha → Habit

Every onboarding flow is evaluated against this framework. Activation is the result of successfully connecting all three moments — completing setup alone is **not** activation.

### Setup Moment
The minimum actions a user must complete before experiencing the product's value.

Analyze:
- Whether the initial steps are clear
- How much information/effort is required
- Whether unnecessary questions or decisions are introduced
- Whether setup is personalized to the user's role, goal, or use case
- Whether users understand *why* each step is necessary
- Where users may abandon the flow

**Key question:** *Can the user complete the minimum setup required to reach value?*

### Aha Moment
When the user experiences clear, relevant, personalized proof of the product's value.

Analyze:
- Whether the value proposition is clear
- How quickly the user reaches meaningful value
- Whether the result is relevant to the user's original goal
- Whether onboarding clearly highlights the value delivered
- Whether the user understands *why* the product is useful
- Whether the flow builds confidence and motivation to continue

**Key question:** *Does the user experience a clear and meaningful moment of value?*

### Habit Moment
When the user understands why and how to return to the product.

Analyze:
- Whether there's a clear next step after the Aha Moment
- Whether users know what to do next
- Whether the product establishes an ongoing workflow
- Whether repeat value is visible
- Whether reminders, progress, saved results, or recurring actions encourage return usage
- Whether the product gives users a reason to build it into their routine

**Key question:** *Does the user understand why they should return and continue using the product?*

### Scoring

Every report produces four scores:

- **Setup Score**
- **Aha Score**
- **Habit Score**
- **Overall Activation Score** (reflects how well the three stages connect, not just an average)

## 5. Input & Upload

- **MVP input method: manual screenshot upload only** (PNG/JPG)
- Users upload an ordered sequence of screenshots representing their onboarding flow, with drag-to-reorder
- Optional per-screen stage tagging (Setup / Aha / Habit) — not required, but improves analysis accuracy when provided
- Single-screen analysis is also supported (quick check on one screen, scoped to whichever stage(s) it's relevant to)
- **Out of scope for MVP, documented future direction:** automated capture via product URL + login credentials (browser automation to log in and screenshot the live flow). Deferred due to engineering complexity (arbitrary flow navigation, multi-step auth) and security/compliance concerns around storing customer credentials.

## 6. Context Questions (collected before analysis)

To ground the AI's evaluation in the product's actual goals, users answer:

- What does your product do? (brief description)
- Who is your target user / role?
- What is the primary action you want new users to complete? (defines the **Setup** boundary)
- What does "value delivered" look like for your product? (defines the **Aha** moment)
- What should users do to get ongoing value / why would they come back? (defines the **Habit** moment)

These definitions let the AI map uploaded screens to the correct stage and judge relevance/personalization against the user's actual goals — even when no per-screen tags are provided.

## 7. Report Structure & Output

For each stage (Setup, Aha, Habit):
- Stage score
- List of findings, each with:
  - **Severity** (Critical / High / Medium / Low)
  - **Description** of the issue and which screen(s) it relates to
  - **Impact** — how it affects that stage's score / the user's path to activation
  - **Recommendation** — a concrete, actionable fix

Plus:
- Overall Activation Score with a short summary of how well Setup → Aha → Habit connect
- Framework-only scope for MVP — all findings map to one of the three stages (no separate accessibility/visual-design layer for v1)

### Output formats
- **In-app interactive report** (primary) — dashboard view, screen-by-screen annotations, expandable findings
- **Exportable report** (PDF) — same content, formatted for sharing with stakeholders

## 8. Accounts

Optional accounts:
- No login required to run an audit and view/export the report
- Creating an account unlocks saving audits, viewing history, and re-visiting past reports

## 9. Analysis Engine

- Design for flexibility — the analysis engine should be swappable/improvable without reworking the product
- Initial approach: multimodal LLM (Claude) given the screenshots + context answers + the Setup/Aha/Habit rubric, returning structured findings (JSON) that the app renders into the report
- Keep the rubric/prompt as a separate, versionable artifact so it can be iterated independently of app code

## 10. Tech Stack (recommendation)

- **Next.js (App Router) + TypeScript** — single framework for frontend, API routes, and server-side logic; good fit for an AI-integrated app and easy deployment on Vercel
- **Tailwind CSS** — supports a clean/clinical visual direction with minimal custom styling overhead
- **Claude API (multimodal)** for screenshot analysis, called from server-side API routes (keeps API keys off the client)
- **Postgres** (e.g. Supabase or Neon) — for optional accounts, audit history, and report storage
- **Object storage** (e.g. S3-compatible, or Supabase Storage) — for uploaded screenshots
- **Auth**: deferred provider choice, but should support optional/guest flows (e.g. Supabase Auth or Clerk, both support this pattern)

## 11. Visual Direction

Clean & clinical — minimal, neutral palette, data-dense layouts. Should feel trustworthy and professional, like an analytics/audit tool, while remaining approachable enough for non-experts (founders, small teams) to act on the findings without confusion.

## 12. Business Model

Not decided — focus on building the product experience first. Revisit monetization (freemium, paid trial, etc.) once the core analysis and report experience are validated.

## 13. MVP Scope Summary

**In scope:**
- Manual screenshot upload (multi-screen ordered flow, or single screen)
- Context questionnaire (product, target user, Setup/Aha/Habit definitions)
- Setup/Aha/Habit framework analysis via LLM
- Four scores: Setup, Aha, Habit, Overall Activation
- In-app report + PDF export
- Optional accounts for saving/history

**Out of scope (documented for later):**
- Automated capture via URL/login credentials
- Accessibility/visual-design analysis layer
- Monetization/billing
- Team collaboration features, multi-flow comparison over time

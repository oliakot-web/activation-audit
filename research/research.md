# Research

Notes, findings, and references gathered while researching the onboarding/activation space, competitor products, and the Setup → Aha → Habit framework.

## Status
In progress — competitor map added below.

## Structure
- `research.md` (this file) — research notes, findings, links, takeaways
- `screens/` — reference screenshots (competitor onboarding flows, inspiration, examples)

## Competitor Map

Three groups: HARD (same product/audience/market), SOFT (different product, same JTBD), ASPIRATIONAL (best-in-class examples to learn from).

### 1. HARD — Same product, same audience, same market (onboarding/activation analysis tools)

| Name | Type | Why in this group | What to learn |
|---|---|---|---|
| **Userpilot** | Onboarding analytics + in-app guidance platform, used by SaaS PMs/growth teams | Directly competes on "onboarding score / benchmark vs. top apps" positioning for the same buyer | How they frame an "onboarding score," benchmark language, report structure that resonates with PMs |
| **Maze (AI Studio)** | UX research platform with AI-generated summaries from usability tests and screens | AI-generated UX feedback delivered as a report — closest to our core mechanic | How AI insights are presented/framed to build trust, severity labeling, report layout |
| **Attention Insight** | AI tool: upload a screenshot, get predicted attention heatmap + analysis | Same core input (single screenshot → AI analysis) and self-serve flow | Upload UX for single screens, how confidence/limitations of AI output are communicated, pricing model |
| **UXtweak (AI UX Audit)** | UX research suite with automated AI audit of designs/screens | Automated audit positioning very close to ours | How findings are categorized/prioritized, export/report formats |
| **Appcues** | Onboarding flow builder with activation analytics & funnel reports | Owns "activation" framing for SaaS onboarding, same buyer persona | Their activation/funnel definitions, segmentation by user role/goal, drop-off visualization tied to specific screens |

### 2. SOFT — Different product, same JTBD (understand & improve onboarding)

| Name | Type | Why in this group | What to learn |
|---|---|---|---|
| **Amplitude** | Product analytics (event-based activation/retention analysis) | Same JTBD via real usage data instead of screenshots | "Aha moment" discovery features, stage-based funnel visualization, activation metric definitions |
| **Hotjar / FullStory** | Session recording + heatmaps | Same JTBD — find onboarding friction — via behavioral signals | How "rage clicks"/dead clicks surface as friction, mapping recordings to onboarding steps |
| **UserTesting / Lyssna** | Moderated/unmoderated user testing platforms | Same JTBD via real human feedback instead of AI | Onboarding test scripts, how qualitative findings get synthesized into themes |
| **PostHog** | Open-source product analytics + session replay + surveys | Same JTBD, dev-friendly audience overlap with early-stage SaaS | How they bundle signals into one "understand user behavior" narrative, self-serve onboarding for technical PMs |
| **Freelance/agency UX audits** (e.g. via Toptal, boutique UX studios) | Manual expert "teardown" services | Same JTBD, traditional manual delivery — sets the anchor we're disrupting | Pricing/turnaround expectations, deliverable structure clients are used to |

### 3. ASPIRATIONAL — Best-in-class in product analytics / UX audit space

| Name | Type | Why in this group | What to learn |
|---|---|---|---|
| **Google Lighthouse** | Automated audit tool (performance/accessibility/SEO → scores + prioritized fixes) | The gold-standard pattern for "automated audit → score + actionable report" | Scoring transparency, report UX (severity color-coding, collapsible findings, "how to fix" links), trust-building for automated scores |
| **Baymard Institute** | UX research benchmark institute (ecommerce UX audits & database) | Gold standard for evidence-backed, structured UX findings | How findings balance "general best practice" vs. "your specific case," premium report structure |
| **Amplitude (thought leadership)** | Activation framework pioneer ("Aha moment," activation metrics) | Best-in-class for the conceptual framework Keystone is built on | How they evangelize activation concepts/terminology, stage-based dashboard visualization |
| **Notion / Linear (their onboarding)** | Products famous for excellent onboarding UX | Concrete reference examples of "good" Setup→Aha→Habit execution | Specific patterns (progressive disclosure, personalization, milestone moments) the AI should recognize and cite |
| **Stripe / Vercel (docs & dashboards)** | Clean, data-dense yet approachable UI | Matches our "clean & clinical" visual direction | Visual patterns for presenting metrics/structured data professionally but approachably for non-experts |

## Onboarding Comparison: Setup → Aha → Habit

> Source: web research / public UX teardowns (see Sources below). Screenshot capture via Playwright was attempted but blocked — the Playwright MCP server is running on Node 18.12.1, which lacks `URL.canParse` (added in Node 18.17). A newer Node (20.20.2) was installed via `nvm`, but the MCP server needs an app restart to pick it up. All screens below are marked **[?] not captured** pending that restart.

| Product | Audience | Core onboarding approach | Key activation mechanism | Trust-building | Monetization |
|---|---|---|---|---|---|
| **Notion** | Knowledge workers, teams, individuals (broad consumer-to-team range) | Welcome survey segments by use case ("for me" / "for my team"), then pre-populates workspace with relevant template content | "Time to first note/edit" — learn-by-doing checklist teaches slash commands and blocks via a fully functional, pre-filled workspace | Familiar templates + visible community (millions of templates/use cases referenced) reduce blank-page anxiety | Freemium — generous free tier for individuals, paid plans gated on team size/collaboration features |
| **Linear** | Software teams (engineering/product), craft-driven culture | "Anti-onboarding" — near-zero setup, no role/permission wizards; pre-populated demo workspace teaches by example | First resolved issue within one session; Cmd+K command menu introduced as the primary interaction model from screen one | Minimalism itself signals quality/craft ("if the product feels this considered, it'll work well") | Freemium — domain-based auto-join drives bottom-up team expansion before paid seats kick in |
| **Stripe** | Developers/technical integrators | Dashboard + docs split — account setup is fast, but deeper "how to integrate" is pushed out to documentation rather than in-context | Test-mode API keys + sandbox let developers make their first API call/charge without real money — value felt before going live | Extensive docs, code samples in every major language, sandbox environment build confidence before real transactions | Usage-based (per-transaction) — no upfront cost, monetization scales with the customer's own success |
| **Vercel** | Developers, especially frontend/framework users | Connect GitHub → pick a repo → auto-detected framework/build settings — no "what is a project" explainer needed | Live deploy URL within minutes ("first deploy as the celebration") — value = seeing your own app live on the internet | Real-time build logs create transparency/control during the "wait" moment; Hobby tier usable indefinitely | Freemium — Hobby tier free essentially forever; conversion happens at natural team-collaboration trigger points, not forced |
| **Userpilot** | SaaS PMs/growth teams (B2B, often non-technical) | Welcome screen collects user goals to segment onboarding; emphasizes "minimum viable onboarding" — only essential steps | Activation defined per-customer via funnel analysis; dashboards surface "time to activation" and drop-off points explicitly | Heavy use of benchmark data/case studies (e.g. "+47% activation") to build credibility before purchase | Subscription SaaS, tiered by MAU/contacts — sales-assisted for larger accounts |
| **Appcues** | SaaS PMs/growth teams (B2B) | Signup optimized for speed (SSO, minimal fields); welcome modal sets up first "flow" to build immediately | Activation defined as a specific in-product action correlated with retention (not just login); their own redesign cited 2.5x activation lift | Self-referential case studies (using Appcues to onboard onto Appcues) double as proof-of-product | Subscription SaaS, tiered by MAU — free trial leads into sales-assisted upgrade |
| **Amplitude** | Data/growth teams, technical and non-technical mixed | Long, structured signup (8 screens: email → name → team → role → company → password) before reaching the product | Test/demo data lets new users explore funnels and dashboards before their own data is integrated — value felt pre-integration | Heavy content marketing on "activation" as a concept — positions Amplitude as the authority defining the term | Freemium with usage-based scaling (event volume) — enterprise sales-assisted tier above self-serve |
| **PostHog** | Developers/technical founders, self-serve first | User picks one product to set up first (analytics, replays, flags, surveys) — onboarding narrows scope rather than overwhelming with the full suite | Activation = events ingested + one insight + one dashboard created — concrete, observable "first win" | Transparent handbook/docs culture; onboarding team uses docs/AI live on calls rather than guessing — models the self-serve behavior they want from users | Usage-based (event volume), generous free tier; sales-assisted only above ~$500/mo forecast |

### 3 Shared Patterns

1. **Segment first, personalize immediately.** Notion, Userpilot, Appcues, and PostHog all ask 1 question (or let the user pick) before showing anything, then tailor the very next screen to that answer — personalization happens *before* any real product use.
2. **The "first win" is engineered, not discovered.** Every product manufactures a fast, visible moment of value (Notion's pre-filled workspace, Linear's first resolved issue, Vercel's live URL, Stripe's sandbox charge, PostHog's first dashboard) — none rely on users stumbling into value organically.
3. **Monetization is decoupled from onboarding.** All seven products let users reach their Aha moment, and often well into Habit, on a free/trial tier. None gate the core "prove the value" experience behind payment — paywalls appear at scale/collaboration triggers, not activation triggers.

### 3 Differences

1. **Explanation vs. demonstration.** Linear and Vercel deliberately avoid explaining concepts (no "what is a project" screens) and let the interface teach by doing; Amplitude and Userpilot/Appcues lean on more structured, multi-step signup and explicit goal-setting questions.
2. **Where the Aha moment lives relative to "real data."** Vercel/Linear/Notion deliver Aha using the user's *own* content (their repo, their issue, their workspace) within minutes. Amplitude and PostHog often deliver an initial Aha via *demo/sample data*, with the "real" Aha deferred until the user's own data is integrated — a longer, two-stage activation.
3. **Audience sophistication shapes onboarding length.** Developer-first products (Vercel, Stripe, PostHog, Linear) compress or skip setup screens, assuming users can self-orient; PM/business-audience products (Amplitude, Userpilot, Appcues, Notion-for-teams) invest more in explicit questionnaires, segmentation, and guided tours.

### 3 Open Questions

1. For Keystone's own onboarding, should we follow the Linear/Vercel "show, don't ask" model (jump straight to uploading a screenshot) or the Notion/Amplitude "ask first, personalize" model (collect product/Aha/Habit definitions before any upload)? Our framework *requires* some context up front — can we make that feel like Notion's segmentation rather than Amplitude's 8-screen form?
2. Several products (Amplitude, PostHog) solve the "no data yet" cold-start problem with demo/sample data. Should Keystone offer a **sample report** (pre-loaded example onboarding flow + analysis) so users experience the Aha moment (a useful report) before uploading their own screenshots?
3. All seven reference products decouple monetization from activation. If/when Keystone introduces pricing, what's our equivalent of "the free tier that's usable forever" — e.g., is a single free audit per account enough to prove value, or does credibility require letting users run multiple audits before any paywall?

### Sources
- [Notion's clever onboarding and inspirational templates](https://goodux.appcues.com/blog/notions-lightweight-onboarding)
- [How Notion Nails Personalized Onboarding (Teardown)](https://www.candu.ai/blog/how-notion-crafts-a-personalized-onboarding-experience-6-lessons-to-guide-new-users)
- [Linear Onboarding Teardown: How Anti-Onboarding Drives Adoption](https://www.candu.ai/blog/linear-onboarding-teardown)
- [The onboarding Linear built without any AB Testing](https://www.growthdives.com/p/the-onboarding-linear-built-without)
- [How Linear welcomes new users (Medium)](https://fmerian.medium.com/delightful-onboarding-experience-the-linear-ftux-cf56f3bc318c)
- [Case study: User flow uncovering—Stripe (Medium)](https://medium.com/design-bootcamp/case-study-user-flow-uncovering-stripe-e58f080043e2)
- [A new and improved onboarding flow for Express accounts (Stripe)](https://stripe.com/blog/connect-express-onboarding)
- [Vercel's AI-Native Customer Onboarding](https://getperspective.ai/blog/vercel-ai-native-customer-onboarding-developer-teams)
- [Vercel Onboarding Flow on Web (Page Flows)](https://pageflows.com/post/desktop-web/onboarding/vercel/)
- [Minimum Viable Onboarding: Your Go-To Guide To User Activation (Userpilot)](https://userpilot.com/blog/minimum-viable-onboarding/)
- [+47% User Activation Rate with Userpilot: Attention Insight Case Study](https://userpilot.com/blog/attention-insight-userpilot-case-study/)
- [We increased our activation rate by 2.5x in just 15 minutes (Appcues)](https://www.appcues.com/blog/we-increased-our-activation-rate-by-2-5x)
- [Product-Led Onboarding: The Complete Guide (Appcues)](https://www.appcues.com/blog/product-led-onboarding)
- [4 Steps to Measure User Onboarding the Right Way (Amplitude)](https://amplitude.com/blog/4-steps-to-measure-user-onboarding)
- [Create a new account | Amplitude Docs](https://amplitude.com/docs/get-started/create-a-new-account)
- [App onboarding: How to fix drop-off points (PostHog)](https://posthog.com/blog/how-to-find-and-fix-app-onboarding-drop-off)
- [How we built our onboarding email flow (PostHog)](https://posthog.com/blog/how-we-built-email-onboarding)

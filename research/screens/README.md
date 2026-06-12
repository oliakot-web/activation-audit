# Screens

Reference screenshots collected during research — competitor onboarding flows, inspiration, examples used to inform the analysis framework and product design.

## Status

**Captured** via Playwright (1440×900, public/unauthenticated pages only). The earlier Node version blocker (`/usr/local/bin/node` v18.12.1 missing `URL.canParse`) was resolved by symlinking `/usr/local/bin/node` to the `nvm`-managed v20.20.2 and restarting the Playwright MCP server.

Naming convention: `{product}-{step}-{description}.png`. Any screen that requires a logged-in account beyond what's publicly reachable is marked `[?]` and not captured.

## Captured screens

- **Notion**
  - `notion-01-homepage.png` — notion.com landing page
  - `notion-02-signup.png` — notion.com/signup (redirects to app.notion.com/signup)
  - `[?]` Post-signup welcome survey / workspace setup — behind login wall, not captured

- **Linear**
  - `linear-01-homepage.png` — linear.app landing page
  - `linear-02-signup.png` — "Create your workspace" signup screen
  - `[?]` Post-signup demo workspace / first-issue flow — behind login wall, not captured

- **Stripe**
  - `stripe-01-homepage.png` — stripe.com landing page (redirected to stripe.com/en-pl)
  - `stripe-02-signup.png` — dashboard.stripe.com/register account creation screen
  - `[?]` Post-signup dashboard / API key setup — behind login wall, not captured

- **Vercel**
  - `vercel-01-homepage.png` — vercel.com landing page
  - `vercel-02-signup.png` — vercel.com/signup ("Your first deploy is just a sign-up away")
  - `[?]` Post-signup project import / first deploy flow — behind login wall, not captured

- **Userpilot**
  - `userpilot-01-homepage.png` — userpilot.com landing page
  - `[?]` No public self-serve signup found — `/book-a-demo/` returned a 404; Userpilot appears to be sales/demo-led. Onboarding flow not captured.

- **Appcues**
  - `appcues-01-homepage.png` — appcues.com landing page
  - `[?]` No public self-serve signup found on the homepage (CTA is "Get a Demo"); Appcues appears to be sales/demo-led. Onboarding flow not captured.

- **Amplitude**
  - `amplitude-01-homepage.png` — amplitude.com landing page
  - `amplitude-02-signup.png` — app.eu.amplitude.com/signup. Note: at capture time the page displayed untranslated i18n keys (e.g. `signup.oneScreenSignupView.emailRequest.email`) instead of localized labels — likely a temporary loading/localization bug on Amplitude's side, but the form structure (Google SSO + email/name/company fields, data-location selector, consent checkboxes) is still legible.
  - `[?]` Post-signup product tour / demo data exploration — behind login wall, not captured

- **PostHog**
  - `posthog-01-homepage.png` — posthog.com landing page
  - `posthog-02-signup.png` — us.posthog.com/signup "Get started" screen
  - `[?]` Post-signup product selection / first insight flow — behind login wall, not captured

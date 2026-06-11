# Screens

Reference screenshots collected during research — competitor onboarding flows, inspiration, examples used to inform the analysis framework and product design.

## Status
**[?] Not yet captured.** Capture via Playwright was attempted for Notion, Linear, Stripe, Vercel, Userpilot, Appcues, Amplitude, and PostHog onboarding/signup screens, but the Playwright MCP server resolves `node` to `/usr/local/bin/node` (v18.12.1, missing `URL.canParse`, added in Node 18.17+). Node 20.20.2 was installed via `nvm`, but `/usr/local/bin/node` is a separate binary not managed by `nvm`, so a session restart didn't fix it. Fix requires `sudo ln -sf "$(nvm which 20)" /usr/local/bin/node` (or reconfiguring the MCP server's node path) — skipped for now.

Naming convention once captured: `{product}-{step}-{description}.png` (e.g. `notion-01-welcome-survey.png`). Mark any screen that requires a logged-in account beyond what's publicly reachable as `[?]` in this file.

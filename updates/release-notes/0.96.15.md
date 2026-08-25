# Continuum 0.96.15

## Features
- The guided first-run journey is now on for everyone on continuumcode.ai: a fresh account lands on welcome, GitHub connect, repository picker, and task cards instead of a bare prompt box. The "first week included" promises appear only when the account actually holds a compute grant (#1679)
- Connections: a new entry at the bottom of the Code sidebar opens one place for AI subscriptions, source control, and apps. Connect a ChatGPT subscription from the web app with a one-time device code; the credential is sealed into the same vault as every other provider, and the box never sees your password (#1679)
- Founder admin console: a Corporates explorer lists every organization and drills into members, teams, usage, spend, budgets, policies, entitlements, provisioning, API access, and recent activity, read-only and secret-safe (#1677)
- Effort pickers now advertise exactly the reasoning tiers each model supports, on Mac, iPhone, web, Windows, Linux, and the Android app. An effort a model does not support is refused before any tokens are spent instead of silently running at the provider default (#1676)

## Fixes
- Usage and Settings sit flush at the bottom of the web sidebar again, matching the Mac app (#1679)
- Existing OpenCode sessions that still carried an effort their model no longer advertises keep sending; the stale effort is dropped instead of every prompt being rejected (#1676)
- Clicking outside the ChatGPT connect tray closes only the tray, and a connect flow that the server has forgotten after a restart now says so instead of waiting forever (#1679)
- Corporate detail pages load on production PostgreSQL, count hosted entitlements the same way billing does, ignore invited or removed members, and resolve Apple and Stripe subscriptions to the right tier (#1677)
- Six guides on continuumcode.ai now close with Get Plus and the in-tool how-tos subscribe first, then mint a key, with the harness pre-selected after checkout (#1675, #1678)

## Under the hood
- The ChatGPT device-auth broker runs the Codex CLI with a minimal environment, caps concurrent flows box-wide, confirms child termination, cleans token directories durably, and seals credentials atomically; the Codex CLI is baked into the cloud image (#1679)
- CONTINUUM_FIRST_RUN_JOURNEY_ENABLED=false darkens the journey for every account, including compute-grant holders (#1679)

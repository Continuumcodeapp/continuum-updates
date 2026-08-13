# Continuum 0.87.0

## Features
- Grok 4.6 is now a first-class model: pick it natively in the model picker or run it on Continuum's hosted inference, routed, priced, and ranked alongside everything else — Grok 4.5 keeps working (#1534)
- Auto mode is back in the Mac composer. It appears as soon as your host supports routing, and stays usable even when Auto is the only choice available (#1532)
- Per-model usage promotions: individual hosted models can run 1.5x, 2x, or 3x allowance multipliers on a schedule, with the promotional rates and their UTC dates published on the pricing page (#1529)
- New guide: point Cursor's OpenAI base URL at Continuum's hosted inference and use your Continuum models inside Cursor (#1530)

## Fixes
- Queued follow-ups now survive a reload or a restart on web and the Windows/Linux desktop app — order, attachments, edits, and steer baselines all come back intact (#1527)
- Hosted inference in Cursor no longer dies on the first agent turn: the gateway accepts flat Responses-API tool definitions instead of rejecting the whole request (#1528)
- Seven Mac hosted-inference and session lifecycle defects are fixed — transcript accessibility recursion, Plan-to-Code drift, provider-readiness disagreement, transient "Session not found", queued work lost after a crash, Sparkle offering downgrades, and opaque hosted terminal failures (#1526)
- Sparkle's updater helpers no longer linger in macOS 27's background-activity indicator, and the update action reads "Update & Relaunch" there (#1525)
- 21 verified P1 fixes across cloud, web, desktop, the Go agent, and Mac/iOS — including offboarding that left ex-members' API keys billing the org, stale invitations that could re-admit a removed member, and dropped WorkOS webhooks (#1531)

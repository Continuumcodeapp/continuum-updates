# Continuum 0.57.22

Seventeen PRs land as one coordinated release: plan approvals that actually flip to Code mode, a faster Mac, a multi-account iOS Usage screen, and a web app rebuilt to match the Mac.

## New

- **Multi-account on iOS Usage.** Work/Personal-style account pills appear under the provider selector when you have secondary accounts; the hero gauge and limits follow the selected account, matching the Mac. (#880)
- **Cowork connector browser sign-in persists.** Each app connector gets a durable browser profile, so web sign-ins survive relaunches and updates - kept fully separate from agent-usable credentials, with token paste still available. (#876)
- **Branded Mac download.** `mac.continuumcode.ai` now redirects to the latest signed DMG, and the website's download buttons use it everywhere. (#881)
- **Web app, rebuilt.** continuumcode.ai/app now matches the Mac app's Quiet Black chrome - Mac-parity titlebar with Chat | Cowork | Code, a new Organisations tab, and frictionless onboarding. (#851)

## Fixed

- **Approved plans switch to Code mode.** Approving a plan respawns the session with Code-mode permissions instead of a lower prompting tier, and the composer pill reflects it - including for managed/SDK providers, which now surface "Approve & run" even without structured plan text. (#873, #871)
- **Your prompt no longer vanishes mid-send.** The pending message stays visible while the provider streams (the "create pr" disappearing-text gap), and titlebar Create PR always targets the active session without flashing collapsed turns open. (#878, #874)
- **Code sidebar cleanups.** First-turn sessions get compact 1-5 word titles again (manual names always win), and archived branches no longer resurrect from lingering drafts or terminal tabs. (#869, #872)
- **Custom project icons sit cleanly on the black sidebar** - no tinted pill behind uploaded logos, and flat corner fills are knocked out on import without eating dark logo art. (#868)
- **Codex live usage refreshes on cadence** for ChatGPT-auth accounts even when local session files are quiet. (#875)
- **Chat attachment paths with spaces** are preserved and no longer leak bogus artifact chips. (#870)
- **iOS spend chart opens on a single tap**, even on narrow 90-day bars. (#879)
- **iOS Settings shows your signed-in email**, backfilled automatically on older installs. (#867)
- **iPhone visitors to the website** get "Install iOS app" (App Store) instead of a Mac DMG they can't use. (#877)

## Faster

- **Mac session switching is instant-feeling** with 8-12 active sessions: hidden tabs stop burning CPU on animations, the transcript pool is right-sized with recovery, and composer/header state moved onto narrow slices. (#882)

Ships build 293 for Mac (signed Sparkle feed).

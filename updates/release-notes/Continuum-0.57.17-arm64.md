# Continuum 0.57.17

A new provider, a rebuilt website, one-tap device setup, and a batch of connect + voice reliability fixes.

## New

- **Z.ai Coding is now a first-class provider.** Connect your Z.ai GLM Coding Plan key in Settings → Providers and Continuum tracks GLM-5.2, 5.1, 5-Turbo, and 4.7 across chat, the Code launcher, live 5-hour + weekly quota gauges, and its own analytics column. If the account has no active Coding Plan, the gauge tells you that instead of showing a dead bar. (#843)
- **One-tap device setup.** Adding a Linux or Mac device (Settings → Devices) now runs a single setup script on the target and streams live, step-by-step install progress right in the app — naming the failing step if anything goes wrong. (#845)
- **A rebuilt continuumcode.ai.** New homepage plus Product, Solutions, and Pricing pages, with cursor-driven feature demos. (#846)

## Fixed

- **OpenCode "Connect usage meters" actually connects.** When there's no readable browser login it opens the opencode.ai sign-in for you, and when the import is blocked it now tells you exactly what to fix — grant Full Disk Access (with a one-tap Settings link) or allow the Keychain prompt — instead of silently re-opening the browser in a loop. (#842, #848)
- **Reliable Left Option voice trigger.** The overlay pill appears the instant you press Option, voice still works in-app when Accessibility isn't granted (with a one-time heads-up), and rapid gestures no longer race or leave a stuck pill. (#850)
- **Grok menu-bar popover** now shows the monthly "Credits used" bar, matching the Usage page, instead of a "credits unavailable" tile. (#849)
- **"Add your first repo"** empty state in the Code sidebar when it's genuinely empty, instead of a misleading "no matching sessions" filter message. (#847)

Ships build 288 for Mac (signed Sparkle feed).

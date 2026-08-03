# Continuum 0.76.0

## What's new

- **Stop a running turn from your iPhone.** The Code composer now turns into a Stop button while the model is working, so you can cut a turn short without reaching for the Mac — and typing a follow-up still sends it, so mid-turn steering keeps working exactly as it does on desktop. (#1401)
- **Grok sessions no longer look finished while they're still working.** When Grok retries a request in the background, the live stream animation and turn timer stay up instead of the transcript quietly going idle — and a retry that never resolves now ends cleanly rather than leaving a session spinning forever. (#1404)
- **Usage reads as a percentage, not a dollar figure.** The weekly hosted-inference limit no longer shows a dollar cap anywhere — Mac, iPhone, web, and the pricing page all show how much of your allowance you've used and when it resets. Plans now describe their allowance relative to Plus instead of a raw number. (#1402)
- **A product page for every feature.** continuumcode.ai now has dedicated pages for Code, Voice, App Shots, Cloud, sharing, plan review, the auto model router, env variables, pairing, widgets, desktop, and security — reachable from the Product menu and the footer. (#1403)
- **Compare hub.** New "Continuum vs" pages covering 14 tools (Cursor, Claude Code, Codex, Copilot, Devin, Aider, Windsurf, Conductor and more), each one honest about where the other tool wins and how to use both together. (#1405)

## Fixes and under-the-hood

- Sparkle delta updates generate correctly again — code-signature extended attributes are stripped from Mac sources before packaging, so incremental updates stop falling back to full downloads. (#1398)
- The website's download links now auto-bump to the newest desktop and CLI releases as part of the release process, instead of drifting behind. (#1397)
- Site analytics: Google Tag Manager is live on the marketing site. (#1400)
- Fixed an apns-gateway dependency mismatch that could break a clean install. (#1399)

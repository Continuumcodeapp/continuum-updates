# Continuum 0.69.0

- Everything that syncs your sessions got dramatically lighter. The session list that refreshes every couple of seconds now sends only what the client actually renders — live sessions instead of your whole archive, and plan documents only on the screen that shows them. On a real workspace that's a 687 KB refresh down to 57 KB, roughly 44× smaller once compressed, on Mac, web, Windows, Linux, and the terminal client. (#1329)
- Idle machines stay idle. A background connector poller was spinning at about a third of a CPU core doing nothing but failing, and the Windows/Linux agent re-uploaded its full workspace snapshot every single minute — both are fixed, so a Continuum that's just sitting there costs you almost nothing. (#1329)
- Chat is usable before you have an account. Ask one question on continuumcode.ai and get a real answer before signing up, then keep the conversation when you do. Free models are available on every plan, and the web chat now has the same model picker as the Mac composer. (#1331)
- Web Chat and Code now look and work like the Mac app: the same workbench layout, history rail, transcript, and composer. Opening Code goes straight to your most-used connected device instead of stopping at a "pick a runtime" screen, and falls back to Continuum Cloud when nothing is connected. (#1328)
- Long conversations scroll all the way back to where they started. The transcript used to hit a wall at the loaded tail; now it reveals what it's holding and pages further back on its own, keeping your place while it loads. (#1322)
- Voice transcription starts the instant you press the key. The microphone now opens before the speech model finishes loading, models stay warm between uses, and the one you've selected is prepared at launch — short recordings no longer come back empty. Grok speech-to-text stays available whenever you have a Grok login. (#1327)
- Your weekly Continuum limit resets exactly seven days from when your plan started, not on a calendar boundary, and every client shows the same countdown, spend, and budget the server enforces. (#1324)
- Codex shows both of its meters again — the rolling 5-hour session limit is back alongside the weekly one, matching how Codex actually bills. (#1320)

## Fixes

- The Personal Claude gauge no longer disappears behind a false "reconnect" prompt when a token refresh briefly fails, while an account that genuinely needs re-authentication now says so instead of showing a stale number. (#1332)
- The Grok weekly gauge no longer sticks on STALE at 0% during a week you haven't spent anything — on Mac, Windows, and Linux. (#1330, #1333)
- The plan progress bar now appears in every direction it should: on the Mac sidebar for sessions hosted on Linux or Windows, and in the web and desktop clients for sessions hosted on a Mac. It was silently missing on both. (#1329)
- Messages typed while your Mac was unreachable now actually send once it reconnects, instead of sitting in the queue forever. (#1329)
- The web dashboard can connect to your Mac again — identifying itself correctly on connect, and encrypting the link the way the Mac expects. (#1323, #1325, #1326)
- Code project headers no longer show an environment-variable count pill. (#1321)

## Under the hood

- Faster chat rendering: incoming messages update in place and only new content is re-processed, instead of rebuilding the transcript on every token.
- Database work for large workspaces got a dedicated index, and the scheduled maintenance job now claims its work so it can't run twice and send duplicate notifications. (#1329)
- Security hardening on the pre-sign-up chat endpoint: cross-site requests are rejected, per-network limits can't be bypassed by rotating addresses, and the endpoint refuses to run unless its privacy salt is configured. (#1331)
- Release builds now refuse to publish unsigned Windows installers or resolve dependencies without a lockfile. (#1329)

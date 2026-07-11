# Continuum 0.48.0

A big workbench release: a new Save Costs control center for token/cost reducers, a cleaner Settings layout, snappier streaming that shows your turn the instant you send, and a wide sweep of Code-tab, composer, and permission-banner fixes.

## New & improved

- **Save Costs settings.** A new Settings section to cut token spend: enable the **Headroom** local-compression proxy and the **Caveman** token reducer per provider, see live install/status, and one-click install the tooling. Estimated savings are shown up front. (#615)
- **Streaming shows up the instant you send.** Send a prompt and the active turn - the streaming footer and elapsed timer - appears within a frame, before the server confirms, instead of after a beat. Worktree streams light their status immediately too. (#609, #606)
- **Settings that read as one surface.** The Visual toggles now use the same trackless segmented style as the primary nav, Skills is promoted to its own top-level Settings group, and provider preferences persist across restarts. (#598, #597, #602)
- **Tidier Code-tab transcript.** Consecutive Bash/shell tool runs collapse into a single "Ran N commands" group, attachments show their real generated filename instead of a type label, and session/branch summaries read cleanly even when your first message is attachment-only. (#612, #607, #610)
- **Faster Codex startup.** Opening a Codex workspace returns immediately and brings the agent online in the background instead of blocking on the handshake. (#608)
- **Small touches.** A save tick when you rename an account, and a hover affordance on the composer's tools menu so it reads as clickable. (#601, #617)

## Fixes

- **Manual scrolling is respected while streaming.** Scrolling up to read during a streaming response no longer yanks you back to the bottom; auto-follow resumes when you return to the latest. (#611)
- **Permission banners reflect reality, live.** The Accessibility grant for Voice + App Shots now flips the moment you grant it (no relaunch), the App Shots both-Option capture chord is fixed, and the Full Disk Access banner hides as soon as access is granted. (#599, #600, #604)
- **Provider picker connect controls.** The OpenCode provider picker's connect + close controls are clickable again and render the right icons. (#603)
- **Cleaner chat layout & formatting.** Customer bubbles no longer tuck under the transcript rail, and an assistant's final response is formatted without duplicated or run-together paragraphs. (#605, #614)
- **PR state stays honest.** A stale PR referenced earlier in chat no longer hijacks the session's PR card, and the sidebar's per-branch PR status icons stay current (open/draft/merged/closed). (#613, #616)

Ships build 261 for Mac (signed Sparkle feed).

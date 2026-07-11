# Continuum 0.58.0

Eighty-six PRs land as one release, and speed is the headline: a top-to-bottom performance overhaul keeps the Mac app fast even with many worktrees and sessions active at once - switching, scrolling, and typing stay instant where they used to drag. On top of that, Grok 4.5, a Claude Fable usage bar, iOS new-session attachments, and a deep reliability campaign on session history, archive, and delete.

## New

- **Grok 4.5.** The new model is available across the model pickers on Mac, iOS, and web, with same-day pricing so Grok usage and cost show up correctly everywhere. (#918)
- **Claude Fable usage bar.** A dedicated Fable quota bar sits under the all-models weekly/monthly bar in the Mac Usage tab, the menu-bar popover, and the iOS usage surfaces - including scoped-weekly Fable limits. (#897)
- **Attach files when you start a session on iPhone.** The iOS new-session composer gets a plus menu with separate Photos/Videos and Files options; selected items show as removable thumbnail chips and upload into the session with the first prompt. (#884)
- **Your paired Mac shows by name.** The iOS New Session device picker now labels the Mac with its actual host name instead of a generic "This Mac." (#885)

## Fixed

- **Sessions you start from your phone now actually run.** A phone-created Code session sends your typed prompt as the first turn - the transcript and working state appear instead of an empty tab. (#883)
- **Session history, archive, and delete are reliable under load.** A deep hardening pass closed a class of races in how sessions are stored, mirrored, and paired - write-ahead archive receipts, atomic delete with sibling de-pairing, and resync that reliably publishes - so archived sessions no longer resurrect and history stays consistent even when mutations overlap. (#905, #915, #917, #919, #920, #925, #926, #927, #928, #929, #930, #931, #935)
- **No more duplicate completions or notifications.** Duplicate Codex transcript completions, duplicate edge feedback, and duplicate "done" notifications are all gone, and follow-up sends into a live transcript stay stable. (#888, #889, #892, #893)
- **The Grok gauge stays live.** Grok CLI tokens now refresh through xAI's OIDC endpoint instead of reading as a terminal auth failure, so the gauge no longer sticks at 0; usage parsing also tolerates xAI's weekly-style billing shape. Grok headless turns complete cleanly. (#894, #903)
- **Codex live usage refreshes correctly** when you toggle the provider on, and the Codex usage gauge parses its rate-limit data reliably. (#896, #908)
- **Cleaner Mac Code transcript.** The completed-turn preview chip is gone so final responses stay focused, and safe URLs render inline as tappable blue links. (#887, #898)
- **iOS surface polish.** The live "Working…" footer now matches the Mac's steady elapsed-time stream, the inert session progress bar is gone, and chat broadcasts feel snappier. (#886, #891, #895)
- **Mac Code cleanups.** The composer action button no longer wraps awkwardly, Code sidebar branch-count badges are correct, a duplicate paired Mac no longer appears in the device mesh, sent prompts clear out of the queue tray, the new Code tab starts in the right first-send state, and uploaded repo icons sit cleanly without tinted backgrounds. (#899, #900, #901, #902, #904, #890)
- **Custom-provider settings errors are surfaced** in the logs instead of being silently discarded, making misconfigured providers easier to diagnose. (#921)

## Faster

This release rebuilds the hot paths so the app stays responsive with lots going on at once.

- **Multi-worktree scaling.** Stores are now event-driven with row-level publishes, and the subprocess storms that fired on every change are gone - the single biggest win for many active worktrees. (#906, #943)
- **Instant interactions.** Client interactions apply immediately, hidden tabs stop opening sockets and running polls, and off-screen sessions go dormant so only the active transcript is mounted and rendering. (#909, #938, #945)
- **Lighter transcripts and chat.** Web transcripts virtualize, chat streams apply only changed slices as deltas across every stack, and markdown/transcript rendering caches its converted output instead of re-computing it. (#907, #913, #936, #937, #954, #958)
- **Faster usage, pricing, and analytics.** Usage pollers share scheduling and coalesce keychain reads, `/usage` fan-out sits behind a snapshot cache, pricing and aggregation hot loops are memoized, and analytics ingests JSONL incrementally instead of re-walking everything. (#933, #940, #941, #944, #946, #951, #955)
- **Snappier composer and terminal.** Attachment staging and clipboard encoding moved off the main thread, the FFF/git index cache is bounded, and the PTY/terminal feed gates subscriptions and stops copying chunks. (#932, #960)
- **Broad hot-path cleanup.** O(n²) projection fixes, JSONL tail rework, timer elimination, coalesced fan-out, cached sidebar and RepoIndex scans, de-duplicated PR polling, and leaner Go agent streams round out the sweep. (#910, #911, #912, #939, #942, #947, #948, #949, #950, #952, #953, #956, #957, #959, #961, #962)

## Under the hood

- **Security hardening.** Broker dependencies are pinned, broker HMAC requests are replay-protected, and Vite is bumped. (#922)
- **Reliability fixes and coverage.** A final review pass cleaned up remaining slice-level findings across the composer, pollers, web, and broker paths; the AntigravityLSP client now drains subprocess output before exit; and the Python sidecar gained real test coverage (19% → 96%). (#916, #963, #964, #965, #966, #967, #968, #923)
- **Motion language.** A cross-platform motion token set and micro-interaction catalog now document the app's animation behavior. (#914)

Ships build 294 for Mac (signed Sparkle feed).

# Continuum 0.96.14

## Features
- When an AI design flow generates visual options, Option 1, Option 2, and Option 3 now appear inline in the chat before the assistant asks which one to build — on Mac, iPhone, web, Windows, Linux, and remote hosts. Image bytes stay in bounded private frames on the producing host, never in transcripts (#1670)
- Effort pickers are now truthful per model: every picker on Mac, iPhone, and web shows exactly the reasoning tiers the selected model actually advertises, and an unsupported effort is refused before any tokens are spent (#1667)
- A new Turn Trace diagnostics pane (Settings → Diagnostics on Mac, iPhone, and web) records each provider turn's lifecycle — acceptance, first response, tool calls, completion — with stable tool counts across reconnects, and never stores prompts or file contents (#1666)
- Attachments are now verified end to end: the host re-checks ownership, type, size, and digest at send time, OpenCode models receive real typed file parts, and a model that cannot accept images says so up front with image-capable suggestions (#1668)
- Dropping a screenshot with a bug report now routes the turn into a real investigation instead of the model trying to recreate the picture, identically on Mac and Linux/Windows hosts; an explicit /skill mention always wins (#1669)
- The Android app's first-run now matches the iPhone app: the provider-consent page, the Set up Continuum cover with launch reveal, the full sign-in sheet, streaming session detail with live elapsed time, and a per-account usage toggle (#1674)

## Fixes
- Starting two sessions in the same repository no longer loses one to a git lock race that left orphaned branches with no session; branch creation is now atomic on both the Mac and Linux/Windows hosts, and a real failure reports the actual git error instead of a progress message (#1673)
- Switching a Codex session between Plan and Code keeps the same provider thread: no more hidden transcript replay, ghost answers under old questions, or a wasted turn on every toggle; if continuity is impossible the switch refuses cleanly instead of silently starting over (#1665)
- A session running on one of your other devices shows its Code/Plan chip and effort controls on iPhone again (#1672)
- Mac Settings dropdowns no longer show a stray hollow circle before their labels (#1661)
- The Continuum Plus subscription is findable as its own row in Settings on iPhone, web, and the Android app (#1671, #1674)
- The streaming session timer on iPhone is visible in light mode again (#1674)

## Under the hood
- Groundwork for a standalone web product shipped dark behind server flags: free-compute rails with database-enforced caps, a repository task-recommendation pipeline, org join requests, PR-ready email, and night-queue scaffolding — nothing is user-visible until enabled (#1660)
- The serverless credential path was hardened: per-execution exchange secrets, seeded inference keys that expire and revoke on every terminal state, replay-proof scan callbacks, and installation-verified org join requests (#1660)
- Sign-in from the Android app returns to the Android app instead of bouncing into the iPhone app's URL scheme (#1674)

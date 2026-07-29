# Continuum 0.68.0

- Share a transcript as a link: publish any Chat, Code, or Cowork conversation to a public page at continuumcode.ai/share/… with expiry, refresh, and revoke. Everything is redacted server-side before it's stored — home directories, credentials, connection strings, emails, and private IPs never leave your machine in the clear. Works from Mac, iPhone, web, Windows, Linux, and the terminal client. (#1319)
- Repository environment variables now work on every client, not just the Mac. Your repo's own `.env` files are picked up automatically and injected into sessions, terminals, and agents; variables you paste into a chat are captured into the repo's list and redacted from the prompt instead of being sent to the model; and agents are told which variables already exist so they stop asking you for secrets you've already set. Keys that could redirect traffic or hijack process loading are refused rather than stored. (#1317)
- Connect third-party apps from Settings: the full ~140-app connector directory now loads on every client, with one-click authentication, your own MCP servers, and per-app connection state. Previously anything paired to a Mac showed an empty gallery. (#1309)
- Dictate with your own provider's voice models: speech-to-text through a connected Grok or OpenAI subscription, on Mac, iPhone, Windows, Linux, and the web — no separate sign-in, and your provider key never leaves the host. (#1315)
- Provider setup is far easier to use: every provider in the catalog now has a visible Connect button (it used to appear only on hover), real brand marks, live connection status, keyboard navigation, and a prominent entry point in Settings instead of a buried link. (#1316)

## Fixes

- Approve & run now starts on the first click. A busy git index could silently swallow the first press, so plan approvals appeared to do nothing. (#1310)
- Queued follow-up prompts now send the moment the current turn ends, even if you've moved to another session or worktree — no reselection needed. (#1313)
- Sub-agents that finished now show as Done instead of being stuck on "Working" forever. (#1318)
- One end-of-turn notification per turn, instead of one per sub-agent on turns that fan out. (#1308)
- Assistant replies no longer appear twice in the transcript when a message and its recorded copy arrive out of order. (#1311)
- Links in chat render correctly: URLs no longer break apart into pieces with injected spaces, and multi-word link text stays one continuous, clickable block. (#1303, #1314)
- The edited-file chip counts the lines that actually changed instead of the whole file's line totals, and large diffs no longer stall the interface. (#1305)
- A brand-new session's first message says "Starting session…" instead of "Resuming session…". (#1304)
- Continuum-hosted model pickers stay populated when the gateway is briefly unreachable, and Continuum now has a menu-bar gauge with weekly spend like every other provider. (#1312)
- The Land PRs button has been retired from Code and Settings. (#1307)

## Under the hood

- Search engines can now index the site and docs properly (sitemap index, structured data, canonical URLs). (#1306)
- Android release build scaffolding for the mobile app. (#1302)
- Security hardening: authentication added to the connector runtime routes, repository `.env` files can no longer redirect an agent's API traffic, and public share pages are rate-limited with hardened redaction. (#1309, #1317, #1319)

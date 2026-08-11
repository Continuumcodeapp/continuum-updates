# Continuum 0.86.0

## Features
- Chat spacing setting: pick Compact or Spacious transcript density on Mac, iPhone, web, and the desktop app — with a live preview in Settings, and a roomier 16px default (#1509)
- Settings has a real information architecture: six labelled groups on every client, search that understands plain words like "MCP", and a direct "Add MCP server" action from search (#1521)
- Buy Continuum for your team: the organizations page rebuilt with five live demos, a tier + seat picker that checks out through Stripe, and a post-purchase org setup flow with invites and roles (#1500)
- Queued messages grew up: reorder follow-ups without losing attachments, a compact 3-row tray inside the composer, and Cmd+Return now queues-and-steers into the running turn (#1511)
- The account you pick for a new session is now enforced end to end — no more silent billing to the default account on any client (#1516)
- Admin: see each customer's average weekly-limit consumption over the last 1, 5, or 20 periods, with CSV export (#1505)
- Secondary Continuum accounts now get image input on Fable 5 without re-authenticating (#1508, #1504)
- MCP connectors now work out of the box in the Mac app — the connector runtime ships bundled, no external Python required (#1513)
- Anonymous-usage sharing is now a clear opt-in toggle in iPhone Settings (#1517)

## Fixes
- Codex replies no longer duplicate or arrive garbled after fast output bursts, and queued follow-ups stop getting stuck when a completion event is lost (#1510, #1512)
- First-turn session titles are real summaries again — on Claude and Codex, identical across Mac, web, and Linux/Windows hosts (#1515)
- The sidebar data-stream animation now survives second turns and background registry refreshes (#1518, #1520, #1497)
- Favorited Grok models no longer show up mislabelled as OpenCode Go in the model picker and composer pill (#1519)
- OpenCode sessions sync their to-do checklist into the To-dos pane, including recovery for older sessions (#1507)
- iOS Code no longer shows the "Browser off" chip; browser safety controls moved to Settings > Browser (#1514)
- Hosted model picker ordering is consistent across every client (#1503)
- Fixed a duplicate first-send race in local Worktree sessions (#1502)

## Under the hood
- A full-repository security and correctness audit landed: 147 high-severity findings fixed across every platform, including hardened relay encryption, credential-scrubbed process environments, exactly-once session creation, durable transcript mirrors, and stricter release-artifact verification (#1517)
- Remote MCP servers can authenticate through your real browser session (#1501)
- Live provider pricing refresh across the Mac and Linux/Windows analytics engines (#1523)

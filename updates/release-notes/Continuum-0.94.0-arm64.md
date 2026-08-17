# Continuum 0.94.0

## Features
- The admin Customers and Users tabs now show tokens each customer burns on their OWN provider subscriptions (Claude, Codex, Gemini, …), as their devices report it — with coverage, freshness, a provider split, sorts, and CSV columns. Hosted usage stays in its own columns, so the two never double-count (#1571)
- Five superseded models left the Continuum-hosted lineup (Grok 4.5, Grok Composer 2.5, Gemini 3.1 Pro, Gemini 3 Flash, Opus 4.8) — the rail is now 16 current rungs, and the free tier's xAI trial rung moved to Grok 4.6 at the same rate, on every client including mobile (#1568)

## Fixes
- A hosted turn can no longer fail silently: an exhausted model chain answers with a readable error naming the model instead of an opaque 502 the CDN swallows, the Mac fails a turn that produced nothing for 3 minutes with an honest message instead of spinning forever, and the bundled OpenCode runtime now carries the entitlement it needs to actually start (#1569)
- Long multi-agent OpenCode turns no longer die at the 45-minute clock while a delegated sub-agent is still working: the parent's clock pauses during delegation, each sub-agent gets its own full budget, and a 3-hour backstop keeps everything finite (#1567)
- Mac prompt editors finally scroll: every composer grows to its cap and then scrolls the overflow instead of trapping it, with focus, paste, undo, and the Enter-to-send contract all kept intact (#1566)
- Edit chips now count the actual change instead of both sides of the surrounding context, so the per-edit numbers in the transcript stop reading as a suspicious symmetric +14 −14 — identically on Mac, web, mobile, and Linux/Windows hosts (#1570)

# Continuum 0.66.0

## What's new

- **Auto Model Mode** — pick "Auto" instead of a model and Continuum assigns a planner, executor, and cross-provider verifier from the providers you've connected, then runs plan → approval → execute → verify with visible routing reasons, live cost, receipts, and crash-safe resume. (#1252)
- **Multiple accounts for every provider** — add more than one Z.ai, OpenCode, or other vendor account (not just Claude/Codex), pick a preferred account per provider, and Auto Mode + new sessions respect it — with strict per-account credential isolation. (#1259)
- **Try Continuum App free for 7 days** — the base Continuum App plan now starts with a card-on-file 7-day free trial; $25/mo or $250/yr after, cancel anytime. (#1256)
- **Same picture on every client** — PR and merge status, real session titles, and all your onboarded repos now mirror to web and iPhone even when the owning computer is offline. (#1260)
- **Plan/Code toggle you can trust** — one shared source of truth across Mac, iPhone, web, and Linux/Windows hosts: approving a plan reliably flips the session to Code everywhere, and Cursor (which has no plan mode) no longer shows a Plan pill. (#1255)

## Fixes

- Working subagents stay visibly live with the data-stream animation and elapsed timer — the phantom "Started" status is gone. (#1253)
- iPhone reconnects to your computer automatically after the desktop app restarts or updates — no more sessions stuck on a read-only mirror while the host is online. (#1254)
- Continuum hosted inference now appears in the usage analytics legend on Mac and web. (#1257)

## Under the hood

- continuumcode.ai search-ranking fixes: docs canonicals now point at continuumcode.ai, tuned marketing metadata, and a crawlable app shell. (#1258)

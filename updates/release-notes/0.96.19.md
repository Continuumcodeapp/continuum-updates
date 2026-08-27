## What's new in v0.96.19

Connect once, use everywhere. A provider account you connect on any device now belongs to your Continuum identity, not to that device.

### Features
- **Your accounts follow you.** Connect Claude, Codex, Gemini, Cursor, Grok, OpenCode Go, OpenRouter, Z.ai or a custom provider once, on any Mac, Windows or Linux machine, and it shows up on every other device and in Continuum Cloud — no re-auth, no toggles. Turning an account off anywhere removes it everywhere.
- **Continuum Cloud runs your own accounts with your devices offline.** Cloud sessions run under the account you pick, even when the machine you connected it on is asleep. Cloud runners now support Gemini, Grok and Cursor alongside Claude, Codex and OpenCode.
- **Cloud is on for every org.** No entitlement setup: every account can spin up cloud workers (300 minutes and 1 concurrent session per week on the free lane).
- **Android catches up.** Account picker across all your hosts, a Cloud execution host, real repo and device pickers, sessions without a live host, and merged usage.
- **Usage that doesn't freeze.** Per-account usage is merged across hosts and stays visible when a host is offline.

### Fixes
- Windows/Linux hosts now share their accounts (they could only receive before) and install Cursor/Grok keys where those CLIs actually read them; installing one API key no longer wipes the others.
- Credential routes are rate-limited and audited; revoking an account purges its escrow, stops running Cloud sessions and tells every host to delete local copies.

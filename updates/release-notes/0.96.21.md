# Continuum 0.96.21

Connect from anywhere.

- **Connect an account from your phone, the web, or any computer.** The Connect sheet on iPhone, Android and the web is driven by a live capability catalog: paste an API key once for OpenRouter, Z.ai, Grok, Cursor or a custom provider and it is validated server-side and becomes usable on every device and in Cloud; Codex signs in with a device code from anywhere. (#1701)
- **Finish on a computer.** Providers that only support a desktop login (Claude, Gemini, Grok CLI) hand off with one tap to any Mac, Windows or Linux machine you own; the login completes there and the account syncs everywhere automatically. (#1701)
- **Custom providers follow you.** Custom provider definitions are stored with your identity, synced to every host and to Cloud runners, and migrated from device-local settings the first time each machine sees them. (#1701)
- **Refreshed tokens are written back**, mid-session, from Cloud runners and hosts, with a conflict rule so two devices never clobber each other. (#1701)
- **Revoking an account removes it everywhere**: a durable outbox fans the revocation out to every device that installed it, tombstones prevent resurrection, and removing a device can wipe its credentials. (#1701)
- **Cloud fix:** OpenRouter and Z.ai accounts run in Cloud without extra configuration (the runner ships built-in OpenCode settings), and the runner's error messages now name the actual provider. (#1701)
- Security floor: rate limits and per-member caps on connect/deliver/rotate, audit rows for every credential action, no secrets in any log or DTO. (#1701)

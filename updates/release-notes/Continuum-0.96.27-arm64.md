# Continuum 0.96.27

- **Linux and Go hosts publish workspace changes promptly and stay visible.** Durable session changes wake the publisher immediately, and unchanged mirrors emit a heartbeat within two ticks instead of going silent for about eleven minutes. (#1761)
- **Expired or unavailable provider logins fail the turn with a clear reason.** Claude, Codex, Gemini, Cursor, Grok, and OpenCode now persist a typed failure instead of leaving the turn pending; Cursor authentication is confirmed with a real model-capability probe. (#1761)
- **Claude and Codex reauthentication on Mac no longer loses credentials at the finish line.** Wrapped or pasted Claude tokens are reassembled and verified before replacing the saved account, while Codex accepts only a complete fresh login and preserves the previous account on cancellation, rejection, or inconclusive verification. (#1760)
- **Continuum Cloud is caught up.** The hosted execution and Bot desktop reliability updates packaged in 0.96.26 are now live in production.

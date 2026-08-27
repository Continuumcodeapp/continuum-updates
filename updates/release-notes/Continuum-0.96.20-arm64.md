# Continuum 0.96.20

Connect once, usable everywhere — for real this time.

- **Your accounts now show up on every device.** After 0.96.19, a live end-to-end run against production showed accounts connected on one machine were not appearing on Windows/Linux hosts or in Cloud. The causes are fixed: hosts can now publish and fetch the shared account catalog, the Mac no longer loops on re-installing an account after a restart, and Cloud runners start again (the Cloud runner service had been running stale code). (#1699)
- **Windows and Linux install every kind of account** — Claude, Codex, Gemini, Cursor, Grok, OpenCode, OpenRouter, Z.ai and custom — with named accounts, so two accounts of the same provider no longer collapse into one. A failed or empty catalog fetch never disables the providers you already signed into locally. (#1699)
- **iPhone and Android show one account list**: accounts on your live Mac and accounts in the cloud catalog, merged, with a source badge. Chat can pick a cloud account and model directly; the "Mac required" walls are gone. Android now identifies itself as Android across the mesh. (#1699)
- **Web Providers page** lists every connected account across your devices, shows where each is installed and whether it can run in Cloud, and lets you rename, rotate or revoke it. Cloud sessions launch with just the account — no host needed. (#1699)
- **Cloud runners** install Cursor credentials correctly, honour custom/OpenRouter/Z.ai model lists, write refreshed tokens back mid-session, and only report ready after a real health check. (#1699)
- **Ops:** the live "connect-once" end-to-end gate is now part of the release runbook, with a deployment canary. (#1699)

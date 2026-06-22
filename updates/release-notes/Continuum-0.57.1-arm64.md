# Continuum 0.57.1

A small reliability patch: your default preferences now survive app updates, and healthy secondary Claude accounts stop showing as logged out.

## Fixed

- **Your Preferences stop resetting after an update.** Settings → Your Preferences (your default provider, model, effort, and Plan/Code choice) no longer reverts to defaults after an app update — the values now persist reliably across launches, and anyone already affected has their settings restored automatically on next launch. (#733)
- **Secondary Claude accounts read as logged in when they are.** A healthy secondary Claude account (added via `claude setup-token`) no longer shows a red "logged out" dot in Settings → Providers. Account liveness is now checked against the same endpoint the usage gauge and the spawned CLI already use, so a working account shows green and re-login correctly flips it. (#734)

Ships build 272 for Mac (signed Sparkle feed).

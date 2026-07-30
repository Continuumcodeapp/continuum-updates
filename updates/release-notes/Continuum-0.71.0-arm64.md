# Continuum 0.71.0

Reliability release: cross-device session sync now works end-to-end, on every
platform.

## What's new

- **Your sessions follow you everywhere.** Sessions running on your Mac (or any
  computer) now appear on your iPhone, the web, and the desktop apps — with an
  icon showing which machine each one lives on. Archiving on one device finally
  sticks everywhere. (#1353, #1355, #1357, #1358)
- **Open a synced session and it's live.** Tapping a session from another
  computer now connects directly to that machine over your account mesh: full
  transcript, live updates, and a working composer — not a frozen read-only
  snapshot. (#1361, #1363, #1364)
- **Transcripts always load.** Saved cloud transcripts render on every client
  instead of showing an empty screen. (#1362)
- **The web app stays connected.** Fixed a bug that silently dropped the web's
  mesh connection every 25 seconds, plus a faster, cache-first Code sidebar
  that paints instantly on sign-in and opens transcripts in a single click.
  (#1354, #1356)
- **Focused navigation.** Chat and Cowork are tucked away on every client —
  Continuum opens straight into Code. (#1359)
- **Self-diagnosing sync.** A new one-command health check
  (`tools/verify-mesh-sync.mjs`) verifies the whole cross-device pipeline in
  seconds and names the broken link when something's off. (#1360)

## Under the hood

- Host devices now report themselves healthy from their first heartbeat, so
  clients connect to them automatically. (#1361)
- Removing a device archives its leftover sessions instead of leaving phantom
  "Offline" rows. (#1355)
- Hardened diagnostics across iOS connection paths — every connect failure now
  logs its exact reason. (#1364)

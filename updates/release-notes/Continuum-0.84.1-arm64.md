# Continuum 0.84.1

## Fixes

- **No more crash on the latest macOS 27 beta when plugging in an external display.** A macOS ViewBridge bug could abort the app while the menu-bar item re-ordered its window during display reconfiguration; Continuum now installs a narrow, fail-closed guard on the affected OS builds. (#1490)
- **OpenCode sessions survive heavy builds and long subagent reviews.** Compiler and tool processes no longer count against the runtime's strict 2 GiB ceiling — the combined process tree gets its own capacity-aware limit — and subagent orchestration uses the full turn deadline instead of being cut off at 10 minutes. A finished server's memory can no longer get a healthy one terminated. (#1489)
- **One managed API key per Mac.** The desktop app no longer accumulates duplicate hosted-inference keys from test builds or cache refreshes — the credential is now a managed singleton, and stale duplicates are revoked automatically without exposing key material. Manually created API keys are untouched. (#1492)
- **The chat elapsed timer no longer clips.** The readout keeps a stable width as it counts up (9.9s → 10.0s, 59.9s → 1m), on Mac and iOS, without reserving visible dead space in the bubble. (#1491)

# Continuum 0.89.0

## Features
- Kimi K3 joins Continuum inference: served through a new adapter sidecar with real per-class token accounting, so hosted billing reflects actual usage, and unsupported request shapes fall through cleanly to the next capacity rung instead of failing the turn (#1547)
- Inference admin adds provider and live-model dropdowns: pick a configured provider, fetch its model list from the source (Anthropic catalogs now follow pagination past 20 models), and support a model with one click — no more typing exact upstream model IDs (#1539)
- A pasted Cursor API key is now a full credential on every surface: Settings shows Connected instead of "Sign-in required", sessions spawn without a false auth gate, the account's display name persists, and a revoked key turns the row red instead of staying green (#1546)

## Fixes
- OpenCode Go usage meters work again: quota reads the authenticated usage API first with the dashboard scrape as fallback, parses the new nested contract on both the Mac host and the Go agent, and dashboard-only hosts keep their meters (#1543)
- Phantom sessions no longer linger on iPhone and iPad: hosts publish a complete active-session set so the cloud mirror can retire stale rows past the 500-row cap, and the Mac answers every fresh iOS reconnect on a persistent socket (#1544)
- Your own message renders above the reply on Claude sessions: the optimistic bubble anchors at its send boundary on Mac, iOS, and web — including sessions opened for the first time on a device (#1545)
- On iPhone, collapsed tool-run headers split into two readable lines — counts above, live command below — instead of a five-line wrap that squeezed the command to a stub; desktop and Mac keep their single row (#1548)
- Custom tools defined via the Responses API now translate correctly on the chat-completions gateway path (#1540)
- watchOS: fixed a 32-bit overflow in timestamp validation on arm64_32 that could break the watch build (dabdd54)

## Under the hood
- Cursor setup guide refreshed to match the current UI and key format, with a curl-based verification step (#1541, #1542)

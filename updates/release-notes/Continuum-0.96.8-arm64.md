# Continuum 0.96.8

## Features
- On iPhone, Continuum Plus is now an in-app subscription with a 7-day free trial. The app stays free if you have a Mac or Linux box of your own; the offer appears only when you try to run a task on Continuum Cloud without a plan (#1641)
- Buying Plus on iPhone unlocks hosted inference on Mac, web, and every other Continuum surface, and trying to buy a second plan on the web while subscribed through the App Store now points you at iPhone Settings instead of a Stripe portal that cannot see the subscription (#1641)

## Fixes
- Continuum Voice keys type again. An invisible listening overlay had been swallowing every tap, so the keyboard looked live while the field stayed empty. Action Button dictation still reaches the keyboard the same way (#1643)
- OpenCode sessions that fail to start now tell you the real reason: the error names the failing stage (hosted plan, model metadata, serve startup) instead of a blanket "opencode serve could not start", and a missing hosted plan brings up the upgrade prompt instead of a dead end (#1644)
- An MCP server stuck on a half-finished sign-in now recovers on its own: Continuum retries silently, and at most once a day reopens the authorization page to finish the handshake, instead of contributing zero tools forever with no explanation (#1644)
- A question prompt no host can answer no longer hangs the turn in a silent "Running" state; it is declined cleanly and the agent continues, and an undeliverable decline ends the turn with a visible reason (#1644)

## Under the hood
- The ws WebSocket library is patched to 8.21.3 across the cloud backend, relay, and fallback rendezvous, closing an uninitialized-memory disclosure and a memory-exhaustion denial of service (#1642)
- Apple subscriptions now record their App Store environment and bind strictly to the org that purchased them, tier follows the product actually renewed, and establishing an org plan from a phone requires an admin or a personal org (#1641)

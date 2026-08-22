# Continuum 0.96.9

## Fixes
- Live OpenRouter models (like Ox Alpha) now run correctly through OpenCode instead of failing with "model not found" right after you send. Partner models — Z.ai, Continuum hosted, OpenCode — keep their own routing, sessions are billed to the provider that actually ran them, and a malformed model selection falls back to the default instead of erroring (#1646)

## Admin
- The admin dashboard now shows Apple free-trial status on customer rows, and signup analytics include the device and country each account came from (#1648)

## Website
- 32 new guides, a Grok Bot cost calculator, a plan picker, and a head-to-head compare page went live on continuumcode.ai, all fact-checked against current xAI and Cursor pricing (#1649)

## Under the hood
- Signed-in web sessions now reach product analytics: the collector accepts an authenticated user identity instead of rejecting the batch, page views carry real page URLs, and identity claims require a valid session so nobody can spoof another account into the data. Page metadata is scrubbed of query strings before leaving the browser (#1647)
- The vitest test runner is patched to 3.2.6 in the fallback rendezvous service, closing a dev-only file-read advisory (#1645)

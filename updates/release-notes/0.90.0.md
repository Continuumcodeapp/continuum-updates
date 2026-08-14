# Continuum 0.90.0

## Features
- GLM 5.3 is now served on Continuum inference via OpenCode Go, alongside the existing GLM and Kimi lines (#1550)
- Session activity finally agrees across iPhone, Mac, and desktop: a per-turn activity signal rides the cloud mirror with a strict freshness window, so a session that is streaming on one device shows as streaming on all of them — and an absent signal falls back safely instead of guessing (#1549)
- iOS mesh connections now self-heal: four permanent-outage paths that could wedge the phone's connection to a Mac until an app restart now retry with a pure, unit-tested recovery policy (#1549)

- OpenCode startup now self-diagnoses and self-heals, and inference requests emit structured logs for faster support (#1552)

## Fixes
- Clients that accumulate streamed tool-call deltas (Cursor, OpenAI SDK helpers) no longer get a 400 from the inference gateway when replaying assistant tool_calls: the stream-only index key is accepted and stripped (b739937b)
- The Continuum Inference attach point on the Mac is named "Continuum" instead of the internal label (#1551)

## Under the hood
- Review fixes and site-app snapshot regeneration from the #1549 landing (4d033e7)

# Continuum 0.81.0

## What's new

- Codex can now run on Continuum's hosted gateway: full OpenAI Responses API support at `/v1/responses`, with correct tool-call and usage translation (#1435)
- DeepSeek V4 Flash is served on the hosted free lane (#1434)
- Action Button voice on iPhone is dramatically more responsive: presses register instantly every time, pauses no longer erase what you said, words appear live in the focused field while you speak, and a warm audio session makes back-to-back dictation immediate (#1437)
- Images and files an agent writes now appear as chips in iOS Code transcripts — tap to preview them full-screen (#1430)
- iOS now celebrates with confetti when an agent opens a PR, matching the Mac (#1431)

## Fixes and reliability

- Hosted billing is materially more accurate: cached and reasoning tokens are metered at their true rates instead of the full input price, and free-model usage records cleanly at $0 (#1440, #1438)
- Hosted model discovery only advertises models that can actually be served right now, on every client (#1442)
- The free lane's gateway now ships as a managed service in the box stack, with a deploy canary that streams a real completion through every advertised free model (#1439)
- Hosted stream failures surface as in-band error events instead of opaque 502s, with sanitized structured logging (#1443)
- Claude system instructions are preserved through the hosted proxy, and its release process is now transactional with automatic rollback (#1441)
- Menu bar gauges: weekly-only Codex no longer paints a phantom "0% now", and the Continuum item uses the shared compact countdown (#1433)
- DeepSeek V4 Pro and Qwen3.7 Max report their true 1M-token context windows (#1436)
- Agent CI runs the full test suite in its container again, and a Linux process-group signal hazard was fixed at the syscall level (#1432)

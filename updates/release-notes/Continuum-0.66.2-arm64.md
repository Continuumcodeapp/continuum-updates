# Continuum 0.66.2

## What's new

- **iPhone Code gets more powerful** — live archive-sync, a one-tap **Create PR** button in the top right, swipe-to-archive on sessions, and a little confetti when a PR lands. (#1287)
- **New hosted models on the way** — GLM 5.2 and Kimi K3 now appear as "Coming Soon" in the model picker. (#1278)

## Fixes

- **One computer owns the mesh** — two Continuum instances signed into the same account no longer fight over the mesh host role, so your devices connect to a single, stable host. (#1281)
- **Reliable session creation** — creating a session is now idempotent, so retries no longer spawn duplicate worktrees, and a relay frame-count limit no longer aborts a legitimate cold-sync on session create. (#1285, #1282)
- **iPhone polish** — the transcript no longer mis-folds during an active turn, and the Code "jump to latest" button actually scrolls to the bottom now. (#1283, #1284)
- **iPhone diff counter stays put** — the host re-pushes sessions when diff stats finish computing, so the counter no longer goes missing. (#1280)
- **Links open where you expect** — public URLs in chat open in your browser, with a Copy Link option. (#1266)

## Under the hood

- Streaming chat now sends roughly **3× fewer frames** over the wire — smoother updates with less overhead. (#1288)
- Tidied the Ask / compare tray by removing a redundant account chip. (#1264)
- Homepage: removed the "Continue with Google" button. (#1286)

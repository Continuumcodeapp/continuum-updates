# Continuum 0.59.1

A big one: live Plan↔Code switching without losing your turn, background sub-agents you can actually see, steered messages that never vanish, and a long list of chat-reliability fixes. Continuum also moves to a single $25/month subscription (annual $250) across every platform.

## Features

- **Switch Plan↔Code mid-turn without interrupting the session.** The toggle now switches the agent's mode live — no respawn, no "Request interrupted", and the plan you approved lands in the right-pane Plan section. Claude's AskUserQuestion forms render as a labeled, answerable tray right in the transcript. (#1019)
- **Background sub-agents stay visible.** Agents launched in the background keep their transcript row animated until they actually finish, then fold in the real completion time and summary — a turn waiting on background work no longer looks stopped. (#1014)
- **Sub-agent rows show what each agent is doing.** Running sub-agents display their task summary (like the worktree sidebar) instead of a generic "Explore", and settled runs show an honest Done / Failed / Stopped status instead of a frozen timer. (#1001, #1002)
- **One subscription, every platform.** Continuum is now $25/month or $250/year — sign up on the web, or subscribe on iOS, and the whole app unlocks everywhere. You still pay your model providers directly, with no markup. (#1018)
- **Snappier with many worktrees open.** Continuum now keeps upcoming session transcripts warm once you're past ~7 open sessions, so switching to the 8th, 9th, 10th tab stays instant. (#1008)

## Fixed

- **Steered messages no longer disappear.** Sending a follow-up mid-turn keeps your message as a real bubble in the same turn — the timer keeps its anchor, and "Request interrupted" noise is gone. A wedged Codex send now times out cleanly in 20s instead of hanging forever. (#1016, #1017)
- **Your first message in a new worktree is durable.** If provider attach or worktree setup fails, the opening message stays visible, editable, and retryable — never silently dropped. App Shot and attachment sends spawn optimistically with an instant provisional row. (#1009, #1007)
- **Sends self-heal.** Transient network blips show a "Reconnecting…" chip and retry safely in the background — the same message is never delivered twice. (#1016)
- **New Code tabs no longer inherit a sibling's transcript** when opened in the same worktree. (#1006)
- **User prompts stay visible during long background tasks** instead of scrolling out of retention. (#1004)
- **Plan mode stops popping permission cards** for ordinary tools — research quietly, approve once. The ExitPlanMode card is a clean "Approve & Code / Keep planning" choice. (#1005, #999)
- **Transcript polish:** compact JSON blobs render as readable markdown, empty "Thinking" rows are gone, duplicate Codex commentary and duplicate mode rows are deduped, and hover-to-copy is back on every settled message. (#1011, #997, #998, #1000)
- **Sidebar diff counts stay current** — no more stale badge after edits. (#1003)
- **The Create PR button updates the moment the agent's PR lands** (the confetti was right; the button now agrees). (#1015)
- **Codex usage gauges stop locking on STALE** when the provider jitters its reset timestamps. (#1012)
- **Usage from Continuum-managed worktrees is attributed to the parent repo** in Analytics instead of "Other". (#1013)
- **Clearer connection language** — user-facing "daemon" wording replaced with plain language throughout. (#1016)

## Under the hood

- The full Mac unit suite is green headless again (124 stale failures triaged to 0) with three real product bugs fixed along the way. (#996)
- Hardened Stripe + Apple billing rails with signature-verified webhooks and org-scoped subscriptions. (#1018)

Ships build 297 for Mac (signed Sparkle feed).

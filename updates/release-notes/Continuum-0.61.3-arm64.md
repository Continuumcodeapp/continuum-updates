# Continuum 0.61.3

Agentic sessions get legible: every sub-agent now shows up in the transcript with a provider tag, replies format as Markdown while they stream, and plan approvals surface a proper Approve tray. Under the hood, subscriptions go tiered with a prepaid usage balance, and loading spinners are gone for good.

## Added

- **Every sub-agent is visible in the transcript, tagged by provider.** A Fable or agentic session that fans out workers used to hide most of them behind the "N tool calls" fold once a turn completed. Sub-agent rows now stay above the fold with a provider dot — terra for Claude, graphite for Codex — and the worker's role (Explore, Plan, Codex, …), while routine Bash/Edit/Read calls keep collapsing as before. Parallel fan-outs render as distinct rows, each with its own live packet-stream and timer. (#1082)
- **Tiered subscriptions with a prepaid usage balance.** The Continuum plan now renders as a weekly usage gauge — just another provider on the Usage tab (Mac, iOS, web). Free tier runs OSS chat (DeepSeek + OpenRouter free models) with frontier models shown greyed with an upgrade path; paid tiers unlock everything. Power users can prepay a usage balance that covers overage past the weekly budget at pass-through model cost — no markup — with an optional auto-top-up when the balance runs low. Paid tiers resolve from the actual Stripe price, so higher plans get their full budget. (#1079, #1083)
- **Project logos in the Code sidebar.** Repos that carry a favicon or AppIcon in their checkout now show that mark on the sidebar automatically instead of a letter monogram. A custom image still wins; session-row badges match the header glyph. (#1077)
- **Loading is the orange data-stream everywhere.** Every indeterminate spinner wheel across Mac, iOS, Watch, and the web dashboard is replaced by the terra-cotta packet stream — the product's one loading language. Determinate progress bars stay. (#1081)

## Fixed

- **Streaming replies format live.** Bold, headings, inline code, links, and lists render as tokens arrive instead of showing raw `**`/`##` syntax until the turn settles — including paused "continue" turns, on every chat surface. (#1080)
- **ExitPlanMode shows its Approve tray again.** Plan-mode sessions no longer strand on "Waiting for result…": when the agent proposes a plan, a sticky Approve & run / Comment tray appears above the composer, and the session is never force-cancelled while it waits for you. Comment rejects the plan, prefills your refinement, and unblocks the turn. (#1078)
- **Second Claude accounts keep their gauges live.** Adding a second Claude subscription no longer sticks at STALE forever: truncated setup-tokens are rejected loudly at login, a throttled usage endpoint falls back to rate-limit headers without spending tokens on healthy accounts, and the poller stops hammering a rate-limited account so it can recover. Codex shows one clean weekly-limit line. (#1076)

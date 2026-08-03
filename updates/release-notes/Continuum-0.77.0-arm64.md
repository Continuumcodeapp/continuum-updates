# Continuum 0.77.0

## What's new

- **See what your AI coding actually costs — one command, no account.** `curl -fsSL https://continuumcode.ai/scan.sh | sh` reads the Claude Code, Codex, Gemini, Cursor, and Grok history already on your machine, prices every token locally, and separates the token value you burned from the cash you actually pay — your plans, their real prices, and what came back. Nothing leaves your machine unless you ask for the emailed breakdown, and even then delivery is confirmed opt-in. (#1407)
- **Your subscription is now an API you can actually find.** Settings → Account on web and Mac gains an Inference API panel: mint a key, choose OpenAI or Anthropic wire format, and copy a ready-to-run snippet for your harness — Claude Code, Codex CLI, plain curl, and more. Recipes pin the background model too, so the first background turn no longer fails, and the panel shows a neutral "checking your plan" state instead of an upsell while entitlements load. (#1412)
- **A guides library built to answer real questions.** 119 guides across ten clusters — pricing, installs, git worktrees, slash commands, rate limits, troubleshooting and more — join the site, and all 14 compare pages get real vendor logos, per-page visuals, and pricing figures that are checked and dated instead of hedged. (#1406)

## Fixes and under-the-hood

- The AI-coding-agents roundup is wired into the cluster it summarises — it links to every tool's compare page and they link back — and compare-page headings read in order. Page titles and descriptions now have a build-time guard keeping them inside the search-results window. (#1410, #1414)
- The scan report's upload endpoint is rate-limited with confirmed double-opt-in email delivery, and provider-history reads are memory-bounded against corrupt or oversized files. (#1407)

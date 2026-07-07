# Continuum 0.57.19

Two big new surfaces — Cowork and Org Control — plus multi-account usage, iOS-first onboarding, and a batch of accuracy and performance fixes.

## New

- **Continuum Cowork.** A new third surface between Chat and Code for folder-scoped agent work. Point Cowork at a folder and it gets durable project memory plus scheduled or on-demand runs that work autonomously — writes inside the folder auto-approve, while deletes, commands, and anything outside the folder ask first. Runs on your Mac or a Linux box, works with all six providers, and shows a live run timeline on Mac, iOS, and web.
- **Org Control (V2).** An enterprise control plane for teams: provision provider workspaces and keys, watch usage against per-team and per-member budgets, and automatically enforce limits (block, unblock, and model policy) when a budget trips. Comes with an admin dashboard for people, teams, budgets, subscription requests, and analytics.
- **iOS-first onboarding.** Your account is now the spine and devices attach to it, so you can sign in on iPhone first and add your Mac (or other devices) afterward without re-doing setup.
- **Multi-account Claude usage on Mac.** A second Claude account now shows a working secondary gauge and a combined account card, and the primary account self-heals if it gets into a bad state.

## Fixed

- **Historical Opus pricing.** Older Claude Code sessions that used Opus 4.6 or 4.7 now price correctly instead of showing $0 — including after a pricing refresh.
- **Analytics parity with ccusage.** Token and cost numbers line back up with `ccusage`.
- **Composer drafts persist.** In-progress text in the composer is saved and restored instead of being lost.
- **Renamed account labels in Usage.** The Usage view now reflects account labels you've renamed.

## Under the hood

- **Smoother with many sessions.** Running ~15 concurrently active sessions is now viable, via hot/cold stores, coalesced disk I/O, and tail-only transcript commits.
- **Serverless + device-mesh hardening.** Fixes for a broker connection leak, a revoke race, wake-fallback, mesh reconnect, and safer serverless account deletion.

Ships build 290 for Mac (signed Sparkle feed).

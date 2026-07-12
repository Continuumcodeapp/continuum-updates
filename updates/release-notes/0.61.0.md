# Continuum 0.61.0

Continuum Cloud sessions arrive: run agents on zero-setup managed cloud runners straight from the dashboard. On the Mac, chat and the sidebar get a batch of polish — real paragraph breaks in streamed status lines, one copy button instead of two, hover-to-archive for Cowork tasks, a data-stream cable that actually stops when the turn ends — and Personal Claude accounts now heal (and honestly report) their sign-in state.

## Features

- **Continuum Cloud serverless sessions.** Start a cloud session with zero setup — GCP-managed runners spin up on demand from the dashboard, with managed active-minute and concurrency limits per org. (#1042)
- **Archive Cowork tasks from the sidebar.** Task history rows now show the same hover-to-archive control as the Code sidebar, with an Undo toast in case a click was accidental. Archiving the open task safely closes its thread. (#1063)

## Fixed

- **Personal Claude status heals the moment you re-log in.** Pasting a fresh setup-token now revives the usage gauge and flips the status dot immediately — no restart, no permanent "Re-log in" button on healthy accounts. A rate-limited check no longer paints a working account as dead. (#1059)
- **"Re-log in" appears exactly when it should.** If a saved token is actually rejected by Anthropic, the row now turns red and offers the one-click re-paste — instead of showing green with no way to fix it. Transient network blips still stay quiet. (#1064)
- **Agent status lines get real paragraph breaks.** Grok and other delta-streaming agents no longer glue status sentences together across tool calls ("…done.Looking…") — each status renders as its own paragraph. (#1061)
- **One copy button per answer.** Completed assistant answers showed two hover copy controls (the footer chip and a body glyph); the footer is now the single affordance. Your prompts and error bubbles keep their hover-copy. (#1060)
- **The data-stream cable stops when the turn ends.** The Code sidebar animation no longer keeps running after a model finishes — the chat's own turn state is now authoritative, with the coarse session status used only while a background session's store is evicted. (#1062)
- **Settings copy cleanup.** OpenCode Go no longer carries a "Recommended" badge and Z.ai Coding's subtitle drops the "via OpenCode" attribution. (#1058)

## Under the hood

- The signup → payment funnel is now measurable end-to-end: the dashboard fires a server-side `payment_completed` event when a subscription activates, native Google Analytics events carry real session identifiers (GA was silently dropping everything), and the marketing site reports pageviews. (#1056)
- Relay endpoint tests now assert the branded `relay.continuumcode.ai` primary that went live 2026-07-11, clearing the last latent red in the shared suite.

# Continuum 0.64.3

The biggest release since the cloud-sync program: the phone experience gets fixed end to
end, hosted inference arrives fully hardened (dark until cutover), the founder admin panel
ships, and every platform moves together.

## Features

- **Hosted inference, ready behind the switch.** A metered, tier-enforced OpenAI/Anthropic-
  compatible gateway with subscription pooling, atomic budget reservations, priced-model
  enforcement, fail-closed capacity routing, and full tool-calling through the Anthropic
  bridge — plus personal `cont_sk_` API keys with a dashboard panel. Everything stays dark
  until the master toggle flips. (#1170, #1178, #1189, #1195)
- **Continuum hosted models as a first-class coding provider.** Pick Claude/GPT/Grok/Gemini
  "on Continuum" in the Code picker; keys mint automatically and opencode is configured for
  you — gated by entitlement with honest upgrade states. (#1177, #1188)
- **Zero-setup hosted chat.** A signed-in user lands in chat and can talk immediately — no
  paired device — with a free-tier weekly allowance and a clean upgrade nudge at the cap.
  (#1197)
- **Founder admin panel** at admin.continuumcode.ai: cross-customer growth, revenue,
  marketing, and usage; runtime inference capacity + per-user consumption; comp grants and
  emailed invites (Stripe codes minted with product-scoped restrictions) — every sensitive
  read and money-moving action audit-logged append-only. (#1180, #1187, #1191, #1196)
- **Ultra promo codes.** Allowlisted higher-priced SKUs can now offer promotion codes at
  checkout (100%-off 3-month Ultra for friends), fail-closed to the $25-only rule when
  unconfigured. (#1185, #1179)
- **All outbound email on AWS SES** with a hand-rolled, vector-verified SigV4 signer —
  injection-safe templates, no new dependencies — plus self-hosted Listmonk for
  newsletters at emails.continuumcode.ai. (#1195, #1199)
- **Cloud runners bill your own subscription.** A managed runner installs your provider
  credentials at boot over a least-privilege signed pull — creds sealed at rest, scoped to
  the runner's own agent, never touching the GCP broker. (#1193)
- **Web + iOS mesh onboarding.** The browser defaults to Cloud with a Mac-parity
  "Run on" chip (no more device wall), and GitHub connect lives in Settings on web and
  iOS — with identity-fenced sign-out handling. (#1190, #1198)
- **CLI: context, palette, and cross-provider memory.** A real context-occupancy readout,
  a safer command palette, and opt-in memory shared across providers (plainly disclosed,
  off by default, stored securely with instant revocation). (#1200)

## Fixed

- **Phone sessions load their transcripts — instantly and in real time.** Opening a
  worktree session no longer shows a blank screen: live sessions register for cloud
  transcript pushes and fall through to the durable cloud copy when a host can't answer.
  (#1176)
- **The turn timer matches the machine doing the work.** No more resetting to 0 on every
  open — it anchors to the host's own turn start, Mac and Linux alike. (#1176)
- **The transcript is buttery.** Scroll frames went from ~45–82 ms to ~1.3 ms by caching
  parsed markdown off the main thread; text wraps exactly at screen width; wide code
  blocks scroll in place. (#1176, #1175)
- **Session cards: every live session animates** its data stream from one shared clock;
  the green blinker and "live/idle" label are replaced by the Mac-style **+N −M** diff
  counter, computed identically to the Mac sidebar on both Mac and Linux hosts. (#1176)
- **Plan approvals work on the newest Claude Code** — the tool-based ExitPlanMode shape is
  recognized (and named foreign tools can never false-positive into plan approval), with
  the plan rendered as full markdown in the approval card. (#1183, #1184, #1192)
- **Mid-turn "Send now" can't strand your message or brick the session** — a failed
  interrupt keeps the draft queued and the session recoverable. (#1186)
- **Release Notes opens a readable changelog** instead of raw markdown. (#1182)
- Coverage reports render as proper diagrams; SDK transcript duplicates are gone; the
  relay test gate runs from any checkout path. (#1175, #1173, #1169)

## Under the hood

- Wire v52/v53: per-session diff stats + the hosted-coding capability, additive and gated.
- Migrations 0038–0048 (member API keys, comp grants + audit, superadmin admin + audit,
  hosted reservations, invites, free-tier caps).
- Stripe promo gating composes with data-driven plan prices; comp grants are read-time
  evaluated with full audit trails. (#1168, #1181)

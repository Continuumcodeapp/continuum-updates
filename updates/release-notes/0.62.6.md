# Continuum 0.62.6

Grok CLI usage finally shows up in Analytics — with exact token counts and true API-equivalent spend — and Code sessions get their smart one-to-five-word sidebar names back even after Claude rotates its sign-in token. Plan approval is now a single, uncluttered surface. On iPhone, Continuum goes freemium: a free account lands straight in Chat, with Code and Cowork available on upgrade.

## Features

- **iPhone freemium.** Continuum on iOS no longer gates the whole app behind a paywall — a free account lands directly in Chat with a set of ready-to-use models. Code and Cowork show an in-tab Subscribe prompt with a dismissible Pro sheet, and multi-account renames (for example "Default" → "Work") now carry across Mac and iPhone usage. (#1100)

## Fixed

- **Grok CLI usage now shows up in Analytics.** Plain `grok` command-line sessions contribute authoritative per-prompt token totals and API-equivalent dollar spend — including cached input and output — while your SuperGrok quota stays a separate gauge. Histories refresh incrementally, survive file replacement or truncation, and pricing uses current xAI rates with the 200K long-context threshold applied only to genuine single requests (no overstated spend on multi-call aggregates). (#1108)
- **Smart Code session names come back after a token refresh.** New Code sessions recover their semantic one-to-five-word sidebar and worktree labels when Claude rotates its sign-in token, instead of falling back forever to the first words of your prompt. Title generation retries only after a genuine authentication rejection and never overwrites a newer account you just signed into; your custom-renamed sessions are always preserved. (#1109)
- **One place to approve a plan.** The inline plan card in the transcript is now read-only — Approve & run and Comment live only in the composer tray, so there's a single, unambiguous surface for acting on a plan instead of duplicate controls. (#1107)

## Under the hood

- The primary Claude usage gauge keeps refreshing even when a second account is present or needs re-authentication, and relay reconnects no longer force-bounce a socket that's still connecting or freshly connected. (#1100)

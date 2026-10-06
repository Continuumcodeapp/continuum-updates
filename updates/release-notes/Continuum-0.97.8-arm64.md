# 0.97.8

GPT-6.1 Sol and Claude Sonnet 5.5 on every client, Bots v2, native Code workflows and computer use on Windows and Linux in the desktop app, and a smaller, faster-updating Continuum Unified.

## Models

- GPT-6.1 Sol is available on Mac, iPhone, Android, web, Windows, Linux, Continuum Unified for Mac and Continuum Cloud. It sits above GPT-6 Sol in every model list at the same price, with a 1.05M context window. ChatGPT accounts need Codex CLI 0.159.2 or later, so the bundled Codex moves to 0.159.2.
- Claude Sonnet 5.5 is available everywhere too, above Sonnet 5, and takes the `sonnet` alias. 1M context, adaptive thinking, low through max effort.
- Model pickers on Unified, web and the phone read the live model catalog, so new models show up without an app update.
- Kimi K3 agentic turns with tool calls are served directly instead of falling back.

## Bots

- Bots v2 on web, the desktop apps on Mac, Windows and Linux, and the phone: repo bots, teammate cards in the lead thread, plugin refresh, and a failed turn you can retry.
- Your selected bot survives switching organizations.

## Continuum Unified and the desktop apps

- Code workflows from the native Mac app: Spawn, repo search, Run and Preview, the command palette and keyboard shortcuts.
- Computer use works on Windows and Linux (X11 and Wayland), with a grant you approve per action.
- Updates download only what changed, and the app bundle is smaller (886 MB, down from about 1 GB).
- New sessions open reliably: accounts load, worktree setup errors are shown, and an archived or stale session is never reopened.
- First-run provider setup scrolls on small windows, so Continue is always reachable.
- Usage cards no longer clip in Unified.
- Settings are honest about what each provider supports, including environment variables, roots and the browser switch.
- App Shots, Voice, Cowork and the Plugins tab are removed from Unified; organization settings open on the web.

## Account, usage and billing

- Settings > Continuum Inference Usage breaks usage down by API key and label.
- Delete your account from Unified, the web dashboard or the phone, including when you own an organization.
- Free plans include one API key; more keys come with a paid plan. Existing keys keep working.
- The Plus free trial is limited to one per card.
- Going over your hosted allowance now stops in-flight requests within a minute.

## Reliability and security

- Phone pairing gives each phone its own token; your host's master key never leaves the host.
- Signing out on a phone revokes that phone's own credential and stops its pushes.
- A host re-registers its relay key on its own when controllers keep failing to verify it.
- Code no longer flickers to a loading skeleton when a host reconnects.
- Cursor probes no longer trigger a macOS "Keychain Not Found" prompt.

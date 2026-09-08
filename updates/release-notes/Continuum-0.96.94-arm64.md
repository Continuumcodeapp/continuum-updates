# 0.96.94

The Continuum bot now works where your team already talks. Mention it in a Slack or WhatsApp thread and it answers there, on its own computer, with approvals you grant from the thread. The command line got the same treatment, and sessions finally follow your account across every device you own.

This is the first public release since 0.96.86 and rolls up everything from 0.96.87 through 0.96.93.

## Channel bots

- Mention the bot in a bound Slack channel and the thread becomes a bot turn, with its own computer, screenshots, an Open computer link and handoffs back to the app. (#2000, #2003, #2013)
- The same bot answers on WhatsApp. Approve an action by replying with its number, and the thread stays live for the 24-hour session window. (#2009)
- Bind a channel to a bot from the Bots tab on Mac, iPhone, web and Expo. Connected apps show which channels each bot answers in. (#2008)
- Approve or decline what the bot wants to do from inside the thread, and take a run over from the bot without leaving the channel. (#2012)
- Connected apps get their own channels: per-client Slack install links, WhatsApp binding, channel webhook events, and usage attributed to the right client. (#2011)

## Bots

- Pin your bot leaders. A grid of large avatar tiles sits at the top of the bots rail on every client, with Pin and Unpin in the context menu and the Manage sheet. Pins follow your identity across devices. (#2027)
- Move to Folder lists partner folders such as TrueWave, Chronic and Shabang. Bots created through the Partner API appear under their partner folder. (#2006)
- Bot computers keep a screenshot before they sleep, so the pane shows the last screen behind Click to wake instead of black. (#1977)
- Partner Bot API for connected apps: partner keys, clients, bots, shared or dedicated computers, embed, signed webhooks, usage reporting and partner sign-on. (#1991, #1992, #1993)

## Command line

- Bots are a fourth channel in the command line, on the same contract as Slack and WhatsApp: a rail with personal and partner folders, send, transcript, a living status card, approvals, routines, and waking or opening a bot computer. The terminal app gets a Bots tab. (#2023)
- The command line pairs itself on the Mac that runs the hub, with no token to configure, reads your live usage gauges, and updates itself over a signed release. (#2018)
- The terminal app repaints only the cells that changed. Streaming is coalesced onto a frame budget, markdown renders as it arrives, and the transcript holds your scroll position while output streams in. (#2020)
- Typing stays responsive while a reply streams: keystrokes echo in about nine milliseconds at the 95th percentile. (#2024)
- Install the agent from any host with a one-line script served straight from the site. (#2015, #2016)

## Sessions, accounts and usage

- Archive or restore any session from any device, including projects and chat threads that live on another machine. A session on an offline Linux box can be archived from the Mac and disappears everywhere at once. (#1974, #1987)
- Settings has one Account tab on Mac, web and Expo. The iPhone keeps its purchase row. (#1978)
- Organisation settings are the team page: create an organisation, invite teammates by email or link, manage members and roles. Usage upload, device mesh and cloud sync are always on. (#1983)
- Every extra provider account gets a shell command named after its label, such as `claude-personal` and `codex-personal`. (#1984)
- Providers and Models confirm a saved key or a sign-in at once, and account rows read Cloud ready, This device only, or Needs sign-in instead of listing devices. (#1986)
- Usage shows real quota for Codex and Cursor accounts of every shape, and says plainly when an API key cannot report quota rather than showing a fabricated zero. (#1982, #1985, #1989)
- Continuum Plus now starts with a 7-day free trial, Bot included, on web, Mac, iPhone and Expo. (#1990)
- Spend Control: a corporate admin centre for budgets and limits. (#1702)

## Fixes

- The Mac app no longer freezes at launch. A credential lock was being taken on the main thread while a background verification held it. (#1995)
- The Code rail shows one row per repository, merged across accounts and hosts, and chat or Frontier sessions no longer appear as phantom project rows. (#2004, #2014)
- Cost by repo dedupes repositories across accounts and hosts, and the "Not priced" caption is gone. (#2002, #1994)
- The Fable row stays in Usage when Claude reports only a session window, and an account that has not published yet is no longer drawn as a 0% weekly gauge. (#2007)
- Renaming an account sticks after you sign in, including on the menu-bar popover chips. (#2010)
- Files an agent creates now show their contents in the diff pane instead of coming back blank. (#2026)
- The free model rail recovers instead of retrying a rate-limited provider, and hosted sessions carry the session header those providers require. (#2019)
- The Projects header is back to its previous layout, and the new-session device picker orders devices by how often you use them. (#2005, #1976)
- Routine runs are billed against their own turn, so a user turn running at the same time no longer lands its cost on the routine. (#2001)
- Rebuilding the command line no longer raises a macOS Keychain prompt each time. (#2025)
- Codex sessions start again when the model probe is slow. The hub waits for the probe, falls back to the cached model catalogue instead of refusing the session, and no longer answers 503. (#2028)

# Continuum 0.62.0

Spend numbers you can trust: token costs now price Anthropic's five-minute and one-hour cache writes separately — with the rate that was actually in effect when the usage happened — and the Mac, Continuum Cloud, and the web dashboard all agree to the cent. Chat gets a big one too: Broadcast can now **Synthesize** the replies from every provider into one cited answer. Plus clickable links, configurable App Shot trigger keys, and a batch of transcript fixes.

## Features

- **Broadcast → Synthesize.** After every selected provider finishes replying, one click compiles their answers into a single cited response — each claim traceable to the exact reply it came from — using the summarizer model you picked in the composer. Continue from the synthesis and it becomes a normal solo chat with just your question and the answer. (#1086)
- **Pick your App Shot trigger keys.** The both-modifiers screenshot chord is now configurable: both Options (default), both Commands, or both Shifts — switchable in Settings and applied live, with no accidental fires while another modifier is held. (#1091)
- **Links in chat are actually clickable.** PR links and bare URLs in replies open in your browser on click, show the hand cursor, and reveal the full destination on hover. Only http/https/mailto links are ever openable. (#1088)

## Fixed

- **Token spend is now correct across every surface.** Anthropic 5-minute vs 1-hour cache writes are priced at their real rates (1.25× vs 2×), historical usage uses the rate active at the time (including Sonnet 5's launch promotion, which expires Sept 1), OpenAI cached input is validated before discounting, and a corrupt pricing download can no longer wipe known rates. Mac analytics, Continuum Cloud, and the web dashboard now compute the identical dollar figure. (#1092)
- **Background sessions keep their activity.** Switching a session between providers (Claude → Codex/Grok/Cursor) no longer risks losing chat activity or leaking a stale feed into the new provider's transcript. (#1093)
- **Slash-skill messages show what you typed — once.** Invoking a skill now renders one user bubble with your exact `/skill arguments` text and one SKILL.md attachment, instead of duplicate provider payloads and stray markdown attachments. Two invocations of the same skill no longer merge into one. (#1090)
- **Finished sub-agents say Done.** Synchronous Agent runs that returned their full report no longer sit on "Started" with a running timer forever; only genuinely backgrounded agents stay on Started until they finish. (#1089)
- **Interrupted turns show how long they ran.** A turn you stop (or that errors) now displays its elapsed time in the footer, even though there's no final answer to copy. (#1085)
- **Slash-skill search ranks by name match.** Typing `/rev` puts `review` above skills that merely mention "review" in their description — exact name, then prefix, then contains, then description-only. (#1087)
- **Less noise beside the live timer.** The redundant "thinking…" caption next to the active-turn data stream is gone; the stream and timer are the working-state cue. (#1084)

## Under the hood

- Xcode project generation is now byte-deterministic across worktrees (a checkout-named group was churning the project file on every machine), and duplicate idempotency-key handling releases its reservation before an early-exit response so a fast retry can't see a phantom "in flight" conflict. (#1091, #1086)

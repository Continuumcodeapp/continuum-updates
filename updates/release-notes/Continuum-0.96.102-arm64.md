# 0.96.102

Continuum Cloud now runs on every provider you have connected, and starts in seconds instead of minutes. Your accounts follow you to every machine you own rather than living on the one you happened to sign in from. Archiving a session is instant. And the Usage tab tells you what each pull request cost you.

## Cloud sessions, on every provider

- Claude, Codex, Cursor, Grok, OpenCode and Continuum hosted all run in Cloud now, with your own accounts. Pick the account you want and the runner authenticates as you.
- A Cloud session starts in seconds. A pre-booted runner is claimed on demand instead of waiting for a cold boot, so the wait dropped from around two minutes to single-digit seconds in the warm case.
- The first message you type is delivered on every provider. Sessions that opened silent and stayed empty now run the prompt you actually sent.
- Cloud is a first-class Auto target, so a routed run can pick a Cloud runner the same way it picks a local one.
- Archive and restore work per session, with the real reason shown when one is refused instead of a generic failure.
- A sleeping lease no longer blocks a new session, an abandoned open no longer strands a billable runner, and a Bot computer lease no longer takes Cloud away from the rest of your account.

## Your accounts, on every device

- An account you connect once is offered on every host you own. Choosing a second machine no longer shows an empty picker while the account you connected sits unused on another device.
- Accounts are reconciled continuously. A device that is missing one is repaired automatically rather than staying short until someone notices.
- Switching hosts is instant, because the account list no longer waits on that machine to answer over the network before showing you anything.

## Faster, and quieter

- Archiving is immediate. The row leaves the sidebar the moment you click, instead of waiting for the agent to shut down first. Archiving a whole branch no longer takes tens of seconds.
- Usage opens instantly and uses far less CPU in the background, reading only what is new instead of re-parsing your whole history.
- A restart no longer starves the app with a backlog of usage events.

## Usage, and what each PR cost

- Every session is attributed to the pull request it belongs to, so you can see spend and tokens per PR, grouped by repo, across every harness and every machine on your account.
- One provider filter scopes the whole tab, and spend is charted day by day so a spike has a date.

## Models and providers

- Kimi K3 is selectable and works for real coding turns, including tool use.
- Cursor publishes its real catalogue once you have signed in, rather than only offering Auto.
- Gemini 3.8 Flash, GLM, DeepSeek, Grok 4.6 and GPT-6 Astra all serve on Continuum hosted, and a model with no capacity now says so and suggests another instead of hanging.
- Your Continuum allowance counts only Continuum usage. Bringing your own key no longer eats into it.

## Smaller things

- Every device gets the new agent automatically on each release.
- The device picker marks each host with its platform, and Continuum Cloud appears in the iPhone picker.
- The composer remembers your model and effort, and a remote device offers that host's catalogue rather than this one's.
- Auto shows why it chose each model, on Mac, web and desktop.
- A usage bar that is not empty no longer reads as 0%.

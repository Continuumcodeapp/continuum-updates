## What's new in 0.96.79

Models and inference
- GPT-6 Astra is available on Continuum inference and through your own ChatGPT subscription on every client, with effort from low to max and long-context pricing shown correctly in Usage (#1938)
- Gemini 3.8 Flash is the Antigravity model. Gemini 3.5 Flash, 3 Flash and 3.1 Pro leave the pickers, and their history keeps its pricing (#1928, #1929)
- Continuum inference no longer serves Claude Fable 5 (the 5.0 model). Fable 5.1 stays the hosted Fable, and past usage keeps its pricing (#1938)

Accounts
- The account pill is back in New Session whenever a provider has two or more connected accounts, even if one of them cannot run right now (#1940)
- A primary account that needs sign-in can be removed from this Mac and your other devices. It returns once the provider is signed in here again (#1935)
- A cancelled or hung provider sign-in no longer leaves "Another sign-in is already running" stuck, the Codex sheet completes while the CLI is still open, and a duplicate ChatGPT account gets a clear Try again (#1925)
- Antigravity re-authentication finishes from the credential files, and an already signed-in account offers Sign in with a different account (#1926)

Usage
- Antigravity shows live weekly numbers without the IDE or CLI open, refreshes an expired Google token on its own, and is a weekly-only provider on every client like Codex and Grok (#1931, #1932, #1941)
- A second Claude account's usage is polled at a pace that keeps it out of the header fallback, and a rotated sign-in bundle is re-adopted at launch so the account shows its own Fable window (#1940)
- Switching a provider card between accounts no longer shifts the percentage, caption and rail, and the outgoing number no longer ghosts behind the new one (#1930)
- The Antigravity arched-A mark replaces the old sparkle in the menu bar, popover, widgets, watch, web and Expo (#1927)

Mac
- A second click on a menu-bar gauge collapses its panel again on macOS 26, and the gauge follows the account picked on the Usage card (#1933, #1937, #1941)
- Voice dictation starts faster. The microphone route and the on-device speech model are warmed at launch, so the first press of the mic no longer waits several seconds (#1940)
- Chrome extension: renamed "Continuum: AI Coding", and a Web Store install now connects to the native host (#1936)

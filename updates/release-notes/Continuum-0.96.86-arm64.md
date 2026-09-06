# 0.96.86

## Features

- Bots now live in one list on every client. The Mac, web, iPhone and Expo apps share the same rail: a single flat list of your bots, a compose menu to start a new one, and folders to keep them organised. (#1943, #1960, #1961, #1962)
- The bot computer got a cleaner pane. Start, stop and restart moved behind a header gear so the view stays out of your way, the thread ellipsis became a direct computer button, and the roster row now carries the per-bot actions. (#1946, #1948)
- A sleeping bot computer says so. The pane shows a sleep screen instead of a dead frame, and a banner tells you when the bot needs your attention. (#1947)
- Setting up a session on iPhone no longer blocks the screen. It floats as a widget you can dismiss, so you can keep reading the thread while it connects. (#1949)
- iPhone widgets were redesigned to match the app, and every account you connect to a provider now has its place: pick the account on the small widget, see two side by side on the medium one, all of them on the large one, and per-account chips on the overview. (#1966)
- GPT-6 Astra now offers the full range of reasoning efforts, from low through max. (#1951)

## Fixes

- Signing in on iPhone works again. A fresh app-start sign-in was rejecting the AuthKit URL and dead-ending; it now completes on both the iPhone app and Expo. (#1954, #1955)
- Your provider accounts follow you, not the device. The same account list appears on the Mac, iPhone, web and Expo, one entry per provider identity instead of a duplicate per device, and your devices are sorted most-used first. (#1952, #1959, #1963)
- A Claude account whose session window has elapsed keeps all three usage bars instead of dropping to one. (#1942)
- The Mac composer shows its account chooser straight away and refines the details in the background, instead of making you wait on a blank menu. (#1950)
- Antigravity stopped asking for your keychain every time you opened the menu bar. (#1944)
- The Usage tab no longer shows an empty gauge when you are signed out, and the analytics cache waits for a signed-in account before it fills. (#1953, #1956)
- The Bot tab appears right after you sign in inside the app, without a relaunch. (#1957)
- Re-enrolling a phone rebinds it to whoever is signed in now, and the error copy finally says what went wrong when a device is not bound to the controller. (#1958)
- The bot roster shows each bot's last message, so a bot with a live thread no longer reads "No messages yet". (#1965)
- Removed the Gemini quota Live Activity from the lock screen and Dynamic Island. (#1964)

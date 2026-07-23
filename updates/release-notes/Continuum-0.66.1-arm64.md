# Continuum 0.66.1

## What's new

- **Do more from your iPhone** — archive sessions, review pull requests, and use the terminal directly from mobile, so you can drive work on the go without reaching for your computer. (#1275)
- **Headless agents keep themselves current** — Linux and Windows agents now self-update daily in the background, so remote hosts stay on the latest Continuum without a manual reinstall. (#1269)
- **Sessions open instantly** — a new open cache makes switching into a session feel immediate instead of waiting on a reload. (#1275)

## Fixes

- **Your devices stay connected for hours** — a deep pass on mesh reliability fixes the reconnect churn, the WebSocket "death spiral", and the fleet-connect race that could leave Mac, iPhone, Linux, or Windows stuck on a read-only mirror or unable to connect to your computer at all. (#1263, #1271, #1272, #1275)
- **Linux and Windows hosts connect reliably** — a device-id matching bug that blocked host control on those platforms, and a live server error during device enrollment, are both fixed. (#1268, #1267)
- **Google One Tap is back** — one-click sign-in on the homepage, restored after the site rewrite dropped it. (#1262)
- **Lighter and smoother** — lower idle CPU usage and smoother streaming Markdown rendering during long responses. (#1265)

## Under the hood

- Persistent connection diagnostic logging now runs on every client (Mac, iPhone, Linux, Windows, and web) so mesh issues are caught and root-caused faster. (#1270)
- Additional security hardening, including a serverless SSRF fix. (#1265)
- Cloud database migration reconciling the workspace-mirror foreign keys with the canonical schema. (#1261)

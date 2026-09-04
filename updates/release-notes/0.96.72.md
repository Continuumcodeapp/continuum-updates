## What's new in 0.96.72

Bots
- Bots make authenticated GitHub contributions. Ask a bot for a change in a connected repo and it opens a Code cloud session, works on a continuum/ branch and opens the pull request. A work card in the thread shows Running, Done or Failed, the files changed, View PR and Open Code tab, on Mac, iPhone, web and Expo (#1921)
- Bot computers stay on between conversations, wake with one click, and run routines unattended. Screens attach in under a second, recover on their own after a dropped connection, and stay on the display the bot is using (#1775, #1789, #1826, #1828, #1874, #1891)
- Chat keeps going while the computer wakes, your message leaves the box the moment you send it, and failed or long-pending turns show in the thread with a Retry (#1829, #1872, #1885, #1913)
- Taking over the screen is one step: the expanded screen is the driving surface, and the pane no longer lies about sleep or a dropped session (#1777, #1864, #1914)
- Bots remember useful context, nudge you proactively, build reusable skills, exchange messages with allowed bots and rooms, and can mount any open MCP server with per-tool permissions (#1779, #1781)
- The Bot tab shares the Code tab's model picker, header and composer on every surface (#1841, #1853, #1858, #1860)
- Free accounts see the Bot plans with a product carousel and checkout in Stripe (#1897, #1900, #1903, #1906)

Accounts and providers
- Connect GitHub is sign in, authenticate, done: every repository across every account you can access is imported (#1845)
- Providers connected on the Mac show up on iPhone and Cloud again, and a stale rejected-credential block clears itself (#1865, #1868, #1870, #1875, #1882)
- Turn escrowed providers on from iPhone and Expo while away from the Mac; disconnected rows offer Reconnect with a new key (#1920)
- Reconnecting a Claude account turns green right after sign-in, and a rate-limited usage check no longer demotes a signed-in account (#1837, #1850, #1851)
- Two Codex instances signed into the same ChatGPT account are detected instead of showing duplicate usage (#1922)

Usage
- Costs match the raw records: Claude subagent turns are counted, Grok uses the amount the Grok CLI was billed, Fable 5.1's cache-read rate is applied, and the table, chart and leaderboard share one range and one cost path (#1923)
- Tokens or Cost toggle on the analytics header and the model leaderboard, on Mac and iPhone (#1877, #1890)
- iPhone Usage shows one card per account with the Work/Personal toggle (#1854, #1857)

Models and inference
- Claude Fable 5.1 everywhere Fable 5 was: the model picker, Continuum inference, web, iPhone and Linux hosts (#1840)
- Muse Spark 1.3 is the free Continuum Inference model, and DeepSeek V4 Flash is free, served through OpenCode with Zen retried first (#1880, #1907)
- Hosted Grok 4.6 is billed at xAI's official card (#1923)

Mac
- Clicking inside the menu-bar usage card never brings the Continuum window to the front (#1918, #1844)
- Settings uses the same bottom-left rail as Code and Bots, and the rails read Code, Bots and Settings (#1889, #1895, #1896)

iPhone and iPad
- The Code tab keeps repos and sessions while the host wakes; New Session lists your GitHub repos and shows Mac-connected accounts on Cloud (#1915, #1916, #1917)
- The Bot composer paperclip offers Photo or File (#1886)

Admin
- Funnel shows Connected GitHub and Used Continuum Inference; Customers sort and filter; Prompts are collapsed and attributed by harness, surface and origin (#1879, #1902, #1905)

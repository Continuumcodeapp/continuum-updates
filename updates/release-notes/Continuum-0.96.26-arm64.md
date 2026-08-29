# Continuum 0.96.26

- **Unavailable providers now fail fast instead of leaving a turn pending.** If the selected provider is dead or signed out on a host, every client receives the same typed reason immediately. Durable receipts keep retries deduplicated across restarts and ambiguous acknowledgements. (#1754)
- **Workspace publishes keep moving when one provider account hits its cap.** The host skips and reports the capped account, then publishes the rest instead of failing the whole workspace. (#1746)
- **Plan mode waits for a real plan before asking for approval.** Approve, Comment, and the send hold appear only when the agent has actually finished its plan. (#1744)
- **Grok can ask follow-up questions again on every client.** The `AskUserQuestion` tray is restored on Mac, iPhone, web, and Android. (#1745)
- **Bot desktop turns are more reliable.** Inference and file transfers survive VM startup changes, empty completions no longer strand turns, recreated desktops require fresh creation proof, new relay bootstraps apply without a reboot, and computer actions capture live frames and surface failures. (#1749, #1750, #1751, #1752, #1753, #1755)
- **Grok model picks stay selected when worktree trails collide.** This carries the 0.96.25 internal fix forward to every 0.96.26 client. (#1743)
- **Under the hood:** Signed Mac tests now use an isolated app identity, and the dark, allow-listed Bot roster stays consistent across Mac, iPhone, web, Android, and desktop. (#1734, #1747, #1748)

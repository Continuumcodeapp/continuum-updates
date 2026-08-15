# Continuum 0.91.0

## Fixes
- Phone-to-Mac relay connections now recover from both directions: when the Mac redials while the phone's connection persists, the phone answers the fresh handshake instead of going silent — closing the "sometimes doesn't work to the Mac" gap left after 0.89.0's reconnect fix (#1553)
- OpenCode startup self-diagnoses and self-heals on every platform: a wedged OpenCode process is detected, explained in the session, and restarted instead of leaving dead meters and unresponsive chats (#1552)

## Under the hood
- Inference requests emit structured logs end to end, so support can trace a failing request through the gateway without guesswork (#1552)
- The relay no longer declares its externally-routed production domain in wrangler config, and the relay pairing trust model is now documented with its one residual risk (4805db9, 63be7fd)

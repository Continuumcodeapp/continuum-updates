# Continuum 0.96.16

## Features
- Devices on your phone now show honest per-host status. Each row reports its own link, "host offline" or "relay error" says which side failed, and Retry reconnects that host instead of whichever one was preferred (#1682)
- 24/7 connection diagnostics on every client: rotating logs kept for 30 days on Mac, iPhone, Linux, and Windows, every line tagged with the host and session it belongs to, an Export diagnostics row in iPhone Settings, and automatic uploads so a failure can be investigated later without the device in hand (#1682)

## Fixes
- Linux and Windows hosts no longer go dark after 30 days. The host-to-cloud control session now renews itself before it expires and repairs itself after a failed dial, so a host that was "online" but unreachable from the phone is a thing of the past (#1682)
- A single unreachable host no longer disconnects the others: the Mac row stopped flapping when the Windows host was down, and the phone no longer opens rendezvous the cloud already reported undeliverable (#1682)
- Relay reconnects wait for the old socket to close before opening a new one, ending the overlapping sockets that displaced each other every reconnect (#1682)
- The Windows and Linux desktop apps restart their agent with backoff instead of showing a fatal dialog when it exits (#1682)
- Error copy for Cloud Compute connect and revoke names the actual problem again instead of "Something went wrong" (#1682)

## Under the hood
- The Cloudflare relay path is retired: relay.continuumcode.ai now terminates on the Continuum box itself, so long-lived sockets are no longer cut off at two hours. The release preflight refuses to deploy if relay DNS ever points back at Cloudflare, and the relay Worker deploy is gone from the repo (#1682)
- The relay and the cloud now log every session join, leave, displacement, and push outcome; container logs are retained on the box, and `GET /v1/fleet/sessions` exists instead of 404ing on every refresh (#1682)

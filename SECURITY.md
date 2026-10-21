# Security

## Reporting a problem

Report security problems privately by email to support@tokenusage.dev. Please do not open a
public issue, pull request or discussion for them. Say what you found, how to reproduce it and
how to reach you.

Please do not run load or denial-of-service tests against tokenusage.dev.

## Scope

- This repository. It holds client configuration only: plugin and extension manifests,
  `.mcp.json` and the MCP Registry manifest `server.json`. It contains no server code, and
  installing it adds no code that runs on your machine; your client connects to the hosted
  server over HTTPS.
- The hosted MCP server at https://tokenusage.dev/mcp and the JSON endpoint
  https://tokenusage.dev/api/resets.

## What the server does

Both return public data only: Codex usage-limit reset announcements recorded from
@thsottiaux's public posts on X, the record shown at https://tokenusage.dev/resets. They are
read-only and need no key or sign-in; there are no accounts. Requests do not change the reset
data, and the server stores nothing about who calls it. The hosting platform, Google Cloud,
keeps standard request logs; https://tokenusage.dev/privacy describes them.

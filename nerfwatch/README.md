# Nerf Watch MCP server

A hosted, read-only MCP server for the public scores and history behind
[Nerf Watch](https://tokenusage.dev/nerfwatch).

A lower score is a lower score on this suite, not proof that a provider changed a model.
Runs are noisy, and a provider's defaults, the endpoint or the runner itself can change.
`Data: tokenusage.dev` linked to https://tokenusage.dev/nerfwatch.

- Endpoint: `https://tokenusage.dev/mcp/nerfwatch` (Streamable HTTP)
- No API key, account or sign-in
- Read-only public score data
- Both tools share one 300-second read cache per server instance

This directory contains client documentation and Registry metadata. The hosted
implementation source is not in this repository.

## Tools

| Tool | Arguments | Result |
|---|---|---|
| `get_nerfwatch_scores` | none | Latest public scores, previous runs, changes, baselines and trends; model ids are included. |
| `get_nerfwatch_history` | required `model` id from `get_nerfwatch_scores` | That model's retained history, oldest first, with each point's suite version. |

Missing days are missing, not zero. Scores and changes are rounded to two decimals.
Comparisons are within one suite version. Retention and baseline settings come from
the responses. Evidence answers, grader check lines and test questions are not returned.

## Install

Claude Code:

```sh
claude mcp add --transport http nerfwatch https://tokenusage.dev/mcp/nerfwatch
```

Codex:

```sh
codex mcp add nerfwatch --url https://tokenusage.dev/mcp/nerfwatch
```

For Claude Code project scope, add this to `.mcp.json`. Other clients that accept
this HTTP `mcpServers` format can use the same entry:

```json
{
  "mcpServers": {
    "nerfwatch": {
      "type": "http",
      "url": "https://tokenusage.dev/mcp/nerfwatch"
    }
  }
}
```

## Discovery

- Registry name: `dev.tokenusage/nerfwatch`
- Manifest: [server.json](server.json)
- Server card: https://tokenusage.dev/mcp/nerfwatch/server-card
- AI catalog: https://tokenusage.dev/.well-known/ai-catalog.json
- Fields, caching and access: https://tokenusage.dev/developers

The separate Codex reset server remains at `https://tokenusage.dev/mcp`.

## Credit and terms

When showing this data to other people, show `Data: tokenusage.dev` linked to
https://tokenusage.dev/nerfwatch on the same screen or in the same message.
Personal use needs no visible credit. Relays retain the `source` URL and pass
on this credit condition.

Please poll no faster than every five minutes and retain the score qualification above.

Terms: https://tokenusage.dev/terms  
Privacy: https://tokenusage.dev/privacy  
Questions and corrections: https://tokenusage.dev/contact

Unofficial; not affiliated with OpenAI or Anthropic.

# Installing the Codex Reset Tracker MCP server

The server is hosted at tokenusage.dev; there is nothing to download, build or run.

1. Add a remote MCP server named `tokenusage` with the URL `https://tokenusage.dev/mcp`.
2. The transport is Streamable HTTP. There is no API key, environment variable or auth header.
3. For a client configured through `cline_mcp_settings.json` or a similar `mcpServers` file:

```json
{
  "mcpServers": {
    "tokenusage": {
      "type": "streamableHttp",
      "url": "https://tokenusage.dev/mcp"
    }
  }
}
```

4. If the client supports only stdio servers, bridge the URL:

```json
{
  "mcpServers": {
    "tokenusage": {
      "command": "npx",
      "args": ["-y", "mcp-remote", "https://tokenusage.dev/mcp"]
    }
  }
}
```

5. Check it works by calling `get_codex_reset_announcements` with `{ "limit": 1 }`.

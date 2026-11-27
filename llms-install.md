# Installing Nero Reviews: verified job reviews for trades (remote MCP server, no install needed)

Nero Reviews: verified job reviews for trades is a hosted remote MCP server. There is nothing to download, build or run, and no API key.

Add this to the MCP settings file (in Cline: MCP Servers, Configure, then cline_mcp_settings.json):

```json
{
  "mcpServers": {
    "nero-reviews": {
      "type": "streamableHttp",
      "url": "https://nero-reviews.nerolabs.workers.dev/mcp",
      "disabled": false,
      "autoApprove": []
    }
  }
}
```

Save the file. The server's tools appear straight away. To check it works, ask the assistant to list the server's tools.

Docs: https://nero-reviews.nerolabs.workers.dev/docs

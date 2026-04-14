# MCP: marketplaces and example configs

Use MCP only with **trusted** servers; never commit API keys (use env vars or your host’s secret handling).

## Where to discover servers

| Product | Discovery |
|---------|-----------|
| **Cursor** | [Cursor Marketplace](https://cursor.com/marketplace) (official plugins) · [cursor.directory](https://cursor.directory/) (community servers and configs) |
| **VS Code + Copilot** | Extensions view: search **`@mcp`** for the MCP gallery · Docs: [Add and manage MCP servers in VS Code](https://code.visualstudio.com/docs/copilot/chat/mcp-servers) · Schema: [MCP configuration reference](https://code.visualstudio.com/docs/copilot/reference/mcp-configuration) |
| **Protocol** | [Model Context Protocol](https://modelcontextprotocol.io/) |

## Cursor — project `mcp.json`

Path: **`.cursor/mcp.json`** (project) or `~/.cursor/mcp.json` (global).  
Docs: [Cursor MCP](https://cursor.com/docs/context/mcp).

Example (**illustrative** — replace server names and use `${env:...}` for secrets):

```json
{
  "mcpServers": {
    "example-stdio": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-filesystem", "${workspaceFolder}"]
    },
    "example-remote": {
      "url": "https://example.com/mcp",
      "headers": {
        "Authorization": "Bearer ${env:EXAMPLE_MCP_TOKEN}"
      }
    }
  }
}
```

## VS Code + Copilot — workspace `mcp.json`

Path: **`.vscode/mcp.json`** (often created via *Install in Workspace* from the `@mcp` gallery).  
Official example shape (from VS Code docs):

```json
{
  "servers": {
    "github": {
      "type": "http",
      "url": "https://api.githubcopilot.com/mcp"
    },
    "playwright": {
      "command": "npx",
      "args": ["-y", "@microsoft/mcp-server-playwright"]
    }
  }
}
```

**Note:** Cursor and VS Code use **different** top-level keys (`mcpServers` vs `servers`) and field names. Do not copy one file to the other without converting.

## This lab repo

Do **not** commit real tokens. If you add `.cursor/mcp.json` or `.vscode/mcp.json` with secrets, keep them **local** or use environment interpolation only.

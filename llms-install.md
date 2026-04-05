# Bitpoort MCP Server Setup

Bitpoort is a hosted MCP server -- no local installation needed.

## 1. Get an API Key

Go to https://bitpoort.com/register and enter your email. You will receive a verification email. Click the link to get your API key (starts with `bp_`). All accounts start with $10 free credit.

## 2. Configure Your MCP Client

Add the following to your MCP configuration:

```json
{
  "mcpServers": {
    "bitpoort": {
      "url": "https://bitpoort.com/mcp/sse",
      "headers": {
        "X-API-Key": "bp_YOUR_KEY_HERE"
      }
    }
  }
}
```

### Config file locations

- **Claude Desktop**: `~/Library/Application Support/Claude/claude_desktop_config.json` (macOS) or `%APPDATA%\Claude\claude_desktop_config.json` (Windows)
- **Cursor**: Settings > MCP Servers
- **Cline**: `.cline/mcp_settings.json` in your project

## 3. Verify

Ask your AI assistant: "What whale transactions happened in the last hour?"

If it responds with real on-chain data, you are connected.

## Troubleshooting

- **401 Unauthorized**: Check that your API key is correct and starts with `bp_`
- **429 Too Many Requests**: You have hit the rate limit (60/min free, 300/min subscription)
- **Timeout**: Tool calls have a 30-second timeout. Try a simpler query.

## Links

- Docs: https://bitpoort.com/docs
- Register: https://bitpoort.com/register
- Status: https://bitpoort.com/v1/health

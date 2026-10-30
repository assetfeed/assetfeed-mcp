# AssetFeed MCP servers

<img src="logo.png" alt="AssetFeed" width="96" align="right">

Two hosted (remote) MCP servers from [AssetFeed](https://assetfeed.com). There is nothing to install: point your MCP client at the URL and sign in.

| Server | URL | Tools |
|---|---|---|
| AssetFeed Market Data | `https://api.assetfeed.com/mcp` | 18 read-only tools, 5 prompts |
| AssetFeed AI Detection | `https://api.assetfeed.com/mcp/ai-detection` | `detect_ai_text`, `detect_ai_url` |

This repository holds the public listing metadata (`server.json` for the [MCP Registry](https://registry.modelcontextprotocol.io)) and setup notes. The server code is not open source.

## AssetFeed Market Data

Mention counts, asset recaps and market snapshots for crypto, stocks, ETFs, forex and commodities in Claude, ChatGPT and Cursor.

AssetFeed's market data MCP server gives your AI app read-only access to how often assets come up in tracked sources, with context around it. Ask for mention counts over 7 and 30 days, trending assets, related companies and products, extracted events such as listings or lawsuits, and recap articles for a single asset. Search and compare tools cover crypto, stocks, ETFs, forex pairs and commodities, and five built-in prompts walk through briefs, comparisons and sector scans. For crypto there is also a daily market recap for past days. Sign in with OAuth or use an API key; every plan can connect; each tool call uses AssetFeed credits. Educational data, not financial advice.

[![AssetFeed Market Data MCP connector](https://glama.ai/mcp/connectors/com.assetfeed/market-data/badges/score.svg)](https://glama.ai/mcp/connectors/com.assetfeed/market-data)

Details: [assetfeed.com/mcp](https://assetfeed.com/mcp)

## AssetFeed AI Detection

Check an English text or a page address for AI-written passages from Claude, ChatGPT or Cursor. The result is an estimate, not proof.

AssetFeed AI Detection is a read-only MCP server with two tools. `detect_ai_text` takes pasted text and shows how much of it reads as AI-written, passage by passage. `detect_ai_url` fetches a public web page by its address and checks the text it finds. Ask in plain language, for example "Is this draft written by AI?", and your assistant calls the tool for you. It works on English text of about 50 to 30,000 words; other languages and very short texts are not checked. No detector is right every time, and formal or heavily edited human writing can be flagged, so read the marked passages yourself. Sign in with OAuth or use an API key. Each tool call uses AssetFeed credits.

[![AssetFeed AI Detection MCP connector](https://glama.ai/mcp/connectors/com.assetfeed/ai-detection/badges/score.svg)](https://glama.ai/mcp/connectors/com.assetfeed/ai-detection)

Details: [assetfeed.com/ai-content-detector](https://assetfeed.com/ai-content-detector)

## Connect

**Claude (web, desktop, mobile, Claude Code):** open [assetfeed.com/mcp](https://assetfeed.com/mcp) and use the Claude one-click setup, or add the server URL as a custom connector and sign in with your AssetFeed account.

**ChatGPT (web):** Plugins → + → Add custom MCP server, name it AssetFeed, paste the server URL, choose OAuth and sign in with your AssetFeed account. Works on Business, Enterprise and Edu plans, and Pro with read-only access. An admin may need to allow the server first. It can't be added in the phone app.

**Cursor and VS Code:** one-click setup is on [assetfeed.com/mcp](https://assetfeed.com/mcp). Other clients without sign-in can use an API key from [assetfeed.com/api-keys](https://assetfeed.com/api-keys) sent as a Bearer header:

```json
{
  "mcpServers": {
    "assetfeed": {
      "url": "https://api.assetfeed.com/mcp",
      "headers": { "Authorization": "Bearer YOUR_API_KEY" }
    }
  }
}
```

Use `https://api.assetfeed.com/mcp/ai-detection` for the detector.

## Support

Questions and problems: [assetfeed.com/contacts](https://assetfeed.com/contacts).

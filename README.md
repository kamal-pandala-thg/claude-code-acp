# ACP adapter for Claude Code (Unbound)

[![npm](https://img.shields.io/npm/v/%40zed-industries%2Fclaude-code-acp)](https://www.npmjs.com/package/@zed-industries/claude-code-acp)

Use [Claude Code](https://www.anthropic.com/claude-code) from [ACP-compatible](https://agentclientprotocol.com) clients such as [Zed](https://zed.dev)!

This fork integrates with [Unbound AI](https://getunbound.ai) to route API calls through their multi-provider gateway for optimized model routing and cost optimization.

This tool implements an ACP agent by using the official [Claude Code SDK](https://docs.anthropic.com/en/docs/claude-code/sdk/sdk-overview), supporting:

- Context @-mentions
- Images
- Tool calls (with permission requests)
- Following
- Edit review
- TODO lists
- Interactive (and background) terminals
- Custom [Slash commands](https://docs.anthropic.com/en/docs/claude-code/slash-commands)
- Client MCP servers

Learn more about the [Agent Client Protocol](https://agentclientprotocol.com/).

## How to use

### Prerequisites

Get your Unbound API key from [gateway.getunbound.ai](https://gateway.getunbound.ai)

### Zed

Configure Zed to use this adapter with Unbound by adding to your settings (`cmd+,` on macOS):

```json
{
  "agent_servers": {
    "Claude Code (Unbound)": {
      "command": "node",
      "args": ["/path/to/claude-code-acp/dist/index.js"],
      "env": {
        "UNBOUND_API_KEY": "unb-your-api-key-here"
      }
    }
  }
}
```

Replace `/path/to/claude-code-acp` with the actual path to this repository after building.

To use Claude Code, open the Agent Panel and select "Claude Code (Unbound)" from the `+` button menu in the top-right.

Read the docs on [External Agent](https://zed.dev/docs/ai/external-agents) support.

### Other clients

- Neovim via [CodeCompanion.nvim](https://codecompanion.olimorris.dev/configuration/adapters#setup-claude-code-via-acp)

Setup instructions for other clients are coming soon. Feel free to [submit a PR](https://github.com/zed-industries/claude-code-acp/pulls) to add yours!

#### Installation

Build locally:

```bash
git clone <this-repo>
cd claude-code-acp
npm install
npm run build
```

You can then use `claude-code-acp` as a regular ACP agent:

```
UNBOUND_API_KEY=unb-... node dist/index.js
```

## License

Apache-2.0
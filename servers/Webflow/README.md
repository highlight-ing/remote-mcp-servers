# Webflow MCP Server

This README provides information about the Webflow MCP server.

| Feature        | Details                        |
| -------------- | ------------------------------ |
| Name           | Webflow                        |
| Category       | CMS                            |
| URL            | `https://mcp.webflow.com/sse`  |
| Authentication | OAuth2.1                       |
| Maintainer     | [Webflow](https://webflow.com) |

Build faster with Webflow's APIs using LLMs. Connect directly to your site data, access collection schemas, generate functional code, and solve development challenges with context from your Webflow projects.

## Webflow's official MCP server

For developers using AI-powered tools like [Cursor](https://www.cursor.com/) or [Claude Desktop](https://claude.ai/download), we provide a [Model Context Protocol (MCP)](https://www.npmjs.com/package/webflow-mcp-server) server that enhances your AI agent's understanding of your Webflow projects. The MCP server has tools that enable AI agents to access real-time information about your sites, collections, and other objects, enabling more accurate and contextual code suggestions and troubleshooting. To see a full list of tools, see the [MCP server documentation](https://www.npmjs.com/package/webflow-mcp-server).

## Install Webflow's official MCP server

### Remote installation

Get started quickly by installing Webflow's remote MCP server, which uses OAuth to authenticate with your Webflow sites. For local installation, see the [local installation](#local-installation) section below.

#### Cursor

1. Go to `Settings → Cursor Settings → MCP`
2. Click `+ Add New Global MCP Server`
3. Paste the following configuration into `.cursor/mcp.json` (or add the `webflow` part to your existing configuration)

```json
{
  "mcpServers": {
    "webflow": {
      "command": "npx mcp-remote https://mcp.webflow.com/sse"
    }
  }
}
```

4. Save your file. Cursor will automatically open a new browser window showing an OAuth login page where you can authorize the Webflow sites you want the MCP server to access.

#### Claude Desktop

1. Open `Settings → Developer`
2. Click "Get Started" or `Edit Config` to open the configuration file.
3. Open the `claude_desktop_config.json` file in a code editor and paste the following configuration (or add the `webflow` part to your existing configuration):

```json
{
  "mcpServers": {
    "webflow": {
      "command": "npx",
      "args": ["mcp-remote", "https://mcp.webflow.com/sse"]
    }
  }
}
```

4. **Save and restart Claude Desktop**

   Save the file and restart Claude Desktop `(command/ctrl + R)`. When Claude restarts, it will automatically open a new browser window showing an OAuth login page where you can authorize the Webflow sites you want the MCP server to access.

#### Windsurf

1. Navigate to `Windsurf - Settings → Advanced Settings`
2. Scroll down to the `Cascade` section → `Add Server` → `Add custom server +`
3. Paste the following configuration (or add the `webflow` part to your existing configuration):

```json
{
  "mcpServers": {
    "webflow": {
      "command": "npx",
      "args": ["mcp-remote", "https://mcp.webflow.com/sse"]
    }
  }
}
```

4. Click `Save`. Windsurf will automatically open a new browser window showing an OAuth login page where you can authorize the Webflow sites you want the MCP server to access.

> **Warning:** Webflow's remote MCP server is currently experimental
>
> These installation methods rely on the [`mcp-remote` npm package](https://www.npmjs.com/package/mcp-remote), which is currently considered experimental as of 05/01/2025.

**Resetting your OAuth token**

If you need to reset your OAuth token, you can run the following command before restarting your MCP client.

```bash
rm -rf ~/.mcp-auth
```

### Local installation

If you prefer to install the MCP server locally, you can do so by following the steps below. Local installation requires Node.js and npm to be installed on your machine.

**Prerequisites**

- Node.js version 18 or higher
- npm version 10 or higher

**Steps**

1. Get a Webflow API token from the [Webflow API Playground](https://developers.webflow.com/data/reference/token/authorized-by?playground=/data/reference/token/authorized-by)

2. Add the following snippet to your client's configuration file:

```json
{
  "mcpServers": {
    "webflow": {
      "command": "npx",
      "args": ["-y", "webflow-mcp-server"],
      "env": {
        "WEBFLOW_TOKEN": "YOUR_API_TOKEN"
      }
    }
  }
}
```

> **Note:** Remember to replace `YOUR_API_TOKEN` with your actual Webflow API token.

3. Add the MCP server to your AI client:

#### Cursor

1. Go to Settings → Cursor Settings → MCP
2. Click `+ Add New Global MCP Server`
3. Paste configuration into `.cursor/mcp.json`
4. Save and verify server status
5. Start interacting with the MCP server

   In the "Chat" window, switch to "Agent Mode" and start interacting with the MCP server. You can ask the agent things like:

   - "When was my site last published?"
   - "What were the last 5 CMS items published to this site?"
   - "Based on my last 5 blog posts, can you generate some ideas for new blog posts?"
   - "What are the current SEO issues on my site and how can I fix them?"

6. **Send us feedback!**

   We're just getting started with this, so we'd love to hear from you! If you'd like to see more tools or have any feedback, please log an issue on [GitHub](https://github.com/webflow/mcp-server/issues).

#### Claude Desktop

1. Open Settings → Developer
2. Click "Get Started" or `Edit Config` to open the configuration file.
3. Paste configuration into `claude_desktop_config.json`
4. **Restart Claude Desktop**

   Once you've restarted Claude Desktop, the MCP server will be shown in the Developer settings menu

5. Start interacting with the MCP server

   In the "Chat" window, start interacting with the MCP server. You can ask the agent things like:

   - "When was my site last published?"
   - "What were the last 5 CMS items published to this site?"
   - "Based on my last 5 blog posts, can you generate some ideas for new blog posts?"

6. **Send us feedback!**

   We're just getting started with this, so we'd love to hear from you! If you'd like to see more tools or have any feedback, please log an issue on [GitHub](https://github.com/webflow/mcp-server/issues).

---

## Documentation for LLMs

Webflow's documentation is optimized for consumption by AI assistants, making it easier for these tools to generate accurate code examples and guidance.

- Use [`https://developers.webflow.com/llms.txt`](https://developers.webflow.com/llms.txt) to access the LLM-readable documentation. This optimized structure helps LLMs respond with accurate code snippets and multi-step sequences.
- Additionally, you can access markdown versions of any documentation page to provide a more structured and context-rich experience for LLMs. To access the markdown version of a page, add `.md` to the end of the URL. For example, this current doc is available as a markdown file at [`https://developers.webflow.com/data/docs/ai-tools.md`](https://developers.webflow.com/data/docs/ai-tools.md).

**Installing docs on Cursor**

1. In the chat, click the `@` button
2. Find the "Docs" option
3. Click "Add new doc"
4. Paste in the following link: `https://developers.webflow.com/llms.txt`

Once configured, reference Webflow's documentation by typing `@Docs` in your chat window and selecting "Webflow" from the list.

Refer to the main [Awesome Remote MCP Servers list](../../README.md) for more servers and client information.

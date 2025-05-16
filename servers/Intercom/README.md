# Intercom MCP Server

This README provides information about the Intercom MCP server.

| Feature        | Details                          |
| -------------- | -------------------------------- |
| Name           | Intercom                         |
| Category       | Customer Support                 |
| URL            | `https://mcp.intercom.com/sse`   |
| Authentication | OAuth2.1                         |
| Maintainer     | [Intercom](https://intercom.com) |

# Model Context Protocol (MCP)

Learn how to use the [Model Context Protocol (MCP)](https://modelcontextprotocol.io/introduction) to enable AI agents to securely access and interact with your Intercom data whenever helpful.

> **Note:** Currently the Intercom MCP server is only supported in US hosted workspaces.

## What is Model Context Protocol?

MCP is a protocol that enables AI tools and applications to connect with Intercom's data and services in a secure, standardized way. It provides a structured method for AI models to:

- Find and retrieve Intercom data (conversations, contacts, etc.)
- Access specific tools and functionality provided by Intercom
- Maintain context about your Intercom workspace when working with AI assistants

## How MCP Works

Intercom hosts a remote MCP server at `mcp.intercom.com/sse` that follows the authenticated remote MCP specification ([docs](https://modelcontextprotocol.io/specification/2025-03-26/basic/authorization)). This server handles requests from AI tools and provides access to Intercom data through a secure, event-based interface using Server-Sent Events (SSE).

When an AI tool or application needs to access Intercom data:

1. The tool connects to Intercom's MCP server
2. Authentication verifies the user's permissions
3. The tool can then access relevant Intercom data and functionality
4. The connection remains live to receive updates as needed

## Benefits of Using MCP

- **Secure Access**: All data access is authenticated and authorized
- **Standardized Interface**: Consistent interaction pattern across different AI tools
- **Contextual Understanding**: AI assistants maintain awareness of your Intercom environment
- **Increased Development Efficiency**: Retrieve and interpret customer data from Intercom via your internal AI tools to be more efficient in your work

## Setting things up

> **Troubleshooting:** It's early days for MCP. If you experience connection issues, we've found restarting the client or disabling and re-enabling the MCP server to help.
>
> As a last resort consider clearing your local auth files `rm -rf ~/.mcp-auth`

Here's how you can configure popular AI tools to work with Intercom's MCP server:

### Claude.ai

1. Go to your settings at https://claude.ai/settings/profile.
2. Under the **Integrations** section click on **Add more**.
3. Use `https://mcp.intercom.com/sse` as the server URL.
4. Select the Intercom workspace you would like to access, review permissions and accept if everything looks right.

### Cursor

1. Open Cursor Settings (`CMD/CTRL + Shift + J`)
2. Go to the **MCP** section
3. Click on **Add new global MCP server**
4. Add the following configuration to `mcp.json`

```json
{
  "mcpServers": {
    "Intercom": {
      "type": "Command",
      "command": "npx -y mcp-remote https://mcp.intercom.com/sse"
    }
  }
}
```

### Windsurf

1. Open Windsurf settings (`CMD/CTRL + ,`)
2. Go to the **Cascade** section
3. Press the **Add Server** button then **Add custom server**
4. Add the following configuration to `mcp_config.json`

```json
{
  "mcpServers": {
    "Intercom": {
      "command": "npx",
      "args": ["-y", "mcp-remote", "https://mcp.intercom.com/sse"]
    }
  }
}
```

### VS Code

1. Hit `CMD/CTRL + Shift + P` and search for **> MCP: Add Server...**
2. Select **stdio**
3. Enter `npx mcp-remote https://mcp.intercom.com/sse` as the command
4. Enter `Intercom` as the Server ID.
5. Hit `CMD/CTRL + Shift + P` and search for **> MCP: List Servers**
6. Start Intercom's MCP server

Refer to the main [Awesome Remote MCP Servers list](../../README.md) for more servers and client information.

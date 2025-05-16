# Linear MCP Server

This README provides information about the Linear MCP server.

| Feature        | Details                      |
| -------------- | ---------------------------- |
| Name           | Linear                       |
| Category       | Project Management           |
| URL            | `https://mcp.linear.app/sse` |
| Authentication | OAuth2.1                     |
| Maintainer     | [Linear](https://linear.app) |

![Abstract image of a drive with Linear's logo and the words "Remote MCP server"](https://webassets.linear.app/images/ornj730p/production/1647255e1279a82092d1ce8ce8e34a4b897c2eaf-3600x1800.png?q=95&auto=format&dpr=2)

Your AI models and agents can use our official MCP server to access your Linear data in a simple and secure way.

Connect to our MCP server natively as a new [Claude Integration](https://anthropic.com/news/integrations), or by using the [`mcp-remote`](https://github.com/geelen/mcp-remote) module in Cursor, Windsurf, and other clients.

We're following the authenticated remote [MCP spec](https://modelcontextprotocol.io/specification/2025-03-26), so the server is centrally hosted and managed. It has tools available for finding, creating, and updating objects in Linear like issues, projects, and comments — with more functionality on the way.

We're excited to see how you and your agents use Linear data to power your workflows. If you have questions, feedback, or requests for new MCP tools, please let us know.

Elapsed00:00

Seek to:00:00 / Duration00:00

Remaining00:00

*We want to thank our partners at Cloudflare and Anthropic for helping us get up and running. For anyone in the community looking to build their own MCP server, Cloudflare provides excellent* *[guides and hosting options](https://blog.cloudflare.com/remote-model-context-protocol-servers-mcp/).*

## [Setup Instructions⁠](#setup-instructions)

- Navigate to **Settings** in the sidebar on web or desktop
- Scroll to **Integrations** at the bottom and click **Add more**
- In the prompt enter:
  - Integration name: `Linear`
  - Integration URL: `https://mcp.linear.app/sse`
- Make sure to enable the tools in any new chats

### [Cursor⁠](#cursor)

1.  CTRL/CMD Shift J to open Cursor Settings.
2.  Select **MCP**.
3.  Select **Add new global MCP server**.
4.  Add the following:

```
{
  "mcpServers": {
    "linear": {
      "command": "npx",
      "args": ["-y", "mcp-remote", "https://mcp.linear.app/sse"]
    }
  }
}
```

1.  CTRL/CMD P and search for **MCP: Add Server**.
2.  Select **Command (stdio)**
3.  Enter the following configuration, and hit enter.

`npx mcp-remote https://mcp.linear.app/sse`

1.  Enter the name **Linear** and hit enter.
2.  Activate the server using **MCP: List Servers** and selecting **Linear**, and selecting **Start Server**.

3.  CTRL/CMD + , to open Windsurf settings.
4.  Under Scroll to Cascade -> MCP servers
5.  Select **Add Server -> Add custom server**
6.  Add the following:

```
{
  "mcpServers": {
    "linear": {
      "command": "npx",
      "args": ["-y", "mcp-remote", "https://mcp.linear.app/sse"]
    }
  }
}
```

1.  CMD , to open Zed settings.
2.  Add the following:

```
{
  "context_servers": {
    "linear": {
      "command": {
        "path": "npx",
        "args": ["-y", "mcp-remote", "https://mcp.linear.app/sse"],
        "env": {}
      },
      "settings": {}
    }
  }
}
```

Refer to the main [Awesome Remote MCP Servers list](../../README.md) for more servers and client information.

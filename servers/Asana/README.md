# Asana MCP Server

This README provides information about the Asana MCP server.

| Feature        | Details                     |
| -------------- | --------------------------- |
| Name           | Asana                       |
| Category       | Project Management          |
| URL            | `https://mcp.asana.com/sse` |
| Authentication | OAuth2.1                    |
| Maintainer     | [Asana](https://asana.com)  |

## Overview

Asana offers a Model Context Protocol (MCP) server, accessible via app integration, which allows AI assistants and other applications to access the Asana Work Graph from beyond the Asana platform. This server provides a way to interact with your Asana workspace through various AI platforms and tools that support MCP.

With this server, Asana customers can:

1. Access Asana data from compatible AI applications
2. Create and manage tasks and projects through natural language
3. Generate reports and summaries based on Asana data
4. Analyze project data and get AI-powered suggestions

Example requests users could make from outside Asana using the MCP:

1. "Find all my incomplete tasks due this week"
2. "Create a new task in the Marketing project assigned to me"
3. "List all sections in the Product Launch project"
4. "Show me the status of the Q2 Planning project"

## Requirements

1. A compatible MCP client (Claude.ai, Cursor, or any application that has implemented an MCP client)
2. The app named "Asana MCP" is not blocked via Asana [app management](https://help.asana.com/s/article/app-management-and-integrations?language=en_US). If you're not sure if the app is blocked, try to connect your MCP client to the server and go through the authorization flow. You'll either be able to authorize the app like normal or, if the app is currently blocked, be prompted to send a request for your admin to unblock the app for your domain.

## Connecting to Asana's MCP Server

The Asana MCP server is available at: `https://mcp.asana.com/sse`

This server requires authentication with your Asana account. When connecting, each user will be prompted to authorize the application to access your Asana data.

## Available Tools

Asana's MCP server includes 30+ tools for:

1. Project tracking and status updates
2. Task creation and management
3. User information
4. Getting updates on Goals
5. Team organization
6. Quick Asana object searching via typeahead

## Using with any MCP Client

For MCP-compatible clients:

1. Configure your client to connect to `https://mcp.asana.com/sse`
2. Ensure your client supports OAuth authentication
3. Set up the connection according to your client's documentation
4. Authenticate with your Asana account when prompted
5. Select which Asana tools to enable based on your needs

## Using with Claude.ai

**Note: Requires Claude Enterprise or Teams**

**For Claude.ai Admins**

_Only Workspace Owners and Primary Owners can set up MCP server connections in Claude.ai:_

1. Go to Settings in Claude.ai
2. Navigate to the "Integrations" section
3. Click "Add server"
4. Enter "Asana" as the Name
5. Enter `https://mcp.asana.com/sse` as the Server URL
6. Click "Add server"
7. Authenticate with your Asana account via OAuth
8. Select which Asana tools to enable for your workspace
9. Click "Save"

**For Claude.ai Users**

After your admin has set up the integration:

1. Navigate to claude.ai
2. Click on the tools menu (next to the search icon)
3. Select "Asana" from the list of available integrations
4. If this is your first time using the integration, you'll be prompted to authenticate
5. Once authenticated, you can start using Claude with Asana

## Using with Cursor

1. Go to your Cursor editor's settings ("Settings" > "Cursor Settings")
2. "MCP" > "+ Add new global MCP server"
3. Add the following to your `mcp.json`
   ```json
           "asana": {
               "command": "npx",
               "args": ["mcp-remote", "https://mcp.asana.com/sse"]
           }
   ```
4. Save your `mcp.json`file. If this is your first time using the integration, you'll be prompted to authenticate  
   **NOTE: **If you run into `Internal Server Error`you can delete your local `~/.mcp-auth`directory `rm -rf ~/.mcp-auth`.  
   **WARNING:** if you have other applications that might be using this directory `~/.mcp-auth` you will need to re-auth (**EX:** other applications that use `mcp-remote`)
5. Once authenticated, you can start using Cursor with Asana

## Troubleshooting

1. If authentication fails, try logging out of your Asana account and logging back in
2. Ensure your MCP client supports SSE-based servers (not Streamable HTTP)
3. Check that your client can handle OAuth authentication flows
4. Verify you have the necessary permissions in your Asana workspace

## Support

For additional help with Asana's MCP server, contact [Asana Support](https://help.asana.com/s/).

Refer to the main [Awesome Remote MCP Servers list](../../README.md) for more servers and client information.

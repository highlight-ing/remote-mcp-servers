# DeepWiki MCP

How to use the official DeepWiki MCP server.

The DeepWiki MCP server provides programmatic access to DeepWiki’s repository documentation (Devin Wiki) and search capabilities (Ask Devin).

## What is MCP?

The [Model Context Protocol](https://modelcontextprotocol.io/introduction) (MCP) is an open standard that enables AI apps to securely connect to MCP-compatible data sources and tools. You can think of MCP like a USB-C port for AI applications - a standardized way to connect AI apps to different services.

## DeepWiki MCP Server

The DeepWiki MCP server is a free, remote, no-authentication-required service.

**Base Server URL:** [https://mcp.deepwiki.com/](https://mcp.deepwiki.com/)

## Available Tools

The DeepWiki MCP server offers three main tools:

- `read_wiki_structure` - Get a list of documentation topics for a GitHub repository
- `read_wiki_contents` - View documentation about a GitHub repository
- `ask_question` - Ask any question about a GitHub repository and get an AI-powered, context-grounded response
  ​

## Wire Protocols

The DeepWiki MCP server supports two wire protocols:

### **SSE (Server-Sent Events)** - `/sse`

- **URL:** https://mcp.deepwiki.com/sse
- The official MCP specification version
- Supported by Highlight and Claude
- Recommended for most integrations
  ​

### **Streamable HTTP** - `/mcp`

- **URL:** https://mcp.deepwiki.com/mcp
- Newer protocol, works with HighlightAI, Cloudflare and OpenAI
- Also supports the legacy /sse version
- For maximum compatibility, try the SSE endpoint at /sse first.

## Related Resources

- [Connecting remote MCP servers to Claude](https://support.anthropic.com/en/articles/11175166-about-custom-integrations-using-remote-mcp)
- [OpenAI’s docs for using the DeepWiki MCP server](https://platform.openai.com/docs/guides/tools-remote-mcp)
- [DeepWiki](https://docs.devin.ai/work-with-devin/deepwiki)
- [Devin Wiki](https://docs.devin.ai/work-with-devin/devin-wiki)
- [Ask Devin](https://docs.devin.ai/work-with-devin/devin-search)

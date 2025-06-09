# Awesome Remote MCP Servers

A curated list of high-quality remote Model Context Protocol (MCP) servers that works with [Highlight](https://highlightai.com) out of the box. This repository focuses on listing official and well-maintained MCP servers that can be accessed over the internet, helping developers discover reliable and production-ready services for their AI applications.

## What is MCP?

[Model Context Protocol (MCP)](https://modelcontextprotocol.io/) is a protocol that enables AI models to interact with external tools and resources. Remote MCP servers allow clients to securely connect to these services over the internet.

## Quality Criteria

This is not an exhaustive list of all remote MCP servers. We maintain high standards for inclusion:

- Official Support: Servers that are maintained by their underlying companies are preferred
- Production Ready: Must be stable and suitable for production use
- Active Maintenance: Regular updates and bug fixes
- Security: Proper authentication and security measures, with OAuth 2.0 support required
- Reliability: Proven track record of uptime and performance
- Community: Active user community and support channels

## Remote MCP Server List

| Name                     | Category                 | URL                                            | Authentication | Maintainer                                                      |
| ------------------------ | ------------------------ | ---------------------------------------------- | -------------- | --------------------------------------------------------------- |
| Atlasian                 | Software Development     | `https://mcp.atlassian.com/v1/sse`             | OAuth2.1       | [Atlassian](https://atlassian.com)                              |
| Asana                    | Project Management       | `https://mcp.asana.com/sse`                    | OAuth2.1       | [Asana](https://asana.com)                                      |
| Intercom                 | Customer Support         | `https://mcp.intercom.com/sse`                 | OAuth2.1       | [Intercom](https://intercom.com)                                |
| Neon                     | Software Development     | `https://mcp.neon.tech/see`                    | OAuth2.1       | [Neon](https://neon.tech)                                       |
| PayPal                   | Payments                 | `https://mcp.paypal.com/sse`                   | OAuth2.1       | [PayPal](https://paypal.com)                                    |
| Plaid                    | Payments                 | `https://api.dashboard.plaid.com/mcp/sse`      | OAuth2.1       | [Plaid](https://plaid.com)                                      |
| Sentry                   | Software Development     | `https://mcp.sentry.dev/sse`                   | OAuth2.1       | [Sentry](https://sentry.io)                                     |
| Linear                   | Project Management       | `https://mcp.linear.app/sse`                   | OAuth2.1       | [Linear](https://linear.app)                                    |
| OneContext               | RAG-as-a-Service         | `https://rag-mcp-2.whatsmcp.workers.dev/sse`   | OAuth2.1       | [OneContext](https://onecontext.ai)                             |
| Square                   | Payments                 | `https://mcp.squareup.com/sse`                 | OAuth2.1       | [Square](https://square.com)                                    |
| Webflow                  | CMS                      | `https://mcp.webflow.com/sse`                  | OAuth2.1       | [Webflow](https://webflow.com)                                  |
| Wix                      | CMS                      | `https://mcp.wix.com/sse`                      | OAuth2.1       | [Wix](https://wix.com)                                          |
| Cloudflare Docs          | Documentation            | `https://mcp.cloudflare.com/sse`               | Open           | [Cloudflare](https://cloudflare.com)                            |
| Cloudflare Workers       | Software Development     | `https://bindings.mcp.cloudflare.com/sse`      | OAuth2.1       | [Cloudflare](https://cloudflare.com)                            |
| Cloudflare Observability | Observability            | `https://observability.mcp.cloudflare.com/sse` | OAuth2.1       | [Cloudflare](https://cloudflare.com)                            |
| Cloudflare Radar         | Observability            | `https://radar.mcp.cloudflare.com/sse`         | OAuth2.1       | [Cloudflare](https://cloudflare.com)                            |
| Kollektiv                | Documentation            | `https://mcp.thekollektiv.ai/sse`              | Oauth2.1       | [Kollektiv](https://github.com/alexander-zuev/kollektiv-mcp)    |
| LLM Text                 | Data Analysis            | `https://mcp.llmtxt.dev/sse`                   | Open           | [LLM Text](https://llmtxt.dev)                                  |
| GitMCP                   | Software Development     | `https://gitmcp.io/docs`                       | Open           | [GitMCP](https://gitmcp.com)                                    |
| Globalping               | Software Development     | `https://mcp.globalping.dev/sse`               | OAuth2.1       | [Globalping](https://globalping.io/)                            |
| Semgrep                  | Software Development     | `https://mcp.semgrep.ai/sse`                   | Open           | [Semgrep](https://semgrep.dev/)                                 |
| Bitte                    | Blockchain Data Analysis | `https://mcp.bitte.ai/sse`                     | Open           | [Bitte](https://bitte.ai)                                       |
| McPoogle                 | MCP Server Search Engine | `https://mcp.mcpoogle.com/sse`                 | Open           | [McPoogle](https://www.mcpoogle.com)                            |
| DeepWiki                 | Documentation RAG        | `https://mcp.deepwiki.com/mcp`                 | Open           | [Cognition](https://docs.devin.ai/work-with-devin/deepwiki-mcp) |
| Invideo                  | Video Service            | `https://mcp.invideo.io/sse`                   | OAuth2.1       | [Invideo](https://invideo.io/)                                  |

## MCP Clients with OAuth Support

Note from Highlight Team: As the MCP spec is still in development, not all clients may support all features. In particular client support of OAuth is not yet widespread. If your client supports please contribute. **Make sure to keep alphatical order.**

| Name           | Category     | URL                          | Authentication | Maintainer                              |
| -------------- | ------------ | ---------------------------- | -------------- | --------------------------------------- |
| Claude Desktop | Productivity | `https://claude.ai/download` | OAuth2.1       | [Anthropic](https://claude.ai/download) |
| Highlight AI   | Productivity | `https://highlightai.com`    | OAuth2.1       | [HighlightAI](https://highlightai.com)  |

## Other MCP Clients

To use remote MCP servers that requires auth you need to use [mcp-remote](https://github.com/geelen/mcp-remote). Make sure you have [Node.js](https://nodejs.org/en) installed in your computer. For desktop clients the configuration you need to add to your client's config file will be like this;

```
{
  "mcpServers": {
    "<REMOTE_MCP_SERVER_NAME>": {
      "command": "npx",
      "args": [
        "mcp-remote",
        "<REMOTE_MCP_SERVER_URL>"
      ]
    }
  }
}
```

## License

This project is licensed under the MIT License - see the [LICENSE](./LICENSE) file for details.

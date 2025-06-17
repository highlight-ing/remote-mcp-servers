# Highlight Connections

Connections are first-party integrations that let Highlight AI talk to the apps and services you already use.  
Each connection bundles one or more **tools**—structured function calls—that the Highlight MCP can invoke at runtime.  
This makes it trivial to automate multi-step workflows such as filing a Linear ticket and then scheduling a follow-up meeting in Google Calendar, all from a single prompt.

## Why use Connections?

• Automate cross-product workflows without writing glue code  
• Keep data in sync between your favourite apps and Highlight AI  
• Enrich assistant responses with real-time information from external systems

## Available Connections

| Connection      | Capability                    | Primary Tool(s)                                              |
| --------------- | ----------------------------- | ------------------------------------------------------------ |
| Google Calendar | Create & list calendar events | `create_google_calendar_event`, `get_google_calendar_events` |
| Linear          | Create tickets                | `create_linear_ticket`                                       |
| Notion          | Create pages                  | `create_notion_page`                                         |

## Anatomy of a Connection

A connection lives in its own folder inside `connections/` and typically contains:

- `README.md` – human-readable documentation of the connection and its tools.
- `schema.json` (optional) – machine-readable JSON schema describing tool parameters.
- Auth helper or configuration files if OAuth or API keys are required.

## Using a Connection in a Prompt

Below is an example sequence that files a bug in Linear and schedules a debugging session on Google Calendar:

```json
[
  {
    "tool": "create_linear_ticket",
    "arguments": {
      "title": "Bug: Login button unresponsive",
      "description": "Safari v17.0; users cannot login."
    }
  },
  {
    "tool": "create_google_calendar_event",
    "arguments": {
      "summary": "Debug login issue",
      "description": "Pair-debug with frontend team",
      "start": "2025-06-19T09:00:00Z",
      "end": "2025-06-19T09:30:00Z"
    }
  }
]
```

## Contributing a New Connection

1. Create a new folder under `connections/` named after the service.
2. Add a `README.md` that follows the template used by existing connections.
3. Define the tool(s) you want to expose using a JSON schema.
4. Document authentication requirements (OAuth scopes, API keys, etc.).
5. Open a pull request—our team will review and help publish it.

---

These connections are maintained by the Highlight team. If you have any questions, please reach out on [Discord](https://discord.gg/hlai) or via [email](mailto:support@highlightai.com).

For an overview of all remote MCP servers and clients, see the [main README](../README.md) at the root of this repository.

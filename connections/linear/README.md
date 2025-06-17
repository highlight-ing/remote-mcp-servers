# Highlight Linear

| Feature        | Details                                  |
| -------------- | ---------------------------------------- |
| Name           | Highlight Linear                         |
| Category       | Productivity                             |
| URL            | Present in Plugins Page                  |
| Authentication | OAuth2.1                                 |
| Maintainer     | [Highlight AI](https://highlightai.com/) |

Use this connection to quickly create tickets in your Linear workspace without leaving Highlight AI.

## Available Tools

The Linear connection currently exposes **one** tool:

- `create_linear_ticket` – Creates a new ticket in Linear.
  - Parameters:
    - `title` (string, required): The summary line of the ticket.
    - `description` (string, required): A detailed description of the ticket.

## Usage Examples

### Create a bug report

```json
{
  "tool": "create_linear_ticket",
  "arguments": {
    "title": "Bug: Login button unresponsive",
    "description": "Users report the login button does nothing when clicked on Safari v17.0. Reproduce and investigate."
  }
}
```

---

This connection is maintained by the Highlight team. If you have any questions please contact us on [Discord](https://discord.gg/hlai) or via [email](mailto:support@highlightai.com).

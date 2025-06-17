# Highlight Google Calendar

| Feature        | Details                                  |
| -------------- | ---------------------------------------- |
| Name           | Highlight Google Calendar                |
| Category       | Productivity                             |
| URL            | Present in Plugins Page                  |
| Authentication | OAuth2.1                                 |
| Maintainer     | [Highlight AI](https://highlightai.com/) |

Use this connection to create and retrieve events from your Google Calendar directly through Highlight AI.

## Available Tools

The Google Calendar connection exposes **two** tools:

- `create_google_calendar_event` – Creates a new event in Google Calendar.

  - Parameters:
    - `summary` (string, required): The event title.
    - `location` (string, optional): Where the event takes place.
    - `description` (string, optional): Additional details about the event.
    - `start` (string, optional): ISO-8601 start timestamp (defaults to now).
    - `end` (string, optional): ISO-8601 end timestamp.

- `get_google_calendar_events` – Fetches upcoming events from the user's primary calendar.
  - Parameters: _None_

## Usage Examples

### Create a meeting

```json
{
  "tool": "create_google_calendar_event",
  "arguments": {
    "summary": "Team Sync",
    "description": "Weekly status meeting",
    "start": "2025-06-18T15:00:00Z",
    "end": "2025-06-18T15:30:00Z"
  }
}
```

### List upcoming events

```json
{
  "tool": "get_google_calendar_events"
}
```

---

This connection is maintained by the Highlight team. If you have any questions please contact us on [Discord](https://discord.gg/hlai) or via [email](mailto:support@highlightai.com).

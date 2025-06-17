# Highlight Notion

| Feature        | Details                                  |
| -------------- | ---------------------------------------- |
| Name           | Highlight Notion                         |
| Category       | Productivity                             |
| URL            | Present in Plugins Page                  |
| Authentication | OAuth2.1                                 |
| Maintainer     | [Highlight AI](https://highlightai.com/) |

Use this connection to programmatically create pages within your Notion workspace.

## Available Tools

The Notion connection currently exposes **one** tool:

- `create_notion_page` – Creates a new page in Notion with a title, description, and Markdown-formatted content.
  - Parameters:
    - `title` (string, required): The title to place at the top of the page.
    - `description` (string, optional): A short summary that appears in page properties.
    - `content` (string, required): The body of the page, written in Markdown.

## Usage Examples

### Create a simple page

```json
{
  "tool": "create_notion_page",
  "arguments": {
    "title": "Weekly Planning",
    "content": "## Tasks\n- [ ] Write project brief\n- [ ] Prepare slides"
  }
}
```

### Create a page with a description

```json
{
  "tool": "create_notion_page",
  "arguments": {
    "title": "Product Spec",
    "description": "Initial draft spec for May release",
    "content": "# Product Spec\nDetailed requirements..."
  }
}
```

---

This connection is maintained by the Highlight team. If you have any questions please contact us on [Discord](https://discord.gg/hlai) or via [email](mailto:support@highlightai.com).

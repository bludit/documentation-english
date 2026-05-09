# Create a new page
<!-- position: 7 -->

Create a new page.

Requires the API Token and an Authentication Token. See [Authentication](../authentication).

<h2 id="request">HTTP Request</h2>

```bash
POST /api/pages
```

<h2 id="parameters">Parameters</h2>

| Key | Type | Description |
|-----|------|-------------|
| `token` *(required)* | string | API Token. |
| `authentication` *(required)* | string | User Authentication Token. |
| `title` | string | Page title. |
| `content` | string | Page content (Markdown supported). |
| `description` | string | Short description. |
| `tags` | string | Comma-separated tags. |
| `category` | string | Category key. |
| `type` | string | `published`, `draft`, `static`, `sticky`, or `scheduled`. |
| `date` | string | Publish date, `YYYY-MM-DD HH:MM:SS`. |
| `slug` | string | URL slug. Derived from the title if omitted. |
| `parent` | string | Key of the parent page (creates a child page). |
| `position` | integer | Page position. |
| `coverImage` | string | Cover image filename or URL. |
| `template` | string | Theme template name. |
| `noindex` | boolean | Set the `noindex` meta tag. |
| `nofollow` | boolean | Set the `nofollow` meta tag. |
| `noarchive` | boolean | Set the `noarchive` meta tag. |

<h2 id="response">Response</h2>

```bash
HTTP Code: 201
Content-Type: application/json
Body:
{
  "status": "0",
  "message": "Page created.",
  "data": {
    "key": "my-dog",
    "uuid": "8a4f2b3c-1234-5678-9abc-def012345678",
    "title": "My dog",
    "type": "published",
    "slug": "my-dog",
    "content": "<p>...</p>",
    "contentRaw": "...",
    "...": "..."
  }
}
```

The full page object is returned. See [Page object](../introduction#page-object) for the complete field reference. The `data.key` field is always present.

<h2 id="errors">Errors</h2>

| Code | Reason |
|------|--------|
| `400` | Validation failure (e.g. missing required fields). |
| `401` | Missing or invalid authentication token. |

<h2 id="curl-example">CURL command example</h2>

`data.json`:

```json
{
  "token": "<api-token>",
  "authentication": "<auth-token>",
  "title": "My dog",
  "content": "Content of the page here. Supports Markdown."
}
```

```bash
$ curl -X POST \
    -H "Content-Type: application/json" \
    -d @data.json \
    "https://www.example.com/api/pages"
```

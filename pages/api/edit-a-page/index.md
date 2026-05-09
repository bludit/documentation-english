# Edit a page
<!-- position: 8 -->

Edit an existing page. Only fields included in the request body are updated; omitted fields keep their current value.

Requires the API Token and an Authentication Token. See [Authentication](../authentication).

<h2 id="request">HTTP Request</h2>

```bash
PUT /api/pages/{key}
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
| `date` | string | Publish date. |
| `parent` | string | Parent page key. |
| `position` | integer | Page position. |
| `coverImage` | string | Cover image filename or URL. |
| `template` | string | Theme template name. |
| `noindex` | boolean | Set the `noindex` meta tag. |
| `nofollow` | boolean | Set the `nofollow` meta tag. |
| `noarchive` | boolean | Set the `noarchive` meta tag. |

> Editing a page may change its `key` if the title or slug is updated. The new key is returned in `data.key`.

<h2 id="response">Response</h2>

```bash
HTTP Code: 200
Content-Type: application/json
Body:
{
  "status": "0",
  "message": "Page edited.",
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

The full updated page object is returned. See [Page object](../introduction#page-object) for the complete field reference.

<h2 id="errors">Errors</h2>

| Code | Reason |
|------|--------|
| `400` | Edit operation failed (validation, persistence error). |
| `401` | Missing or invalid authentication token. |
| `404` | No page exists with the given key. |

<h2 id="curl-example">CURL command example</h2>

`data.json`:

```json
{
  "token": "<api-token>",
  "authentication": "<auth-token>",
  "title": "My dog",
  "content": "Updated content."
}
```

```bash
$ curl -X PUT \
    -H "Content-Type: application/json" \
    -d @data.json \
    "https://www.example.com/api/pages/my-dog"
```

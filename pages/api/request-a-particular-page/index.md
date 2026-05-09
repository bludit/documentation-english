# Request a particular page
<!-- position: 6 -->

Get a single page by its key.

Requires the API Token. See [Authentication](../authentication).

<h2 id="request">HTTP Request</h2>

```bash
GET /api/pages/{key}
```

The `{key}` may be hierarchical (`parent/child`) for child pages.

<h2 id="parameters">Parameters</h2>

| Key | Type | Description |
|-----|------|-------------|
| `token` *(required)* | string | API Token. |

<h2 id="response">Response</h2>

```bash
HTTP Code: 200
Content-Type: application/json
Body:
{
  "status": "0",
  "message": "Page filtered by key: my-dog",
  "data": {
    "key": "my-dog",
    "uuid": "8a4f2b3c-1234-5678-9abc-def012345678",
    "title": "My dog",
    "description": "...",
    "type": "published",
    "slug": "my-dog",
    "content": "<p>...</p>",
    "contentRaw": "...",
    "date": "2026-02-02 00:09:38",
    "dateRaw": "2026-02-02 00:09:38",
    "dateUTC": "2026-02-02 22:09:38",
    "tags": {},
    "username": "admin",
    "category": "",
    "permalink": "https://www.example.com/my-dog",
    "coverImage": false,
    "coverImageFilename": false
  }
}
```

See [Page object](../introduction#page-object) for the full field reference.

<h2 id="errors">Errors</h2>

| Code | Reason |
|------|--------|
| `404` | No page exists with the given key. |

<h2 id="curl-example">CURL command example</h2>

```bash
$ curl -X GET "https://www.example.com/api/pages/my-dog?token=<api-token>"
```

<h2 id="javascript-example">Javascript example</h2>

```html
<script>
  fetch("https://www.example.com/api/pages/my-dog?token=<api-token>", {
    method: 'GET'
  })
    .then(response => response.json())
    .then(json => console.log(json.data));
</script>
```

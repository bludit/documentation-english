# Request a list of pages
<!-- position: 5 -->

List pages, with optional filters by status (published, draft, static, sticky, scheduled) and pagination.

Requires the API Token. See [Authentication](../authentication).

<h2 id="request">HTTP Request</h2>

```bash
GET /api/pages
```

<h2 id="parameters">Parameters</h2>

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| `token` *(required)* | string | | API Token. |
| `published` | boolean | `true` | Include published pages. |
| `static` | boolean | `false` | Include static pages. |
| `sticky` | boolean | `false` | Include sticky pages. |
| `draft` | boolean | `false` | Include draft pages. |
| `scheduled` | boolean | `false` | Include scheduled pages. |
| `untagged` | boolean | `false` | Filter the returned slice to pages without tags. Note: applied after pagination, so the page slice may contain fewer items than `pageSize`. |
| `numberOfItems` | integer | plugin setting (default `15`) | Page size. Use `-1` to return all matching pages. Non-positive values other than `-1` fall back to the plugin default. |
| `pageNumber` | integer | `1` | Page number for pagination. Values below 1 are clamped to 1. |

A `pageNumber` past the last page returns `200 OK` with an empty `data` array and `meta.hasMore: false`, not an error.

<h2 id="response">Response</h2>

```bash
HTTP Code: 200
Content-Type: application/json
Body:
{
  "status": "0",
  "message": "List of pages",
  "numberOfItems": 15,
  "meta": {
    "total": 42,
    "pageNumber": 1,
    "pageSize": 15,
    "hasMore": true
  },
  "data": [
    {
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
  ]
}
```

`meta.total` reflects the count of pages matching the type filters (`published`, `static`, `sticky`, `draft`, `scheduled`). The `untagged` filter is applied client-side to the page slice and is not reflected in `meta.total`.

See [Page object](../introduction#page-object) for the full field reference.

<h2 id="curl-example">CURL command example</h2>

List published and static pages:

```bash
$ curl -X GET "https://www.example.com/api/pages?token=<api-token>&published=true&static=true"
```

<h2 id="javascript-example">Javascript example</h2>

```html
<script>
  fetch("https://www.example.com/api/pages?token=<api-token>&published=true&static=true", {
    method: 'GET'
  })
    .then(response => response.json())
    .then(json => console.log(json.data));
</script>
```

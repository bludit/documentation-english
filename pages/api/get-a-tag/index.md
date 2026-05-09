# Get a tag
<!-- position: 11 -->

Get a single tag, including the full details of every page that uses it. Heavier than [Get all tags](../get-all-tags). Use that endpoint when you only need the tag list.

Requires the API Token. See [Authentication](../authentication).

<h2 id="request">HTTP Request</h2>

```bash
GET /api/tags/{key}
```

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
  "message": "Information about the tag and pages related.",
  "data": {
    "key": "bludit",
    "name": "Bludit",
    "description": "",
    "template": "",
    "list": ["follow-bludit"],
    "pages": [
      { "key": "follow-bludit", "title": "...", "...": "..." }
    ]
  }
}
```

`list` contains page keys; `pages` contains the same pages expanded into full [page objects](../introduction#page-object).

<h2 id="errors">Errors</h2>

| Code | Reason |
|------|--------|
| `404` | No tag exists with the given key. |

<h2 id="curl-example">CURL command example</h2>

```bash
$ curl -X GET "https://www.example.com/api/tags/bludit?token=<api-token>"
```

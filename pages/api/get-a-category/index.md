# Get a category
<!-- position: 13 -->

Get a single category, including the full details of every page in it.

Requires the API Token. See [Authentication](../authentication).

<h2 id="request">HTTP Request</h2>

```bash
GET /api/categories/{key}
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
  "message": "Information about the category and pages related.",
  "data": {
    "key": "general",
    "name": "General",
    "description": "",
    "template": "",
    "list": ["welcome", "about"],
    "pages": [
      { "key": "welcome", "title": "...", "...": "..." }
    ]
  }
}
```

`list` contains page keys; `pages` contains the same pages expanded into full [page objects](../introduction#page-object).

<h2 id="errors">Errors</h2>

| Code | Reason |
|------|--------|
| `404` | No category exists with the given key. |

<h2 id="curl-example">CURL command example</h2>

```bash
$ curl -X GET "https://www.example.com/api/categories/general?token=<api-token>"
```

# Get all categories
<!-- position: 12 -->

List every category in the site, with the page keys related to each.

Requires the API Token. See [Authentication](../authentication).

<h2 id="request">HTTP Request</h2>

```bash
GET /api/categories
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
  "message": "List of categories.",
  "data": [
    {
      "key": "general",
      "name": "General",
      "description": "",
      "template": "",
      "list": ["welcome", "about"]
    }
  ]
}
```

To fetch full page details for a specific category, use [Get a category](../get-a-category).

<h2 id="curl-example">CURL command example</h2>

```bash
$ curl -X GET "https://www.example.com/api/categories?token=<api-token>"
```

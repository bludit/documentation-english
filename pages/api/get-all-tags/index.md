# Get all tags
<!-- position: 10 -->

List every tag in the site, with the page keys related to each tag.

Requires the API Token. See [Authentication](../authentication).

<h2 id="request">HTTP Request</h2>

```bash
GET /api/tags
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
  "message": "List of tags.",
  "data": [
    {
      "key": "bludit",
      "name": "Bludit",
      "description": "",
      "template": "",
      "list": ["follow-bludit"]
    },
    {
      "key": "cms",
      "name": "CMS",
      "description": "",
      "template": "",
      "list": ["follow-bludit"]
    }
  ]
}
```

To fetch full page details for a specific tag, use [Get a tag](../get-a-tag).

<h2 id="curl-example">CURL command example</h2>

```bash
$ curl -X GET -G "https://www.example.com/api/tags" \
    -d "token=<api-token>"
```

<h2 id="javascript-example">Javascript example</h2>

```html
<script>
  fetch("https://www.example.com/api/tags?token=<api-token>", {
    method: 'GET'
  })
    .then(response => response.json())
    .then(json => console.log(json.data));
</script>
```

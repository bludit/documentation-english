# Delete a page
<!-- position: 9 -->

Permanently delete a page.

Requires the API Token and an Authentication Token. See [Authentication](../authentication).

<h2 id="request">HTTP Request</h2>

```bash
DELETE /api/pages/{key}
```

<h2 id="parameters">Parameters</h2>

| Key | Type | Description |
|-----|------|-------------|
| `token` *(required)* | string | API Token. |
| `authentication` *(required)* | string | User Authentication Token. |

<h2 id="response">Response</h2>

```bash
HTTP Code: 200
Content-Type: application/json
Body:
{
  "status": "0",
  "message": "Page deleted."
}
```

> No `data` field is returned on delete.

<h2 id="errors">Errors</h2>

| Code | Reason |
|------|--------|
| `401` | Missing or invalid authentication token. |
| `404` | No page exists with the given key. |
| `500` | Delete failed after the page was located. |

<h2 id="curl-example">CURL command example</h2>

```bash
$ curl -X DELETE \
    "https://www.example.com/api/pages/my-dog?token=<api-token>&authentication=<auth-token>"
```

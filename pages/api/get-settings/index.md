# Get settings
<!-- position: 16 -->

Read the site settings.

Requires the API Token **and** an Authentication Token. See [Authentication](../authentication).

<h2 id="request">HTTP Request</h2>

```bash
GET /api/settings
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
  "message": "Settings.",
  "data": {
    "title": "Welcome to Bludit",
    "slogan": "",
    "description": "",
    "language": "en",
    "locale": "en, en_US",
    "timezone": "UTC",
    "theme": "alternative",
    "homepage": "",
    "uriPage": "/",
    "uriBlog": "",
    "uriTag": "/tag/",
    "uriCategory": "/category/",
    "...": "..."
  }
}
```

`data` mirrors the full site configuration. The exact set of fields depends on the Bludit version and the active theme.

<h2 id="errors">Errors</h2>

| Code | Reason |
|------|--------|
| `401` | Missing or invalid authentication token. |

<h2 id="curl-example">CURL command example</h2>

```bash
$ curl -X GET "https://www.example.com/api/settings?token=<api-token>&authentication=<auth-token>"
```

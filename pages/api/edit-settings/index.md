# Edit settings
<!-- position: 17 -->

Update one or more site settings. Only fields included in the request body are changed; omitted fields keep their current value.

Requires the API Token and an Authentication Token. See [Authentication](../authentication).

<h2 id="request">HTTP Request</h2>

```bash
PUT /api/settings
```

<h2 id="parameters">Parameters</h2>

| Key | Type | Description |
|-----|------|-------------|
| `token` *(required)* | string | API Token. |
| `authentication` *(required)* | string | User Authentication Token. |
| *(any settings field)* | various | Any field defined in `Site::$dbFields`, e.g. `title`, `slogan`, `description`, `language`, `theme`, `homepage`, `uriBlog`. |

See [Get settings](../get-settings) for the full list of fields the Bludit instance currently supports.

<h2 id="response">Response</h2>

```bash
HTTP Code: 200
Content-Type: application/json
Body:
{
  "status": "0",
  "message": "Settings edited."
}
```

<h2 id="errors">Errors</h2>

| Code | Reason |
|------|--------|
| `400` | Validation failure (e.g. invalid `customFields` JSON). |
| `401` | Missing or invalid authentication token. |

<h2 id="curl-example">CURL command example</h2>

`data.json`:

```json
{
  "token": "<api-token>",
  "authentication": "<auth-token>",
  "title": "My new site title",
  "slogan": "Concise and on-brand"
}
```

```bash
$ curl -X PUT \
    -H "Content-Type: application/json" \
    -d @data.json \
    "https://www.example.com/api/settings"
```

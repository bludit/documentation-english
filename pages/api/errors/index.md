# Error responses
<!-- position: 3 -->

The API uses standard HTTP status codes to signal success or failure. Failed responses still include a legacy `status: "1"` field in the body for backwards compatibility, but the **HTTP status code is the source of truth**.

<h2 id="status-codes">HTTP status code reference</h2>

| Code | Meaning |
|------|---------|
| `200 OK` | Successful read or update. |
| `201 Created` | New page created via `POST /api/pages`. |
| `400 Bad Request` | Missing or invalid input: missing API token, invalid page key, invalid file extension, or a validation failure on create/edit. |
| `401 Unauthorized` | Invalid API token, or a write endpoint reached without a valid `authentication` token. Also returned for unknown endpoints. |
| `404 Not Found` | The requested page, tag, category, or user does not exist. |
| `500 Internal Server Error` | Server-side failure during the operation (e.g. delete failed after the resource was located). |

<h2 id="error-body">Error response body</h2>

Error responses are `application/json`. Inner-handler errors (404 not found, 400 validation, etc.) include both fields below:

| Field | Description |
|-------|-------------|
| `status` | `"1"` on failure. Legacy field, kept for back-compat. |
| `message` | Human-readable description of the failure. |

Example, page not found:

```bash
HTTP Code: 404
Content-Type: application/json
Body:
{
  "status": "1",
  "message": "Page not found."
}
```

<h2 id="early-errors">Early validation errors</h2>

A small number of early validation errors (missing API token, invalid API token, unknown endpoint) return only `{"message": "..."}` without the `status` field. Always rely on the HTTP status code rather than the body shape:

```bash
HTTP Code: 400
Content-Type: application/json
Body:
{
  "message": "Missing API token."
}
```

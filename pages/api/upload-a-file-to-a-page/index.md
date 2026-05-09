# Upload a file to a page
<!-- position: 20 -->

Upload a file to a specific page's uploads directory. The filename is sanitised (special characters and spaces replaced with `-`); only extensions in Bludit's `ALLOWED_FILE_EXTENSIONS` list are accepted.

Requires the API Token and an Authentication Token. See [Authentication](../authentication).

<h2 id="request">HTTP Request</h2>

```bash
POST /api/files/{key}
```

The body must be `multipart/form-data` with a file field named `file`.

<h2 id="parameters">Parameters</h2>

| Key | Type | Description |
|-----|------|-------------|
| `token` *(required)* | string (form field) | API Token. |
| `authentication` *(required)* | string (form field) | User Authentication Token. |
| `file` *(required)* | file | The file to upload. |

<h2 id="response">Response</h2>

```bash
HTTP Code: 200
Content-Type: application/json
Body:
{
  "status": "0",
  "message": "File uploaded.",
  "filename": "report.pdf",
  "absolutePath": "/var/www/.../bl-content/uploads/pages/my-dog/report.pdf",
  "absoluteURL": "https://www.example.com/bl-content/uploads/pages/my-dog/report.pdf"
}
```

<h2 id="errors">Errors</h2>

| Code | Reason |
|------|--------|
| `400` | No file sent, upload error, dotfile filename, or unsupported extension. |
| `400` | Page key contains path-traversal characters (`..` or null byte). |
| `401` | Missing or invalid authentication token. |
| `500` | The file failed to move from the temporary directory to the page's uploads directory. |

<h2 id="curl-example">CURL command example</h2>

```bash
$ curl -X POST \
    -F "token=<api-token>" \
    -F "authentication=<auth-token>" \
    -F "file=@report.pdf" \
    "https://www.example.com/api/files/my-dog"
```

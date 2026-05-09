# Get files for a page
<!-- position: 19 -->

List the files (images, attachments) uploaded to a specific page. The list is sorted by date (most recent first).

Requires the API Token. See [Authentication](../authentication).

<h2 id="request">HTTP Request</h2>

```bash
GET /api/files/{key}
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
  "message": "Files for the page key: my-dog",
  "data": [
    {
      "file": "/var/www/.../photo.jpg",
      "filename": "photo.jpg",
      "mime": "image/jpeg",
      "size": 248512,
      "thumbnail": "/var/www/.../thumbnails/photo.jpg"
    }
  ]
}
```

`thumbnail` is an empty string when no thumbnail exists for the file.

<h2 id="errors">Errors</h2>

| Code | Reason |
|------|--------|
| `400` | The page key contains path-traversal characters (`..` or null byte). |

<h2 id="curl-example">CURL command example</h2>

```bash
$ curl -X GET "https://www.example.com/api/files/my-dog?token=<api-token>"
```

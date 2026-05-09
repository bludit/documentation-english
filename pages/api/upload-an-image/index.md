# Upload an image
<!-- position: 18 -->

Upload an image and generate its thumbnail. The image can be uploaded to a specific page (when `IMAGE_RESTRICT` is enabled) or to the global uploads directory.

Requires the API Token and an Authentication Token. See [Authentication](../authentication).

<h2 id="request">HTTP Request</h2>

```bash
POST /api/images
```

The body must be `multipart/form-data` with a file field named `image`.

<h2 id="parameters">Parameters</h2>

| Key | Type | Description |
|-----|------|-------------|
| `token` *(required)* | string (form field) | API Token. |
| `authentication` *(required)* | string (form field) | User Authentication Token. |
| `uuid` | string (form field) | Page UUID. When set and `IMAGE_RESTRICT` is on, the image is stored under that page's directory. |
| `image` *(required)* | file | The image file. |

<h2 id="response">Response</h2>

```bash
HTTP Code: 200
Content-Type: application/json
Body:
{
  "status": "0",
  "message": "Image uploaded.",
  "image": "https://www.example.com/bl-content/uploads/photo.jpg",
  "thumbnail": "https://www.example.com/bl-content/uploads/thumbnails/photo.jpg"
}
```

<h2 id="errors">Errors</h2>

| Code | Reason |
|------|--------|
| `400` | No image sent, upload error (e.g. exceeds `upload_max_filesize`), invalid UUID, or unsupported image extension. |
| `401` | Missing or invalid authentication token. |

<h2 id="curl-example">CURL command example</h2>

```bash
$ curl -X POST \
    -F "token=<api-token>" \
    -F "authentication=<auth-token>" \
    -F "image=@photo.jpg" \
    "https://www.example.com/api/images"
```

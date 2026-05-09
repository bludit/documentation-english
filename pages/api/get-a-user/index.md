# Get a user
<!-- position: 15 -->

Get a single user's public profile by username. Sensitive fields (email, role, password hash, authentication token) are **not** returned.

Requires the API Token. See [Authentication](../authentication).

<h2 id="request">HTTP Request</h2>

```bash
GET /api/users/{username}
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
  "message": "User profile.",
  "data": {
    "username": "admin",
    "firstName": "",
    "lastName": "",
    "nickname": "",
    "description": "",
    "twitter": "",
    "facebook": "",
    "codepen": "",
    "instagram": "",
    "github": "",
    "gitlab": "",
    "linkedin": "",
    "xing": "",
    "telegram": "",
    "mastodon": "",
    "vk": "",
    "youtube": "",
    "bluesky": "",
    "profilePicture": ""
  }
}
```

<h2 id="errors">Errors</h2>

| Code | Reason |
|------|--------|
| `404` | No user exists with the given username. |

<h2 id="curl-example">CURL command example</h2>

```bash
$ curl -X GET "https://www.example.com/api/users/admin?token=<api-token>"
```

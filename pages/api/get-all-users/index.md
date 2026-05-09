# Get all users
<!-- position: 14 -->

List every user in the site, returning their public profile fields. Sensitive fields (email, role, password hash, authentication token) are **not** returned.

Requires the API Token. See [Authentication](../authentication).

<h2 id="request">HTTP Request</h2>

```bash
GET /api/users
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
  "message": "Users profiles.",
  "data": {
    "admin": {
      "username": "admin",
      "firstName": "",
      "lastName": "",
      "nickname": "",
      "description": "",
      "twitter": "",
      "facebook": "",
      "instagram": "",
      "github": "",
      "gitlab": "",
      "linkedin": "",
      "mastodon": "",
      "bluesky": "",
      "youtube": "",
      "profilePicture": ""
    }
  }
}
```

`data` is an object keyed by username. See [Get a user](../get-a-user) for the full set of profile fields.

<h2 id="curl-example">CURL command example</h2>

```bash
$ curl -X GET "https://www.example.com/api/users?token=<api-token>"
```

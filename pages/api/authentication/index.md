# Authentication
<!-- position: 2 -->

The Bludit API uses two tokens. Read endpoints require only the **API Token**; write endpoints require both the **API Token** and an **Authentication Token**.

<h2 id="api-token">API Token</h2>

A static token shared by the whole installation. Required for **every** request, read or write. Find it in the API plugin settings:

```bash
Admin panel > Plugins > API > API Token
```

The token can be sent in the query string (for `GET` and `DELETE`) or in the request body (for `POST` and `PUT`).

Query string:

```bash
GET /api/pages?token=<api-token>
```

Request body (JSON):

```json
{
  "token": "<api-token>"
}
```

<h2 id="authentication-token">Authentication Token</h2>

A per-user token, tied to an account with the `Administrator` role. Required for write endpoints: create, edit, delete, settings update, image upload, and file upload. Find it in the user profile:

```bash
Admin panel > Manage > Users > {Username} > Security > Authentication Token
```

Sent alongside the API token, under the field name `authentication`:

```json
{
  "token": "<api-token>",
  "authentication": "<auth-token>",
  "title": "My new page"
}
```

A request to a write endpoint without a valid `authentication` token returns `401 Unauthorized`.

<h2 id="rotation">Token rotation</h2>

The **API Token** is regenerated when the API plugin is reinstalled.

The **Authentication Token** is regenerated from the user's security settings. Rotating either token invalidates any clients using the previous value.

# API Introduction
<!-- position: 1 -->

The Bludit API plugin exposes a JSON HTTP interface for reading and writing site content from external systems (custom scripts, Claude Desktop / MCP integrations, mobile apps, automation pipelines, themes that need server-side data).

<h2 id="installation">Installation</h2>

Bludit ships with the API plugin pre-installed. Activate it from the plugins section:

```bash
Admin panel > Plugins > API > Activate
```

<h2 id="url">URL</h2>

```bash
{protocol}://{domain}/api/{endpoint}
```

Example:

```bash
https://www.example.com/api/pages
```

<h2 id="authentication">Authentication</h2>

Every request requires an **API Token**. Write requests additionally require a per-user **Authentication Token**. See [Authentication](../authentication) for full details.

<h2 id="endpoints">Endpoints and Methods</h2>

| Endpoint | Method | Auth | Description |
|----------|--------|------|-------------|
| `/api/pages` | `GET` | API token | List pages |
| `/api/pages/{key}` | `GET` | API token | Get a single page |
| `/api/pages` | `POST` | API + auth | Create a new page |
| `/api/pages/{key}` | `PUT` | API + auth | Edit a page |
| `/api/pages/{key}` | `DELETE` | API + auth | Delete a page |
| `/api/tags` | `GET` | API token | List tags |
| `/api/tags/{key}` | `GET` | API token | Get a tag with its related pages |
| `/api/categories` | `GET` | API token | List categories |
| `/api/categories/{key}` | `GET` | API token | Get a category with its related pages |
| `/api/users` | `GET` | API token | List users (public profile fields only) |
| `/api/users/{username}` | `GET` | API token | Get a user's public profile |
| `/api/settings` | `GET` | API + auth | Read site settings |
| `/api/settings` | `PUT` | API + auth | Update site settings |
| `/api/images` | `POST` | API + auth | Upload an image |
| `/api/files/{key}` | `GET` | API token | List files for a page |
| `/api/files/{key}` | `POST` | API + auth | Upload a file to a page |

<h2 id="http-response">HTTP Response</h2>

Responses are `application/json`. Successful response bodies include:

| Field | Type | Description |
|-------|------|-------------|
| `status` | `string` | `"0"` on success. Legacy field, kept for back-compat. Prefer the HTTP status code. |
| `message` | `string` | Short description of the result. |
| `data` | `array` or `object` | Endpoint-specific payload (a list, a resource, or omitted for delete). |
| `meta` | `object` | Present on list endpoints: `total`, `pageNumber`, `pageSize`, `hasMore`. |

<h2 id="http-status-code">HTTP status codes</h2>

| Code | Meaning |
|------|---------|
| `200 OK` | Successful read or update. |
| `201 Created` | New resource created. |
| `400 Bad Request` | Missing or invalid input. |
| `401 Unauthorized` | Invalid API token, or write requested without authentication. |
| `404 Not Found` | Resource does not exist. |
| `500 Internal Server Error` | Server-side failure. |

See [Error responses](../errors) for the full reference and [Changelog](../changelog) for recent behaviour changes.

<h2 id="content-type">Sending requests</h2>

Both JSON bodies (`Content-Type: application/json`) and form-encoded bodies (`application/x-www-form-urlencoded`) are accepted on `POST` and `PUT`. JSON is recommended. It preserves nested structures and avoids per-form-field URL encoding.

<h2 id="page-object">Page object</h2>

Read endpoints that return a page (`GET /api/pages/{key}`, `GET /api/pages`, `POST /api/pages`, `PUT /api/pages/{key}`) all return the same page object shape:

| Field | Description |
|-------|-------------|
| `key` | The page key (slug, possibly hierarchical like `parent/child`). |
| `uuid` | Stable unique identifier, unchanged across rename. |
| `title` | Page title (HTML-encoded). |
| `description` | Short description. |
| `type` | `"published"`, `"draft"`, `"static"`, `"sticky"`, or `"scheduled"`. |
| `slug` | URL slug (last segment of `key`). |
| `content` | Markdown rendered to HTML. |
| `contentRaw` | Raw markdown source (HTML-encoded by core). |
| `date`, `dateRaw`, `dateUTC` | Page publish date in display, raw, and UTC forms. |
| `tags` | Tags as `{key: name}` map. |
| `username` | The author's username. |
| `category` | Category key. |
| `permalink` | Full URL to the page. |
| `coverImage` | Absolute URL to the cover image, or `false`. |
| `coverImageFilename` | Filename of the cover image, or `false`. |

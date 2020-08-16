# API Introduction
<!-- position: 1 -->

The Bludit API (Application Programming Interface) plugin is designed to provide an easy way to integrate other systems with Bludit. With this plugin, you can retrieve or update data from the database with a simple HTTP request.

<h2 id="installation">Installation</h2>
Bludit comes with the API plugin pre-installed, you only need to activate it from plugins section.

```bash
Admin panel > Plugins > API > Activate
```

<h2 id="url">URL</h2>
The URL of the API is:

```bash
{protocol}://{domain}/api/{endpoint}
````

Example:

```bash
https://www.example.com/api/pages
```

<h2 id="endpoints">Endpoints and Methods</h2>

| endpoint | method | description |
|----------|--------|-------------|
| /pages | `GET` | Returns a list of pages |
| /pages/{page key} | `GET` | Returns a page by the page key |
| /pages | `POST` | Create a new page |
| /pages/{page key} | `PUT` | Edit a page |
| /pages/{page key} | `DELETE` | Delete a page |
| /settings | `GET` | Returns the Bludit settings |
| /settings | `PUT` | Edit Bludit settings |
| /images | `POST` | Upload an image and generate the thumbnail for a page |
| /tags | `GET` | Returns a list of tags and pages keys related to the tag |
| /tags/{tag key} | `GET` | Returns a tag by tag key |
| /categories | `GET` | Returns a list of categories and pages keys related to the category |
| /categories/{category key} | `GET` | Returns a category by category key |
| /users | `GET` | Returns the list of users in the system |
| /users/{username} | `GET` | Returns the profile user |
| /files/{page key} | `GET` | Returns the files related to a page |

<h2 id="http-response">HTTP Response</h2>

The response content format is `Content-Type: application/json`.

Default values for the body.

| key | type | description |
|-----|------|-------------|
| status | string | Returns 0 on success. |
| message | string | Returns a little message about the execution. |
| data | array | The content of the response for the endpoint. |

<h2 id="http-status-code">HTTP status code</h2>

| HTTP code | description |
|-----------|-------------|
| 200 | Response successfull. |
| 400 | Bad request, missing inputs. |
| 401 | The API token or authentication token are missing or are wrong. |
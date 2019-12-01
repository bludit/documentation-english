# API Introduction
<!-- position: 1 -->

The Bludit API (Application Programming Interface) plugin is designed to provide an easy way to integrate other systems with Bludit. With this plugin, you can retrieve or update data from the database with a simple HTTP request.

<h2 id="installation">Installation</h2>
Bludit comes with the API plugin pre-installed, you only need to activate it.

Go to **Admin panel > Plugins > API > Activate**.

<h2 id="url">URL</h2>
The URL of the API is:

```
{protocol}://{domain}/api/{endpoint}
````

Example:

```
https://www.example.com/api/pages
```

<h2 id="endpoints">Endpoints and Methods</h2>

| endpoint | method | description |
|----------|--------|-------------|
| /pages | `GET` | Returns a list of pages |
| /pages/{key} | `GET` | Returns a page, filtered by the page key |
| /pages | `POST` | Create a new page |
| /pages/{key} | `PUT` | Edit a page |
| /pages/{key} | `DELETE` | Delete a page |
| /tags | `GET` | Returns a list of tags and pages keys related to the tag |
| /tags/{key} | `GET` | Returns a tag information, filtered by the tag key |

<h2 id="http-response">HTTP Response</h2>

The response format is `JSON`, here is a list of keys from the JSON object.

| key | type | description |
|-----|------|-------------|
| message | string | Returns a little message about the execution. |
| data | array | The content of the response for the endpoint. |

<h2 id="http-status-code">HTTP status code</h2>

| HTTP code | description |
|-----------|-------------|
| 200 | Response successfull. |
| 400 | Bad request, missing inputs. |
| 401 | The API token or authentication token is missing or is wrong. |
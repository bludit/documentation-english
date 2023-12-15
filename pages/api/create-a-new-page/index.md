# Create a new page
<!-- position: 4 -->

Create a new page.

All requests to the API need the `API Token`. You can find the token in the API plugin settings.

```bash
Admin panel > Plugins > API > API Token
```

For all requests to the API for write content, you'll need to provide the `Authentication Token`. To get this token, you need a user with `Administrator` role. Get the `Authentication Token` from the user profile.

```bash
Admin panel > Manage > Users > {Username} > Security > Authentication Token
```

<h2 id="request">HTTP Request</h2>

```bash
POST /api/pages/{key}
```

<h2 id="parameters">Parameters</h2>

| key | value |
|-----|-------|
| `required` token | `string` API Token. |
| `required` authentication | `string` Authentication token. |
| title | `string` Page title. |
| content | `string` Page content. |
| description | `string` Page description. |
| tags | `string` Page tags, separated by comma. |
| type | `string` Page type. |
| date | `string` Page date (formatted as "YYYY-MM-DD Hours:Minutes:Seconds"). |
| dateModified | `string` Page modified date. |
| slug | `string` Page URL slug. |
| position | `string` Page position. |
| coverImage | `string` Page cover image. |
| category | `string` Page category. |
| template | `string` Page template. |
| noindex | `string` Page noindex. |
| nofollow | `string` Page nofollow. |
| noarchive | `string` Page noarchive. |
| custom | `map` Custom field. |

<h2 id="response">Response</h2>

```bash
HTTP Code: 200
Content-Type: application/json
Body:
{
	"status": "0",
	"message": "Page created.",
	"data": {
		"key": "<page key>"
	}
}
```

<h2 id="curl-example-1">CURL command example 1</h2>
This example shows you how to create a new page via the command line with the `curl` command.

The `data.json` file has the basic data needed to create a new page.

Content of file `data.json`:

```bash
{
	"token": "24a8857ed78a8c89a91c99afd503afa7",
	"authentication": "193569a9d341624e967486efb3d36d75",
	"title": "My dog",
	"content": "Content of the page here, support Markdown code and HTML code."
}
```

Execute the command and attach the `data.json` file:

```bash
$ curl  -X POST \
	-H "Content-Type: application/json" \
	-d @data.json \
	"https://www.example.com/api/pages"
```

Response Body

```bash
{
	"status": "0",
	"message": "Page created.",
	"data": {
		"key": "my-dog"
	}
}
```

<h2 id="curl-example-2">CURL command example 2</h2>
This example shows you how to create a new page via the command line with the `curl` command and include custom fields.

First, you need to create the custom field, follow the [Quick example](https://docs.bludit.com/en/content/custom-fields#quick-example) from the documentation to create the custom field `subtitle`.

Create a file `data.json` with the page's fields.

```bash
{
	"token": "24a8857ed78a8c89a91c99afd503afa7",
	"authentication": "193569a9d341624e967486efb3d36d75",
	"title": "My dog",
	"content": "Content of the page here, support Markdown code and HTML code.",
	"custom": {
		"subtitle": "Mi perro dinamita"
	}
}
```

Execute the command and attach the `data.json` file:

```bash
$ curl  -X POST \
	-H "Content-Type: application/json" \
	-d @data.json \
	"https://www.example.com/api/pages"
```

Response Body

```bash
{
	"status": "0",
	"message": "Page created.",
	"data": {
		"key": "my-dog"
	}
}
```
# Edit a page
<!-- position: 5 -->

Edit a page.

All request to the API need the `API Token`, you can find the token in the settings of the plugin.

All request to the API to write content is necessary to provide the `Authorization Token`. To get this token you need a user with `Administrator` role. Get the `Authorization Token` from the user profile.

<h2 id="request">Request</h2>

- Endpoint: `/api/pages/{key}`
- Method: `PUT`
- Content-Type: `application/json`

Bellow the list of parameters allowed for this endpoint.

| key | value | Default value |
|-----|-------|---------------|
| `required` token | `string` API Token. | |
| `required` authentication | `string` Authentication token. | |
| title | `string` Page title. | |
| content | `string` Page content. | |
| tags | `string` Page tags. | |
| type | `string` Page type. | |
| date | `string` Page date. | |
| dateModified | `string` Page modified date. | |
| position | `string` Page position. | |
| coverImage | `string` Page cover image. | |
| category | `string` Page category. | |
| template | `string` Page template. | |
| noindex | `string` Page noindex. | |
| nofollow | `string` Page nofollow. | |
| noarchive | `string` Page noarchive. | |

<h2 id="response">Response</h2>

- HTTP Code: `200`
- Content-Type: `application/json`
- Content

```
{
	"status": "0",
	"message": "Page edited.",
	"data": {
		"key": "<PAGE_KEY>"
	}
}
```

<h2 id="curl-example">CURL command example</h2>
The follow curl example shows how to edit a page with the key `my-dog`.

Content of file `data.json`

```
{
	"token": "24a8857ed78a8c89a91c99afd503afa7",
	"authentication": "193569a9d341624e967486efb3d36d75",
	"title": "My dog",
	"content": "Content of the page here, support Markdown code and HTML code."
}
```

Execute the command and attaching the file `data.json`

```
$ curl  -X PUT \
	-H "Content-Type: application/json" \
	-d @data.json \
	"https://www.example.com/api/pages/my-dog"
```

Output:

```
{
	"status": "0",
	"message": "Page created.",
	"data": {
		"key": "my-dog"
	}
}
```

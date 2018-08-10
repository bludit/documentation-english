# Title: Edit a page
<!-- Position: 5 -->
---
Bludit API provides the features to edit a page.

All request to the API need the `API Token`, you can find the token in the settings of the plugin.

All request to the API to write content is necessary to provide an `Authorization Token`. To get this kind of token you need a user with **ADMINISTRATOR** role. You can get the `Authorization Token` on **Admin panel > Manage > Users > {Username} > Edit User > Authentication Token > Token**.

<h2 id="request">Request</h2>

- Endpoint: `/api/pages/{key}`
- Method: `PUT`
- Content-Type: `application/json`
- Content

```
{
	"token": "<TOKEN>",
	"authentication": "<AUTHENTICATION_TOKEN>",
	"title": "<PAGE_TITLE>",
	"content": "<PAGE_CONTENT>"
}
```

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

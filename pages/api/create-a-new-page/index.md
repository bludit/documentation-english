# Create a new page
<!-- position: 4 -->

Bludit API provides the features to create a new page.

All request to the API need the `API Token`, you can find the token in the settings of the plugin.

All request to the API to write content is necessary to provide an `Authorization Token`. To get this kind of token you need a user with **ADMINISTRATOR** role. You can get the `Authorization Token` on **Admin panel > Manage > Users > {Username} > Edit User > Authentication Token > Token**.

<h2 id="request">Request</h2>

- Endpoint: `/api/pages`
- Method: `POST`
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
	"message": "Page created.",
	"data": {
		"key": "<PAGE-KEY>"
	}
}
```

<h2 id="curl-example">CURL command example</h2>
Here is an example that shows you how to create a new page via the command line with the command `curl`. The file `data.json` has the basic data needed to create a new page.

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
$ curl  -X POST \
	-H "Content-Type: application/json" \
	-d @data.json \
	"https://www.example.com/api/pages/my-dog"
```

Output:

```
{
	"status": "0",
	"message": "Page edited.",
	"data": {
		"key": "my-dog"
	}
}
```

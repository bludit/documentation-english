# Delete a page
<!-- position: 6 -->

Delete a page.

All requests to the API need the `API Token`; you can find the token in the plugin settings.

For all requests to the API to write content, you'll need to provide the `Authorization Token`. To get this token, you need a user with `Administrator` role. Get the `Authorization Token` from the user profile.

<h2 id="request">Request</h2>

- Endpoint: `/api/pages/<key>`
- Method: `DELETE`
- Content-Type: `application/json`

Below is the list of parameters allowed for this endpoint.

| key | value | Default value |
|-----|-------|---------------|
| `required` token | `string` API Token. | |
| `required` authentication | `string` Authentication token. | |

<h2 id="response">Response</h2>

- HTTP Code: `200`
- Content-Type: `application/json`
- Content

```
{
	"status": "0",
	"message": "Page deleted."
}
```


<h2 id="curl-example">CURL command example</h2>
The following curl example shows how to delete a page with the key `my-dog`.

```
$ curl  -X DELETE \
	--data "token=24a8857ed78a8c89a91c99afd503afa7" \
	--data "authentication=193569a9d341624e967486efb3d36d75" \
	-H "Content-Type: application/json" \
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
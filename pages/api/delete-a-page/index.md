# Delete a page
<!-- position: 6 -->

Delete a page.

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
DELETE /api/pages/{key}
```

<h2 id="parameters">Parameters</h2>

| key | value | Default value |
|-----|-------|---------------|
| `required` token | `string` API Token. | |
| `required` authentication | `string` Authentication token. | |

<h2 id="response">Response</h2>

```bash
HTTP Code: 200
Content-Type: application/json
Body:
{
	"status": "0",
	"message": "Page deleted."
}
```

<h2 id="curl-example">CURL command example</h2>
The following curl example shows how to delete a page with the key `my-dog`.

```bash
$ curl  -X DELETE \
	--data "token=24a8857ed78a8c89a91c99afd503afa7" \
	--data "authentication=193569a9d341624e967486efb3d36d75" \
	-H "Content-Type: application/json" \
	"https://www.example.com/api/pages/my-dog"
```

Response Body

```bash
{
	"status": "0",
	"message": "Page deleted.",
	"data": {
		"key": "my-dog"
	}
}
```
# Request a particular page
<!-- position: 3 -->

Get a particular page by the page key.

All requests to the API need the `API Token`. You can find the token in the API plugin settings.

```bash
Admin panel > Plugins > API > API Token
```

<h2 id="request">HTTP Request</h2>

```bash
GET /api/pages/{page key}
```

<h2 id="parameters">Parameters</h2>

| key | value | Default value |
|-----|-------|---------------|
| `required` token | `string` API Token | |

<h2 id="response">Response</h2>

```bash
HTTP Code: 200
Content-Type: application/json
Body:
{
	"status": "0",
	"message": "Page filtered by key: my-dog",
	"data": {
		"key": "my-dog",
		"title": "My dog",
		"content": "...",
		"contentRaw": "...",
		"description": "...",
		"type": "published",
		"slug": "my-dog",
		"date": "2019-02-02 00:09:38",
		"dateUTC": "2019-02-02 22:09:38",
		"tags": "",
		"permalink": "https://www.example.com/my-dog",
		"coverImage": false,
		"coverImageFilename": false
	}
}
```

<h2 id="curl-example">CURL command example</h2>
You can request a particular page by the page key.

The following example shows how to get the page with the key `my-dog`.

```bash
$ curl -X GET "https://www.example.com/api/pages/my-dog?token=80a09ba055b73f68e3c9e7c9ea12b432"
```

Response Body

```bash
{
	"status": "0",
	"message": "Page filtered by key: my-dog",
	"data": {
		"key": "my-dog",
		"title": "My dog",
		"content": "...",
		"contentRaw": "...",
		"description": "...",
		"type": "published",
		"slug": "my-dog",
		"date": "2019-02-02 00:09:38",
		"dateUTC": "2019-02-02 22:09:38",
		"tags": "",
		"permalink": "https://www.example.com/my-dog",
		"coverImage": false,
		"coverImageFilename": false
	}
}
```

<h2 id="javascript-example">Javascript example</h2>
You can use the [Fetch API](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API) to get the page.

```bash
<script>
	fetch("https://www.example.com/api/pages/my-dog?token=eaf5df0a626145cc6d37b76f3eccc826", {
		method: 'get'
	}).then(function(response) {
		return response.json();
	}).then(function(json) {
		console.log(json.data);
	});
</script>
```

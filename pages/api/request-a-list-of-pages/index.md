# Request a list of pages
<!-- position: 2 -->

Get a list of pages.

All requests to the API need the `API Token`. You can find the token in the API plugin settings.

```bash
Admin panel > Plugins > API > API Token
```

<h2 id="request">HTTP Request</h2>

```bash
GET /api/pages
```

<h2 id="parameters">Parameters</h2>

| key | value | Default value |
|-----|-------|---------------|
| `required` token | `string` API Token | |
| published | `boolean` Returns published pages. | `true` |
| sticky | `boolean` Returns sticky pages. | `false` |
| static | `boolean` Returns static pages. | `false` |
| draft | `boolean` Returns draft pages. | `false` |
| untagged | `boolean` Returns pages without tags. | `false` |

<h2 id="response">Response</h2>

```bash
HTTP Code: 200
Content-Type: application/json
Body:
{
	"status": "0",
	"message": "List of pages, amount of items: 15",
	"data": [
		{
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
		},
		{
			....
		}
	]
}
```

<h2 id="curl-example">CURL command example</h2>
The following request returns a list of published and static pages, limited by the API. You can change the limit in the API settings.

```bash
$ curl -X GET "https://www.example.com/api/pages?token=80a09ba055b73f68e3c9e7c9ea12b432&published=true&static=true"
```

Response Body

```bash
{
        "status": "0",
        "message": "List of pages, number of items: 15",
        "data": [
		{
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
                },
                {
                        ....
                }
        ]
}
```

<h2 id="javascript-example">Javascript example</h2>
You can use the [Fetch API](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API) to get the list of pages.

```
<script>
	fetch("https://www.example.com/api/pages?token=eaf5df0a626145cc6d37b76f3eccc826&published=true&static=true", {
		method: 'get'
	}).then(function(response) {
		return response.json();
	}).then(function(json) {
		console.log(json.data);
	});
</script>
```

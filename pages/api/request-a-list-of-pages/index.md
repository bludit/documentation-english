# Request a list of pages
<!-- position: 2 -->

Get a list of pages.

All request to the API need the `API Token`, you can find the token in the settings of the plugin.

<h2 id="request">Request</h2>

- Endpoint: `/api/pages`
- Method: `GET`

Bellow the list of parameters allowed for this endpoint.

| key | value | Default value |
|-----|-------|---------------|
| `required` token | `string` API Token | |
| published | `boolean` Returns published pages. | `true` |
| sticky | `boolean` Returns static pages. | `false` |
| static | `boolean` Returns static pages. | `false` |
| draft | `boolean` Returns draft pages. | `false` |
| untagged | `boolean` Returns pages without tags. | `false` |

<h2 id="response">Response</h2>

- HTTP Code: `200`
- Content-Type: `application/json`

```
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
The follow request returns a list of published and static pages, limited by the API, you can change the limit in the API settings.

```
$ curl -X GET \
	-G "https://www.example.com/api/pages" \
	-d "token=80a09ba055b73f68e3c9e7c9ea12b432" \
	-d "published=true" \
	-d "static=true"
```

Output:
```
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
	fetch("https://www.example.com/api/pages?token=eaf5df0a626145cc6d37b76f3eccc826", {
		method: 'get'
	}).then(function(response) {
		return response.json();
	}).then(function(json) {
		console.log(json.data);
	});
</script>
```

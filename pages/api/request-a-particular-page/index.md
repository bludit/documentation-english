# Title: Request a particular page
<!-- Position: 3 -->
---
Bludit API provides the feature to request a particular page.

All request to the API need the `API Token`, you can find the token in the settings of the plugin.

<h2 id="request">Request</h2>

- Endpoint: `/api/pages/{key}`
- Method: `GET`
- Parameters: `token`

<h2 id="response">Response</h2>

- HTTP Code: `200`
- Content-Type: `application/json`
- Content

```
{
	"status": "0",
	"message": "Page filtered by key: my-dog",
	"data": {
		"key": "my-dog",
		"title": "My dog",
		"content": "...",
		"contentRaw": "...",
		"description": "...",
		"date": "2018-08-08 00:09:38",
		"dateUTC": "2018-08-07 22:09:38",
		"permalink": "https://www.example.com/my-dog",
		"coverImage": false,
		"coverImageFilename": false
	}
}
```

<h2 id="curl-example">CURL command example</h2>
You can request a particular page by the page key, the follow example show how to get the page with the key `my-dog`.

```
$ curl	-X GET \
	-G "https://www.example.com/api/pages/my-dog" \
	-d "token=80a09ba055b73f68e3c9e7c9ea12b432"
```

Output:
```
{
	"status": "0",
	"message": "Page filtered by key: my-dog",
	"data": {
		"key": "my-dog",
		"title": "My dog",
		"content": "...",
		"contentRaw": "...",
		"description": "...",
		"date": "2018-08-08 00:09:38",
		"dateUTC": "2018-08-07 22:09:38",
		"permalink": "https://www.example.com/my-dog",
		"coverImage": false,
		"coverImageFilename": false
	}
}
```

<h2 id="ajax-example">Javascript: AJAX with jQuery</h2>
Example of AJAX request with the library [jQuery](https://api.jquery.com/jQuery.ajax/).

```
$.ajax({
        url: "https://www.example.com/api/pages/my-dog",
        method: "GET",
        data: "token=80a09ba055b73f68e3c9e7c9ea12b432",
        dataType: 'json',
        success: function(json) {
                console.log(json);
        }
});
```

<div class="note">
<div class="title">Download</div>
Download the source code of the example in <a href="https://github.com/bludit/examples/tree/master/api/ajax-request-a-particular-page">jQuery</a>.
</div>

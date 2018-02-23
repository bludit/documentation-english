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
	"message": "List of pages, amount of items: 15",
	"data": {
		"key": "the-dog",
		"title": "The Dog",
		"content": "Content of the page",
		"description": "Description of the page",
		"date": "2017-08-24 22:00:00",
		"permalink": "http:\/\/example.com\/the-dog"
	}
}
```

<h2 id="curl-example">CURL command example</h2>
Here is an example of a request made via the command line with the command curl.

```
$ curl -vvv \
	-X GET \
	-G "https://example.com/api/pages/the-dog" \
	-d "token=80a09ba055b73f68e3c9e7c9ea12b432"

> GET /api/pages/the-dog?token=80a09ba055b73f68e3c9e7c9ea12b432 HTTP/1.1
> Host: example.com
> User-Agent: curl/7.54.0
> Accept: */*

< HTTP/1.1 200 OK
< Date: Sun, 27 Aug 2017 18:58:25 GMT
< Set-Cookie: Bludit-KEY=3de3df692e83b9cbbf5d31de385110bb; path=/; HttpOnly
< Expires: Thu, 19 Nov 1981 08:52:00 GMT
< Cache-Control: no-store, no-cache, must-revalidate, post-check=0, pre-check=0
< Pragma: no-cache
< Access-Control-Allow-Origin: *
< Content-Length: 50731
< Content-Type: application/json

{
	"status": "0",
	"message": "List of pages, amount of items: 15",
	"data": {
		"key": "the-dog",
		"title": "The Dog",
		"content": "Content of the page",
		"description": "Description of the page",
		"date": "2017-08-24 22:00:00",
		"permalink": "http:\/\/example.com\/the-dog"
	}
}
```

<h2 id="ajax-example">Javascript: AJAX with jQuery</h2>
Example of AJAX request with the library [jQuery](https://api.jquery.com/jQuery.ajax/).

```
$.ajax({
        url: "https://example.com/api/pages/the-dog",
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

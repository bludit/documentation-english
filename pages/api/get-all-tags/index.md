# Get all tags
<!-- position: 7 -->

Get all tags and the pages keys related to each tag.

All requests to the API need the `API Token`; you can find the token in the plugin settings.

<h2 id="request">Request</h2>

- Endpoint: `/api/tags`
- Method: `GET`

Below is the list of parameters allowed for this endpoint.

| key | value | Default value |
|-----|-------|---------------|
| `required` token | `string` API Token | |

<h2 id="response">Response</h2>

- HTTP Code: `200`
- Content-Type: `application/json`

```
{
  "status": "0",
  "message": "List of tags.",
  "data": [
    {
      "name": "Bludit",
      "description": "",
      "template": "",
      "list": [
        "follow-bludit"
      ],
      "key": "bludit"
    },
    {
      "name": "CMS",
      "description": "",
      "template": "",
      "list": [
        "follow-bludit"
      ],
      "key": "cms"
    },
    {
      "name": "Flat files",
      "description": "",
      "template": "",
      "list": [
        "follow-bludit"
      ],
      "key": "flat-files"
    }
  ]
}
```

<h2 id="curl-example">CURL command example</h2>
The following request returns a list of published and static pages, limited by the API. You can change the limit in the API settings.

```
$ curl -X GET \
	-G "https://www.example.com/api/tags" \
	-d "token=80a09ba055b73f68e3c9e7c9ea12b432"
```

Output:
```
{
  "status": "0",
  "message": "List of tags.",
  "data": [
    {
      "name": "Bludit",
      "description": "",
      "template": "",
      "list": [
        "follow-bludit"
      ],
      "key": "bludit"
    },
    {
      "name": "CMS",
      "description": "",
      "template": "",
      "list": [
        "follow-bludit"
      ],
      "key": "cms"
    },
    {
      "name": "Flat files",
      "description": "",
      "template": "",
      "list": [
        "follow-bludit"
      ],
      "key": "flat-files"
    }
  ]
}
```

<h2 id="javascript-example">Javascript example</h2>
You can use the [Fetch API](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API) to get the list of tags.

```
<script>
	fetch("https://www.example.com/api/tags?token=eaf5df0a626145cc6d37b76f3eccc826", {
		method: 'get'
	}).then(function(response) {
		return response.json();
	}).then(function(json) {
		console.log(json.data);
	});
</script>
```

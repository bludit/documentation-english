# Title: Create/Edit/Delete Content
<!-- Position: 3 -->
<!-- Date: 2017-10-18 22:00:00 -->
---
Bludit API provide the features to create, edit or delete content.

By default the API requiere the `API token`, and to write content you need an user with the **ADMINISTRATOR** role and his `Authorization Token`; You can get the `Authorization Token` on **Manage->Users->{Username}->Edit User->Authentication Token->Token**.

### Content
1. [Create a new page](#create-a-new-page)
2. [Edit a page](#edit-a-page)

---

## <a id="create-a-new-page"></a> Create a new page

### Request
- Endpoint: `/api/pages`
- Method: `POST`
- Content-Type: `application/json`
- Content

```
{
	"token": "24a8857ed78a8c89a91c99afd503afa7",
	"authentication": "193569a9d341624e967486efb3d36d75",
	"title": "My dog",
	"content": "Content of the page here, support Markdown code and HTML code."
}
```

### Response
- HTTP Code: `200`
- Content-Type: `application/json`
- Content

```
{
	"status": "0",
	"message": "Page created.",
	"data": {
		"key": "my-dog"
	}
}
```

### cURL command example
Here is an example to how to create a new page via the command line with the command curl. The file `data.json` has the basic data need it to create a new page.

File `data.json`
```
{
	"token": "24a8857ed78a8c89a91c99afd503afa7",
	"authentication": "193569a9d341624e967486efb3d36d75",
	"title": "My dog",
	"content": "Content of the page here, support Markdown code and HTML code."
}
```

```
$ curl -vvv -X POST -H "Content-Type: application/json" -d @data.json "https://example.com/api/pages"

> POST /api/pages HTTP/1.1
> Host: example.com
> User-Agent: curl/7.54.0
> Accept: */*
> Content-Type: application/json

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
	"message": "Page created.",
	"data": {
		"key": "my-dog"
	}
}
```

---

## <a id="edit-a-page"></a> Edit a page

### Request
- Endpoint: `/api/pages/<key>`
- Method: `PUT`
- Content-Type: `application/json`
- Content

```
{
	"token": "24a8857ed78a8c89a91c99afd503afa7",
	"authentication": "193569a9d341624e967486efb3d36d75",
	"title": "My edited dog",
	"content": "Content of the page here, support Markdown code and HTML code."
}
```

### Response
- HTTP Code: `200`
- Content-Type: `application/json`
- Content

```
{
	"status": "0",
	"message": "Page edited.",
	"data": {
		"key": "my-dog"
	}
}
```

---

## <a id="edit-a-page"></a> Delete a page

### Request
- Endpoint: `/api/pages/<key>`
- Method: `DELETE`
- Content-Type: `application/json`
- Content

```
{
	"token": "24a8857ed78a8c89a91c99afd503afa7",
	"authentication": "193569a9d341624e967486efb3d36d75"
}
```

### Response
- HTTP Code: `200`
- Content-Type: `application/json`
- Content

```
{
	"status": "0",
	"message": "Page deleted."
}
```
# Title: Content
<!-- Position: 2 -->
<!-- Date: 2017-08-27 13:00:00 -->
---
This section describe how to read/write content of your site with the API.

Before to read this section is recommendend to read the section [API Introduction](https://docs.bludit.com/en/api/introduction).

### Content
1. [How to read content](#read-content)

---

## <a id="read-content"></a> How to read content
With the Bludit API you can request a particular page or a list of pages via the API.

By default the API requiere the `API token` to interact with them, so you need to send all the time this token for any request.

### Request a list of pages
- Endpoint: `/api/pages`
- Method: `GET`
- Parameters: `token`

cURL command
```
$ curl -vvv -X GET -G "https://example.com/api/pages" -d "token=80a09ba055b73f68e3c9e7c9ea12b432"

> GET /api/pages?token=80a09ba055b73f68e3c9e7c9ea12b432 HTTP/1.1
> Host: example.com
> User-Agent: curl/7.54.0
> Accept: */*

< HTTP/1.1 200 OK
< Date: Sun, 27 Aug 2017 18:58:25 GMT
< Set-Cookie: Bludit-KEY=3de3df692e83b9cbbf5d31de385110bb; path=/; HttpOnly
< Expires: Thu, 19 Nov 1981 08:52:00 GMT
< Cache-Control: no-store, no-cache, must-revalidate, post-check=0, pre-check=0
< Pragma: no-cache
< Content-Length: 50731
< Content-Type: application/json

{Response JSON data}
```
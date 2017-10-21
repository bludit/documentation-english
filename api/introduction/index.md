# Title: API Introduction
<!-- Position: 1 -->
<!-- Date: 2017-07-10 22:00:00 -->
<!-- DateModified: 2017-07-15 22:00:00 -->
---
The Bludi API (Application Programming Interface) is a plugin to provide an easy integration with Bludit. With this plugin, you can retrieve or update data from the database with just an HTTP request.

### Content
1. [Installation](#installation)
2. [URL](#url)
3. [Endpoints and Methods](#endpoints)
4. [Methods Inputs](#inputs)
4. [HTTP Response](#http-response)

---

## <a id="installation"></a> Installation
Bludit comes with the plugin API pre-installed, you only need to enable it. Go to **Admin panel->Plugins->API->Activate**.

## <a id="url"></a> URL
The URL of the API is:
```
{protocol}://{domain}/api/{endpoint}
````

Example:
```
https://example.com/api/pages
```

## <a id="endpoints"></a> Endpoints and Methods

Endpoint		| Method 	| Description
------------------------|---------------|-----------------------------------------------|
/pages 			| GET 		| Returns an array with a list of pages		|
/pages/<key>		| GET		| Returns a page, filtered by the page key	|
/pages			| POST		| Create a new page				|

## <a id="inputs"></a> Methods Inputs

Key		| Type 		| Description
----------------|---------------|-----------------------------------------------|
token 		| string 	| API token					|
limit		| integer	| A number for limit the pages  		|
authentication	| string	| Authentication user token			|

## <a id="http-response"></a> HTTP Response
The response format is `JSON`, here is a list of keys from the JSON object.

| Key 		| Type 		| Description 					|
----------------|---------------|-----------------------------------------------|
| message	| string	| Returns a little message about the execution	|
| data 		| array		| The content of the response for the endpoint	|

You can check the HTTP Code for differents response.
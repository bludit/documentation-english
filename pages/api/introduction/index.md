# API Introduction
<!-- Position: 1 -->
---
The Bludit API (Application Programming Interface) is a plugin to provide an easy integration with Bludit. With this plugin, you can retrieve or update data from the database with just an HTTP request.

<h2 id="installation">Installation</h2>
Bludit comes with the plugin API pre-installed, you only need to activate it.

Go to **Admin panel > Plugins > API > Activate**.

<h2 id="url">URL</h2>
The URL of the API is:

```
{protocol}://{domain}/api/{endpoint}
````

Example:

```
https://www.example.com/api/pages
```

<h2 id="endpoints">Endpoints and Methods</h2>

Endpoint		  | Method 	| Description
--------------|---------|-----------------------------------------------|
/pages 			  | GET 		| Returns an array with a list of pages		|
/pages/{key}	| GET		  | Returns a page, filtered by the page key	|
/pages			  | POST		| Create a new page				|
/pages/{key}  | PUT		  | Edit a page				|
/pages/{key}  | DELETE	| Delete a page				|

<h2 id="inputs">Methods Inputs</h2>

Key             | Type 		| Description
----------------|---------|-----------------------------------------------|
token 		      | string 	| API token					|
authentication	| string	| Authentication user token			|
limit		        | integer	| A number for limit the pages returned  		|

<h2 id="http-response">HTTP Response</h2>

The response format is `JSON`, here is a list of keys from the JSON object.

| Key 		| Type 		| Description 					|
----------|---------|-----------------------------------------------|
| message	| string	| Returns a little message about the execution	|
| data 		| array		| The content of the response for the endpoint	|

You can check the HTTP Code for different responses.

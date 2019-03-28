# درخواست یک صفحه خاص
<!-- position: 3 -->

دریافت یک صفحه خاص توسط کلید صفحه

تمام درخواست ها به API به `API Token` نیاز دارند، شما این توکن را می توانید در تنظیمات پلاگین بیابید.


<h2 id="request">درخواست</h2>

- اندپوینت: `/api/pages/{key}`
- متد: `GET`

در زیر لیستی از پارامترهای مجاز برای این اندپوینت وجود دارد

| کلید | مقدار | مقدار پیش فرض |
|-----|-------|---------------|
| `required` token | `string` API token | |

<h2 id="response">پاسخ</h2>

- کد HTTP: `200`
- نوع محتوا: `application/json`
- محتوا

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

<h2 id="curl-example">دستور نمونه CURL</h2>
شما می توانید یک صفحه خاص را توسط کلید صفحه درخواست کنید، مثال پایین چگونگی دریافت صفحه توسط کلید `my-dog` را نشان می دهد.


```
$ curl	-X GET \
	-G "https://www.example.com/api/pages/my-dog" \
	-d "token=80a09ba055b73f68e3c9e7c9ea12b432"
```

خروجی:
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

<h2 id="javascript-example">نمونه Javascript</h2>
شما می توانید از [Fetch API](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API) برای دریافت لیستی از نوشته ها استفاده کنید.

```
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

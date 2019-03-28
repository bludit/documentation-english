# درخواست لیستی از صفحات
<!-- position: 2 -->

دریافت لیستی از صفحات

تمام درخواست ها به API به `API Token` نیاز دارند، شما این توکن را می توانید در تنظیمات پلاگین بیابید.

<h2 id="request">درخواست</h2>

- Endpoint: `/api/pages`
- Method: `GET`

در زیر لیستی از پارامترهای مجاز برای این اندپوینت وجود دارد

| کلید | مقدار | مقدار پیش فرض |
|-----|-------|---------------|
| `required` token | `string` توکن API | |
| published | `boolean` نوشته های منتشر شده را برمیگرداند. | `true` |
| sticky | `boolean` نوشته های چسبنده را برمیگرداند. | `false` |
| static | `boolean` نوشته های استاتیک را برمیگرداند. | `false` |
| draft | `boolean` نوشته های پیش نویس را برمیگرداند. | `false` |
| untagged | `boolean` نوشته های بدون برچسب را برمیگرداند. | `false` |

<h2 id="response">پاسخ</h2>

- کد HTTP : `200`
- نوع محتوا: `application/json`

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

<h2 id="curl-example">دستور نمونه CURL</h2>
درخواست زیر لیستی از منتشر شده ها و نوشته استاتیک را برمیگرداند، توسط API محدود شده است، شما می توانید این محدودیت را در تنظیمات API تغییر دهید.

```
$ curl -X GET \
	-G "https://www.example.com/api/pages" \
	-d "token=80a09ba055b73f68e3c9e7c9ea12b432" \
	-d "published=true" \
	-d "static=true"
```

خروجی:
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

<h2 id="javascript-example">نمونه Javascript</h2>
شما می توانید از [Fetch API](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API) برای دریافت لیستی از نوشته ها استفاده کنید.

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

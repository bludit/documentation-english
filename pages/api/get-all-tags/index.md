# دریافت تمام برچسب ها
<!-- position: 7 -->

دریافت تمام برچسب های صفحه و کلید های مربوط به هریک از برچسب

تمام درخواست ها به API به `API Token` نیاز دارند، شما این توکن را می توانید در تنظیمات پلاگین بیابید.


<h2 id="request">درخواست</h2>

- اندپوینت: `/api/tags`
- متد: `GET`

در زیر لیستی از پارامترهای مجاز برای این اندپوینت وجود دارد

| کلید | مقدار | مقدار پیش فرض |
|-----|-------|---------------|
| `required` token | `string` API Token | |

<h2 id="response">Response</h2>

- کد HTTP: `200`
- نوع محتوا: `application/json`

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

<h2 id="curl-example">دستور نمونه CURL</h2>
درخواست زیر لیستی از منتشر شده ها و نوشته استاتیک را برمیگرداند، توسط API محدود شده است، شما می توانید این محدودیت را در تنظیمات API تغییر دهید.

```
$ curl -X GET \
	-G "https://www.example.com/api/tags" \
	-d "token=80a09ba055b73f68e3c9e7c9ea12b432"
```

خروجی:
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

<h2 id="javascript-example">نمونه Javascript</h2>
شما می توانید از [Fetch API](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API) برای دریافت لیستی از نوشته ها استفاده کنید.

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

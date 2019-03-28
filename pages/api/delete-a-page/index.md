# حذف یک نوشته
<!-- position: 6 -->

حذف یک صفحه

تمام درخواست ها به API به `API Token` نیاز دارند، شما این توکن را می توانید در تنظیمات پلاگین بیابید.

همه درخواست ها به API برای نوشتن محتوا لازم است که `Authorization Token` ارائه شود. برای دریافت این توکن شما به کاربری با نقش `Administrator` احتیاج دارید. `Authorization Token` را از پروفایل کاربری دریافت کنید.


<h2 id="request">درخواست</h2>

- اندپوینت: `/api/pages/<key>`
- متد: `DELETE`
- Content-Type: `application/json`

در زیر لیستی از پارامترهای مجاز برای این اندپوینت وجود دارد

| کلید | مقدار | مقدار پیش فرض |
|-----|-------|---------------|
| `required` token | `string` API Token. | |
| `required` authentication | `string` Authentication token. | |

<h2 id="response">پاسخ</h2>

- کد HTTP: `200`
- نوع محتوا: `application/json`
- محتوا

```
{
	"status": "0",
	"message": "Page deleted."
}
```


<h2 id="curl-example">دستور نمونه CURL</h2>
در اینجا نمونه ای است که نشان می دهد چگونه یک صفحه را توسط کلید `my-dog` حذف کنیم.

```
$ curl  -X DELETE \
	--data "token=24a8857ed78a8c89a91c99afd503afa7" \
	--data "authentication=193569a9d341624e967486efb3d36d75" \
	-H "Content-Type: application/json" \
	"https://www.example.com/api/pages/my-dog"
```

خروجی:

```
{
	"status": "0",
	"message": "Page created.",
	"data": {
		"key": "my-dog"
	}
}
```

# ویرایش یک نوشته
<!-- position: 5 -->

ویرایش یک صفحه

تمام درخواست ها به API به `API Token` نیاز دارند، شما این توکن را می توانید در تنظیمات پلاگین بیابید.

همه درخواست ها به API برای نوشتن محتوا لازم است که `Authorization Token` ارائه شود. برای دریافت این توکن شما به کاربری با نقش `Administrator` احتیاج دارید. `Authorization Token` را از پروفایل کاربری دریافت کنید.


<h2 id="request">درخواست</h2>

- اندپوینت: `/api/pages/{key}`
- متد: `PUT`
- نوع محتوا: `application/json`

در زیر لیستی از پارامترهای مجاز برای این اندپوینت وجود دارد

| کلید | مقدار | مقدار پیش فرض |
|-----|-------|---------------|
| `required` token | `string` API Token. | |
| `required` authentication | `string` Authentication token. | |
| title | `string` Page title. | |
| content | `string` Page content. | |
| tags | `string` Page tags. | |
| type | `string` Page type. | |
| date | `string` Page date. | |
| dateModified | `string` Page modified date. | |
| position | `string` Page position. | |
| coverImage | `string` Page cover image. | |
| category | `string` Page category. | |
| template | `string` Page template. | |
| noindex | `string` Page noindex. | |
| nofollow | `string` Page nofollow. | |
| noarchive | `string` Page noarchive. | |

<h2 id="response">پاسخ</h2>

- کد HTTP: `200`
- نوع محتوا: `application/json`
- محتوا

```
{
	"status": "0",
	"message": "Page edited.",
	"data": {
		"key": "<PAGE_KEY>"
	}
}
```

<h2 id="curl-example">دستور نمونه CURL</h2>
در اینجا نمونه ای است که نشان می دهد چگونه یک صفحه را توسط کلید `my-dog` ویرایش کنیم.

محتوای فایل `data.json`

```
{
	"token": "24a8857ed78a8c89a91c99afd503afa7",
	"authentication": "193569a9d341624e967486efb3d36d75",
	"title": "My dog",
	"content": "Content of the page here, support Markdown code and HTML code."
}
```

اجرای دستور و پیوستن کردن فایل `data.json`

```
$ curl  -X PUT \
	-H "Content-Type: application/json" \
	-d @data.json \
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

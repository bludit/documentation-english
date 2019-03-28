# اصول اولیه قالب
<!-- position: 1 -->

قالب‌ها در بلودیت بسیار انعطاف پذیر هستند، شما می‌توانید از هر فریم ورکی ([Bootstrap](http://getbootstrap.com/), [Foundation](https://foundation.zurb.com/), [Bulma](https://bulma.io), [UIkit](https://getuikit.com/), [Semantic UI](https://semantic-ui.com) و غیره) ، هر کد جاوا اسکریپتی ، هر آنچه که می‌خواهید استفاده کنید.

همه قالب ها در فولدر `bl-themes` مستقر می شوند، و آنها یک ساختار از پیش تعریف شده ای دارند.


<h2 id="structure">ساختار فایل ها و فولدر</h2>
این ساختار اجباری فولدر و فایل ها برای قالب است.

```
/bl-themes/{THEME_NAME}/
	languages/en.json
	metadata.json
	index.php
```

<h2 id="name-description">نام و توضیحات</h2>
نام و توضیحات قالب در فایل JSON به نام `languages/en.json` قرار دارد.

```
{
	"theme-data":
	{
		"name": "Hello World",
		"description": "My new theme"
	}
}
```

<h2 id="information">اطلاعات</h2>
اطلاعات قالب در فایل JSON به نام `metadata.json` قرار دارد.

```
{
	"author": "Bludit",
	"email": "",
	"website": "https://themes.bludit.com",
	"version": "1.0",
	"releaseDate": "2018-08-01",
	"license": "MIT",
	"compatible": "3.0",
	"notes": ""
}
```

<h2 id="examples">مثال</h2>
ما در اینجا دو مثال داریم، یکی از مثال ها بسیار ساده است و دیگری کمی پیچیده به همراه فایل های CSS و Javascript است.

- [اولین قالب من](https://docs.bludit.com/fa/themes/example-my-first-theme)
- [دومین قالب من](https://docs.bludit.com/fa/themes/example-my-second-theme)

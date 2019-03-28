# ترجمه یک قالب
<!-- position: 2 -->

هر قالب یک فولدر `languages` دارند، از داخل این فولدر می توانید برای زبان های مختلف فایل های دلخواه ایجاد کنید. 


```
/bl-themes/{THEME_NAME}/languages/
	de_DE.json
	en.json
	es.json
	fr_FR.json
	...
```

<div class="note">
<div class="title">انکودینگ فایل</div>
تمام فایل های زبان به فرمت <b>JSON</b> هستند و انکودینگ آنها <b>UTF-8</b> می باشد.
</div>

در اینجا مثالی از زبان انگلیسی `en.json` است. هر خط در فایل `en.json` یک جفت مقدار-کلیدی است که کلید در سمت چپ و مقدار در سمت راست قرار می گیرد.

```
{
	"theme-data":
	{
		"name": "Pure",
		"description": "Simple and clean, based on the framework Pure.css."
	}
}
```

همانطور که می بینید، شما کادری به نام `theme-data` دارید، که شامل نام و توضیحات قالب.

در اینجا مثالی از زبان اسپانیایی داریم، فایل در مسیر  `/bl-plugins/{THEME_NAME}/languages/es.json` قرار دارد.


```
{
	"theme-data":
	{
		"name": "Pure",
		"description": "Simple y minimalista, basado en el framework Pure.css."
	}
}
```

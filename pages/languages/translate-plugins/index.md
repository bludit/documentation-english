# ترجمه یک پلاگین
<!-- position: 1 -->

هر پلاگین یک فولدر `languages` دارند، از داخل این فولدر می توانید برای زبان های مختلف فایل های دلخواه ایجاد کنید.


```
/bl-plugins/{PLUGIN_NAME}/languages/
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
	"plugin-data":
	{
		"name": "Page list",
		"description": "Shows the list of pages in order."
	},

	"home": "Home",
	"show-home-link": "Show home link"
}
```
همانطور که می بینید، شما کادری به نام `plugin-data` دارید، که شامل نام و توضیحات پلاگین است، و در کادرهای روبرو جمله ای است برای پلاگین به نام `home` و `show-home-link`.

در اینجا مثالی از زبان اسپانیایی داریم، فایل در مسیر  `/bl-plugins/{PLUGIN_NAME}/languages/es.json` قرار دارد.

```
{
	"plugin-data":
	{
		"name": "Listado de paginas",
		"description": "Muestra el listado de paginas en orden."
	},

	"home": "Inicio",
	"show-home-link": "Mostrar link de la pagina de incio"
}
```

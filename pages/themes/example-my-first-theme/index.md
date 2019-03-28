# مثال: اولین قالب من
<!-- position: 101 -->

بیایید یک قالب جدید و ساده ای را بسازیم، من قالب جدید خودم را `Coffee` می نامم.


- فولدر قالب را درون فولدر `/bl-themes/` بسازید،  ، حال شما  `/bl-themes/coffee/` را دارید
- فایل `en.json` را درون فولدر  `/bl-themes/coffee/languages/` بسازید.
- فایل `metadata.json` را درون فولدر  `/bl-themes/coffee/` بسازید.
- فایل `index.php` را درون فولدر  `/bl-themes/coffee/` بسازید.

شما ساختار فایل ها و فولدر به شکل زیر دارید.

```
/bl-themes/coffee/
	language/en.json
	metadata.json
	index.php
```
قدم بعدی ایجاد محتوای فایل ها است. بیایید از فایل `index.php` شروع کرده و کد های HTML و PHP زیر را اضافه می کنیم.


```
<!DOCTYPE html>
<html>
<head>
	<meta charset="UTF-8">
	<title>Bludit</title>
</head>
<body>
	<?php foreach ($content as $page): ?>

		<h1><?php echo $page->title(); ?></h1>
		<div><?php echo $page->content(); ?></div>
		<hr>

	<?php endforeach; ?>
</body>
</html>
```

فایل `languages/en.json` را ویرایش کرده و نام قالب و توضیحات آن را اضافه می کنیم. 


```
{
	"theme-data":
	{
		"name": "Coffee",
		"description": "This is my first theme for Bludit."
	}
}
```
حال فایل `metadata.json` را برای تکمیل اطلاعات درباره قالب را ویرایش می کنیم.


```
{
	"author": "Bludit",
	"email": "",
	"website": "",
	"version": "1.0",
	"releaseDate": "2019-01-01",
	"license": "MIT",
	"compatible": "3.0",
	"notes": ""
}
```

تبریک میگم، شما اولین قالب خود را برای بلودیت ساختید! حال می توانید به تنظیمات رفته و آن را فعال کنید.

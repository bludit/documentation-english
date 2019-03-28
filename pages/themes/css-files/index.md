# فایل های CSS
<!-- position: 3 -->

بلودیت helpers را عرضه کرده تا به توسعه دهندگان کمک کرده آن‌ها کدهای کمتری بنویسند.

برای این آموزش از نامهای زیر استفاده خواهیم کرد.


- نام قالب `box`
- آدرس وب سایت `https://www.example.com`
- مسیر قالب `/bl-themes/box/`
- مسیر فایل CSS قالب `/bl-themes/box/style.css`


بیایید فایل CSS به نام `style.css` اضافه کنیم، فایل در مسیر `/bl-themes/box/style.css` قرار دارد، اگر شما helper به نام `Theme::` داشته باشید نیازی به اهمیت دادن به مسیر مطلق ندارید.
```
<?php
	echo Theme::css('style.css');
?>
```

خروجی HTML
```
<link rel="stylesheet" type="text/css" href="https://www.example.com/bl-themes/box/style.css">
```

<h2 id="example">مثال</h2>

کد HTML و PHP بعدی یک مثال کامل از چگونگی گذاشتن دو فایل CSS درون یک قالب است.

```
<!DOCTYPE html>
<html>
	<head>
		<title>Hello</title>

		<?php
			echo Theme::css('style.css');
			echo Theme::css('buttons.css');
		?>
	</head>
<body>

<h1>This is a Heading</h1>
<p>This is a paragraph.</p>

</body>
</html>
```

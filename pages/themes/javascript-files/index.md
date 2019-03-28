# فایل های Javascript
<!-- position: 4 -->

بلودیت helpers را عرضه کرده تا به توسعه دهندگان کمک کرده آن‌ها کدهای کمتری بنویسند.

برای این آموزش از نامهای زیر استفاده خواهیم کرد.


- نام قالب `box`
-  آدرس وب سایت `https://www.example.com`
- مسیر قالب `/bl-themes/box/`
-  مسیر فایل Javascript قالب `/bl-themes/box/main.js`


بیایید فایل Javascript به نام `main.js` اضافه کنیم، فایل در مسیر `/bl-themes/box/main.js` قرار دارد، اگر شما helper به نام `Theme::` داشته باشید نیازی به اهمیت دادن به مسیر مطلق ندارید.
```
<?php
	echo Theme::js('main.js');
?>
```

خروجی HTML
```
<script src="https://www.example.com/bl-themes/box/main.js"></script>
```

<h2 id="example">مثال</h2>

کد HTML و PHP بعدی یک مثال کامل از چگونگی گذاشتن دو فایل Javascript درون یک قالب است.

```
<!DOCTYPE html>
<html>
	<head>
		<title>Hello</title>
	</head>
<body>

<h1>This is a Heading</h1>
<p>This is a paragraph.</p>

<?php
	echo Theme::js('main.js');
	echo Theme::js('buttons.js');
?>

</body>
</html>
```

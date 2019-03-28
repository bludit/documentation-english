# قرار دادن پلاگین ها
<!-- position: 6 -->

بلودیت از پلاگین ها پشتیبانی می کند و هر پلاگین دارای هوک می باشد، هوک ها توابع هستند و این توابع در مکان های مختلف قالب اجرا می شوند.

لیستی از هوک ها را می توانید اینجا ببینید:
- https://docs.bludit.com/en/plugins/hooks-list

برای مثال، برای اجرای همه پلاگین های فعال شده توسط هوک `siteHead` می توانید از helper `Theme::plugins()` استفاده کنید. 

```
<?php
	Theme::plugins('siteHead');
?>
```

<h2 id="example">مثال</h2>
کد HTML و PHP بعدی یک مثال کامل از چگونگی گذاشتن 3 نوع مختلف از هوک و اجرای آن ها در مکان صحیح قالب است.

```
<!DOCTYPE html>
<html>
	<head>
		<title>Hello</title>

		<?php
			Theme::plugins('siteHead');
		?>
	</head>
<body>

<?php
	Theme::plugins('siteBodyBegin');
?>

<h1>This is a Heading</h1>
<p>This is a paragraph.</p>

<?php
	Theme::plugins('siteBodyEnd');
?>

</body>
</html>
```

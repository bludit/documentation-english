# مثال: دومین قالب من
<!-- position: 101 -->

این دومین مثالی است در مورد اینکه چطور یک قالب بلودیت را از صفر شامل CSS ، Javascript و پشتیبانی از پلاگین ها بسازیم.


قالب بعدی را `Mars` می نامیم.
اگر شما علاقه ای به این آموزش ندارید می توانید کد منبع <a href="https://github.com/bludit/examples/tree/master/themes/mars">قالب مارس</a> را دانلود کنید. 


<h2 id="folder-structure">ساختار فولدر</h2>

فولدری را درون فولدر `/bl-themes/` بسازید، حال شما `/bl-themes/mars/` را دارید. 
بعد، فولدرهای language ، css و js را بسازید.

- فولدر `language` را درون فولدر `/bl-themes/mars/` بسازید.
- فولدر `css` را درون فولدر `/bl-themes/mars/` بسازید.
- فولدر `js` را درون فولدر `/bl-themes/mars/` بسازید.

```
/bl-themes/mars/
	css/
	js/
	language/
```

<h2 id="name-and-information">نام و اطلاعات</h2>
فایلی را با اطلاعات قالب بسازید. فایل بایستی در شاخه قالب باشد، فایل `metadata.json` با کد JSON زیر:
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

فایل دیگری با نام و اطلاعات قالب بسازید، فایلی به نام `en.json` درون فولدر `/bl-themes/mars/languages/` با کد JSON زیر:

```
{
	"theme-data":
	{
		"name": "Mars",
		"description": "This is my second theme for Bludit."
	}
}
```
<h2 id="index">Index.php</h2>
بیایید بر روی فایل `index.php` کار کنیم، فایلی درون فولدر `/bl-themes/mars/` با کد HTML پایین بسازید:


```
<!DOCTYPE html>
<html>
<head>
	<meta charset="UTF-8">
</head>
<body>

</body>
</html>
```

<h2 id="css-files">فایل های CSS</h2>
فایل های CSS را اضافه کنید:

- با استفاده از Helper object `Theme::css()`
- یا با استفاده از تگ HTML `<link href="..." rel="stylesheet" type="text/css" />`

در این مورد ما استفاده از Helper فایل CSS `/bl-themes/mars/css/style.css` را اضافه می کنیم. با استفاده از Helper شما نیاز ندارید که مسیر مطلق را تعیین کنید.


```
<!DOCTYPE html>
<html>
<head>
	<meta charset="UTF-8">

	<!-- CSS -->
	<?php echo Theme::css('css/style.css') ?>
</head>
<body>

</body>
</html>
```

<h2 id="javascript-files">فایل های Javascript</h2>
فایل های Javascript را اضافه کنید:
- با استفاده از Helper object `Theme::js()`
- یا با استفاده از تگ HTML `<script>...</script>`

در این مورد ما استفاده از Helper فایل Javascript `/bl-themes/mars/js/mars.js` را اضافه می کنیم. با استفاده از Helper شما نیاز ندارید که مسیر مطلق را تعیین کنید.


```
<!DOCTYPE html>
<html>
<head>
	<meta charset="UTF-8">

	<!-- CSS -->
	<?php echo Theme::css('css/style.css') ?>

	<!-- Javascript -->
	<?php echo Theme::js('js/mars.js') ?>
</head>
<body>

</body>
</html>
```

<h2 id="plugin-support">افزودن پشتیبانی پلاگین</h2>
افزودن پشتیبانی برای پلاگین ها، می توانید از helper `Theme::plugins()` استفاده کنید.

هوک های پلاگین برای سایت عبارتند از:

- `siteHead`شامل تمام پلاگین هایی می شود که کد درون `<head>...</head>` را بر میگردانند.
- `siteBodyBegin`شامل تمام پلاگین هایی می شود که کد درون `<body>...</body>` را از شروع بر می گردانند، می تواند بنر خوش آمد گویی، و یا نوار ابزار در بالا باشد.
- `siteBodyEnd`شامل تمام پلاگین هایی می شود که کد درون`<body>...</body>` را در پایین بر می گردانند، مثل کدهای جاوا اسکریپت.

```
<!DOCTYPE html>
<html>
<head>
	<meta charset="UTF-8">

	<!-- CSS -->
	<?php echo Theme::css('css/style.css') ?>

	<!-- Javascript -->
	<?php echo Theme::js('js/mars.js') ?>

	<!-- Load plugins with the hook siteHead -->
	<?php Theme::plugins('siteHead') ?>
</head>
<body>
	<!-- Load plugins with the hook siteBodyBegin -->
	<?php Theme::plugins('siteBodyBegin') ?>

	<!-- Here all the rest of HTML code -->

	<!-- Load plugins with the hook siteBodyBegin -->
	<?php Theme::plugins('siteBodyEnd') ?>
</body>
</html>
```

<h2 id="site-title-and-slogan">عنوان و شعار سایت</h2>
شما می توانید از Site_object برای دریافت عنوان و شعار سایت استفاده کنید.

```
<!DOCTYPE html>
<html>
<head>
	<meta charset="UTF-8">

	<!-- CSS -->
	<?php echo Theme::css('css/style.css') ?>

	<!-- Javascript -->
	<?php echo Theme::js('js/mars.js') ?>

	<!-- Load plugins with the hook siteHead -->
	<?php Theme::plugins('siteHead') ?>
</head>
<body>
	<!-- Load plugins with the hook siteBodyBegin -->
	<?php Theme::plugins('siteBodyBegin') ?>

	<h1><?php echo $site->title() ?></h1>
	<h2><?php echo $site->slogan() ?></h2>

	<!-- Load plugins with the hook siteBodyBegin -->
	<?php Theme::plugins('siteBodyEnd') ?>
</body>
</html>
```

<h2 id="where-am-i">من کجا هستم</h2>
حال بیایید با محتوای سایت کار کنیم.

برای یافتن مکانی که کاربر در آن سایت را مرور می کند می توانید از متغییر `$WHERE_AM_I` استفاده کنید. برای مثال، اگر کاربر در حال بازدید از صفحه ای است که مقدار متغییر آن استرینگ `value`  باشد، و اگر کاربر در حال بازدید از محیط کاربری (صفحه اصلی) باشد، مقدار متغییر `home` می باشد.

```
<!DOCTYPE html>
<html>
<head>
	<meta charset="UTF-8">

	<!-- CSS -->
	<?php echo Theme::css('css/style.css') ?>

	<!-- Javascript -->
	<?php echo Theme::js('js/mars.js') ?>

	<!-- Load plugins with the hook siteHead -->
	<?php Theme::plugins('siteHead') ?>
</head>
<body>
	<!-- Load plugins with the hook siteBodyBegin -->
	<?php Theme::plugins('siteBodyBegin') ?>

	<h1><?php echo $site->title() ?></h1>
	<h2><?php echo $site->slogan() ?></h2>

	<?php if ($WHERE_AM_I=='page'): ?>
		<p>The user is watching a particular page</p>
	<?php elseif ($WHERE_AM_I=='home'): ?>
		<p>The user is watching the homepage</p>
	<?php endif ?>

	<!-- Load plugins with the hook siteBodyBegin -->
	<?php Theme::plugins('siteBodyEnd') ?>
</body>
</html>
```

<h2 id="main-content">محتوای اصلی</h2>
اگر کاربر در صفحه اصلی باشد، بلودیت یک آرایه عمومی به نام `$pages` به همراه تمام نوشته های منتشر شده تولید می کند، هر نوشته یک `Page Object` است.


```
<!DOCTYPE html>
<html>
<head>
	<meta charset="UTF-8">

	<!-- CSS -->
	<?php echo Theme::css('css/style.css') ?>

	<!-- Javascript -->
	<?php echo Theme::js('js/mars.js') ?>

	<!-- Load plugins with the hook siteHead -->
	<?php Theme::plugins('siteHead') ?>
</head>
<body>
	<!-- Load plugins with the hook siteBodyBegin -->
	<?php Theme::plugins('siteBodyBegin') ?>

	<h1><?php echo $site->title() ?></h1>
	<h2><?php echo $site->slogan() ?></h2>

	<?php if ($WHERE_AM_I=='page'): ?>
		<p>The user is watching a particular page</p>
	<?php elseif ($WHERE_AM_I=='home'): ?>
		<?php foreach ($content as $page): ?>
			<h3><?php echo $page->title(); ?></h3>
		<?php endforeach ?>
	<?php endif ?>

	<!-- Load plugins with the hook siteBodyBegin -->
	<?php Theme::plugins('siteBodyEnd') ?>
</body>
</html>
```
اگر کاربر در حال بازدید از یک صفحه خاصی است، بلودیت یک Page-object `$page` عمومی تولید می کند، در این مثال، ما می خواهیم عنوان و محتوا را چاپ کنیم.

```
<!DOCTYPE html>
<html>
<head>
	<meta charset="UTF-8">

	<!-- CSS -->
	<?php echo Theme::css('css/style.css') ?>

	<!-- Javascript -->
	<?php echo Theme::js('js/mars.js') ?>

	<!-- Load plugins with the hook siteHead -->
	<?php Theme::plugins('siteHead') ?>
</head>
<body>
	<!-- Load plugins with the hook siteBodyBegin -->
	<?php Theme::plugins('siteBodyBegin') ?>

	<h1><?php echo $site->title() ?></h1>
	<h2><?php echo $site->slogan() ?></h2>

	<?php if ($WHERE_AM_I=='page'): ?>
		<h3><?php echo $page->title(); ?></h3>
	<?php elseif ($WHERE_AM_I=='home'): ?>
		<?php foreach ($pages as $page): ?>
			<h3><?php echo $page->title(); ?></h3>
		<?php endforeach ?>
	<?php endif ?>

	<!-- Load plugins with the hook siteBodyBegin -->
	<?php Theme::plugins('siteBodyEnd') ?>
</body>
</html>
```

<div class="note">
<div class="title">دانلود</div>
کد سورس <a href="https://github.com/bludit/examples/tree/master/themes/mars">قالب مارس</a> را دانلود کنید.
</div>

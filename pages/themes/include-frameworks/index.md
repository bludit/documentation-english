# قراردادن frameworks
<!-- position: 7 -->

قالب‌ها در بلودیت بسیار انعطاف پذیر هستند، شما می‌توانید از هر فریم ورکی (Bootstrap، Foundation، Bulma، UIkit، Semantic UI ، غیره) ، هر کد Javascript ، هر آنچه که می‌خواهید استفاده کنید.

ما تعداد کمی از فریم ورک ها را در مستندات نوشتیم، ولی شما می توانید با ویرایش این صفحه هر تعدادی که دوست داشتید اضافه کنید.

<h2 id="jquery">قراردادن jQuery</h2>

بلودیت آخرین نسخه از jQuery را درون بسته قرار داده است، شما می توانید آن را توسط helper قرار دهید.
```
<?php
	echo Theme::jquery();
?>
```

خروجی HTML
```
<script src="https://www.example.com/bl-kernel/js/jquery.min.js"></script>
```

<h2 id="bootstrap">قراردادن Bootstrap</h2>

بلودیت آخرین نسخه از Bootstrap را درون بسته قرار داده است، شما می توانید آن را توسط helper قرار دهید.
قراردادن فایل Javascript برای Bootstrap.
```
<?php
	echo Theme::jsBootstrap();
?>
```

خروجی HTML
```
<script src="https://www.example.com/bl-kernel/js/bootstrap.bundle.min.js"></script>
```

قراردادن فایل CSS برای Bootstrap.
```
<?php
	echo Theme::cssBootstrap();
?>
```

خروجی HTML
```
<link rel="stylesheet" type="text/css" href="https://www.example.com/bl-kernel/css/bootstrap.min.css">
```

<h2 id="uikit">قراردادن UIkit</h2>

این فریم ورک در بسته بلودیت قرار ندارد ولی شما به راحتی توسط helpers `Theme::css()` و `Theme::js()` با استفاده از UIKit CDN و یا دانلود فایل های آن درون قالب خود قرار دهید.

مثال پایین UIKit را از CDN درون قالب قرار می دهد، به `false` در انتهای خط دقت کنید، این مورد به تابع می گویید که ما می خواهیم فایلی را از بیرون استفاده کنیم.

```
<?php
	echo Theme::css('https://cdnjs.cloudflare.com/ajax/libs/uikit/3.0.0-rc.26/css/uikit.min.css', false);

	echo Theme::js('https://cdnjs.cloudflare.com/ajax/libs/uikit/3.0.0-rc.26/js/uikit.min.js', false);
	echo Theme::js('https://cdnjs.cloudflare.com/ajax/libs/uikit/3.0.0-rc.26/js/uikit-icons.min.js', false);
?>
```

خروجی HTML
```
<link rel="stylesheet" type="text/css" href="https://cdnjs.cloudflare.com/ajax/libs/uikit/3.0.0-rc.26/css/uikit.min.css">

<script src="https://cdnjs.cloudflare.com/ajax/libs/uikit/3.0.0-rc.26/js/uikit.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/uikit/3.0.0-rc.26/js/uikit-icons.min.js"></script>
```

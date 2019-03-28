# فاوآیکن
<!-- position: 5 -->
بلودیت helpers را عرضه کرده تا به توسعه دهندگان کمک کرده آن‌ها کدهای کمتری بنویسند.
برای این آموزش از نامهای زیر استفاده خواهیم کرد.

- نام قالب `box`
- آدرس وب سایت `https://www.example.com`
- مسیر قالب `/bl-themes/box/`
- مسیر فاوآیکن قالب `/bl-themes/box/favicon.png`

روش بعدی از helper قالب  `Theme::` برچسب head مربوط به فاوآیکن را تولید می‌کند، بصورت پیش‌فرض mime type مقدار  `image/png`  را باز می گرداند.

```
<?php
  echo Theme::favicon('favicon.png');
?>
```

خروجی HTML

```
<link rel="shortcut icon" href="https://www.example.com/bl-themes/box/favicon.png" type="image/png">
```

همچنین اگر می‌خواهید از نوع دیگر فاوآیکن مثل `.ico` استفاده کنید می‌توانید mime type آن را مشخص کنید.
```
<?php
  echo Theme::favicon('favicon.ico', 'image/x-icon');
?>
```
خروجی HTML
```
<link rel="shortcut icon" href="https://www.example.com/bl-themes/box/favicon.ico" type="image/x-icon">
```
<h2 id="example">مثال</h2>
کد HTML و PHP بعدی یک مثال کامل از چگونگی گذاشتن فاوآیکن درون یک قالب است.

```
<!DOCTYPE html>
<html>
  <head>
    <title>Hello</title>

    <?php
      echo Theme::favicon('favicon.png');
    ?>
  </head>
<body>

<h1>This is a Heading</h1>
<p>This is a paragraph.</p>

</body>
</html>
```

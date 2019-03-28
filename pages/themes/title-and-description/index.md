# عنوان و توضیحات
<!-- position: 2 -->
بلودیت helpers را عرضه کرده تا به توسعه دهندگان کمک کرده آن‌ها کدهای کمتر و تمیزتری بنویسند
<h2 id="title">عنوان</h2>

چاپ برچسب `<title>` مربوط به head در محتوای داینامیک. عنوان پیکربندی تعریف شده در تنظیمات وبسایت شما را بر می‌دارد.
```
<?php
  echo Theme::metaTags('title');
?>
```

خروجی HTML
```
<title>Page title | Title site</title>
```
<h2 id="description">توضیحات</h2>
چاپ برچسب `<description>` مربوط به head در محتوای داینامیک. عنوان پیکربندی تعریف شده در تنظیمات وبسایت شما را بر می‌دارد.

```
<?php
  echo Theme::metaTags('description');
?>
```
خروجی HTML
```
<meta name="description" content="Description about your site">
```

<h2 id="examples">مثال</h2>
کد HTML و PHP بعدی یک مثال کامل از چگونگی استفاده از عنوان و توضیحات در یک قالب است.

```
<!DOCTYPE html>
<html>
  <head>
    <?php
      echo Theme::metaTags('title');
      echo Theme::metaTags('description');
    ?>
  </head>
<body>

<h1>This is a Heading</h1>
<p>This is a paragraph.</p>

</body>
</html>
```

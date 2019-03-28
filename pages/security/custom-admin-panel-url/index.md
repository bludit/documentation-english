# آدرس وب پنل مدیریت بلودیت
<!-- position: 3 -->

بلودیت پیش فرض آدرس پنل مدیریت را  بصورت متن `/admin/` عرضه می کند.

شما می توانید این آدرس را با ویرایش فایل `/bl-kernel/boot/variables.php` تغییر دهید. مقدار ثابت `ADMIN_URI_FILTER` را به دلخواه خود تغییر دهید.

<pre><code data-language="php">define('ADMIN_URI_FILTER', 'admin');</code></pre>

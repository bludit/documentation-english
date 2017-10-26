# Title: Custom admin panel URL
<!-- Position: 3 -->
---
Bludit by default provides the admin panel on the context `/admin`.

You can change it editing the file `/bl-kernel/boot/init.php` and change the constant `ADMIN_URI_FILTER` for your own value.

<pre><code data-language="php">define('ADMIN_URI_FILTER', 'admin');</code></pre>
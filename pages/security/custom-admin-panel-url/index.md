# Custom admin panel URL
<!-- Position: 3 -->

Bludit by default provides the admin panel on the context `/admin`.

You can change it by editing the file `/bl-kernel/boot/variables.php`. Change the constant `ADMIN_URI_FILTER` to your own value.

<pre><code data-language="php">define('ADMIN_URI_FILTER', 'admin');</code></pre>

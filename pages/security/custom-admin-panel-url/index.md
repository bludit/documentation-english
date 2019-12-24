# Custom admin panel URL
<!-- position: 3 -->

By default, the Bludit admin panel resides in the `/admin/` folder.

You can change it by editing the `/bl-kernel/boot/variables.php` file. Change the `ADMIN_URI_FILTER` constant to your own chosen value.

<pre><code data-language="php">define('ADMIN_URI_FILTER', 'admin');</code></pre>

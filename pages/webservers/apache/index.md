# Apache
<!-- Position: 1 -->

Bludit try to auto configure the system, if you don't have any issues with the installation you don't need to follow the next steps.

Apache web server use the `.htaccess` file to keep some configurations, like rewrite rules. The `.htaccess` file is a hidden file.

- If you install Bludit in the root directory, you need to uncomment the line `RewriteBase /`.

- If you install Bludit in a sub-directory, for example, `bludit`, you need to uncomment and change the `RewriteBase /` for `RewriteBase /bludit/`.

File: `.htaccess`

```
AddDefaultCharset UTF-8

<IfModule mod_rewrite.c>

# Enable rewrite rules
RewriteEngine on

# Base directory
#RewriteBase /

# Deny direct access to .txt files
RewriteRule ^bl-content/(.*)\.txt$ - [R=404,L]

# All URL process by index.php
RewriteCond %{REQUEST_FILENAME} !-f
RewriteRule ^(.*) index.php [PT,L]

</IfModule>
```




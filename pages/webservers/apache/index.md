# Apache
<!-- position: 1 -->

Bludit will try to auto-configure the system. If you don't have any issues with the installation, you don't need to follow the next steps.

Apache web server uses the `.htaccess` file to keep some configurations, like rewrite rules. The `.htaccess` file is a hidden file.

- If you install Bludit in the root directory, you need to uncomment the line `RewriteBase /`.
- If you install Bludit in a sub-directory, for example, `bludit`, you need to uncomment and change the `RewriteBase /` like `RewriteBase /bludit/`.

`.htaccess` file.

```
AddDefaultCharset UTF-8

<IfModule mod_rewrite.c>

# Enable rewrite rules
RewriteEngine on

# Base directory
#RewriteBase /

# Deny direct access to the next directories
RewriteRule ^bl-content/(databases|workspaces|pages|tmp)/.*$ - [R=404,L]

# All URL process by index.php
RewriteCond %{REQUEST_FILENAME} !-f
RewriteRule ^(.*) index.php [PT,L]

</IfModule>
```




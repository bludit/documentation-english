# Title: Requirements
<!-- Position: 2 -->
---
You just need a web server with PHP support.

- PHP v5.3 or higher.
- PHP [mbstring](http://php.net/manual/en/book.mbstring.php) module for full UTF-8 support.
- PHP [gd](http://php.net/manual/en/book.image.php) module for image processing.
- PHP [dom](http://php.net/manual/en/book.dom.php) module for DOM manipulation.
- PHP [json](http://php.net/manual/en/book.json.php) module for JSON manipulation.
- Supported web servers:
  * PHP Built-in web server
  * Apache with module [mod_rewrite](http://httpd.apache.org/docs/current/mod/mod_rewrite.html)
  * Lighttpd with module [mod_rewrite](http://redmine.lighttpd.net/projects/1/wiki/docs_modrewrite)
  * Ngnix with module [ngx_http_rewrite_module](http://nginx.org/en/docs/http/ngx_http_rewrite_module.html)
  * Other

# Requirements
<!-- position: 2 -->

You just need a web server with PHP support.

- PHP v5.6 or higher.
- PHP [mbstring](https://www.php.net/manual/en/book.mbstring.php) module for full UTF-8 support.
- PHP [gd](https://www.php.net/manual/en/book.image.php) module for image processing.
- PHP [dom](https://www.php.net/manual/en/book.dom.php) module for DOM manipulation.
- PHP [json](https://www.php.net/manual/en/book.json.php) module for JSON manipulation.
- Bludit supports almost every webserver:
  * [PHP Built-in web server](https://www.php.net/manual/en/features.commandline.webserver.php)
  * Nginx with module [ngx_http_rewrite_module](http://nginx.org/en/docs/http/ngx_http_rewrite_module.html)
  * Apache with module [mod_rewrite](http://httpd.apache.org/docs/current/mod/mod_rewrite.html)
  * Lighttpd with module [mod_rewrite](https://redmine.lighttpd.net/projects/1/wiki/docs_modrewrite)
  * Hiawatha, [rewrite rules](https://www.hiawatha-webserver.org/howto/url_rewrite_rules)
  * H2O, see the post [H2O HTTP/2 web server and Bludit](https://forum.bludit.org/viewtopic.php?f=6&t=1015) in the Support Forum
  * IIS with module [URL Rewrite](https://www.iis.net/downloads/microsoft/url-rewrite), see [this](https://forum.bludit.org/viewtopic.php?f=6&t=1420) post in the Support Forum

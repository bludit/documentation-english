# پیش نیازها
<!-- position: 2 -->

شما فقط نیاز به یک سرویس دهنده با پشتیبانی PHP دارید.

- PHP نسخه 5.6 یا بالاتر.
- ماژول PHP [mbstring](http://php.net/manual/en/book.mbstring.php) برای پشتیبانی کامل از UTF-8.
- ماژول PHP [gd](http://php.net/manual/en/book.image.php) برای پردازش تصاویر.
- ماژول PHP [dom](http://php.net/manual/en/book.dom.php) برای بکارگیری DOM.
- ماژول PHP [json](http://php.net/manual/en/book.json.php) برای بکارگیری JSON.
- بلودیت تقریباً از تمام سرویس دهنده های وب پشتیبانی میکند: 
  * [سرویس دهنده توکار PHP](http://php.net/manual/en/features.commandline.webserver.php)
  * Ngix به همراه ماژول [ngx_http_rewrite_module](http://nginx.org/en/docs/http/ngx_http_rewrite_module.html)
  * Apache به همراه ماژول [mod_rewrite](http://httpd.apache.org/docs/current/mod/mod_rewrite.html)
  * Lighttpd به همراه ماژول [mod_rewrite](http://redmine.lighttpd.net/projects/1/wiki/docs_modrewrite)
  * Hiawatha به همراه ماژول [rewrite rules](https://www.hiawatha-webserver.org/howto/url_rewrite_rules)
  * H2O برای اطلاعات بیشتر موضوع [H2O HTTP/2 web server and Bludit](https://forum.bludit.org/viewtopic.php?f=6&t=1015) را در انجمن ببینید.
  * IIS به همراه ماژول [URL Rewrite](https://www.iis.net/downloads/microsoft/url-rewrite), see [this](https://forum.bludit.org/viewtopic.php?f=6&t=1420) موضوع را در انجمن ببینید.

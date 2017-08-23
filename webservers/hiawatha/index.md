# Title: Hiawatha
<!-- Position: 2 -->
<!-- Date: 2017-08-22 22:00:00 -->
---
Bludit suppors Hiawatha webserver, you can use the following rewrite rule:

```
UrlToolkit {
    ToolkitID = bludit
    RequestURI exists Return
    Match [^?]*(\?.*)? Rewrite /index.php$1
}
```

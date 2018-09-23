# Hiawatha
<!-- position: 3 -->

Bludit supports Hiawatha webserver, you can use the following rewrite rule:

```
UrlToolkit {
    ToolkitID = bludit
    RequestURI exists Return
    Match [^?]*(\?.*)? Rewrite /index.php$1
}
```

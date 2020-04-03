# Internet Information Services (IIS)
<!-- position: 4 -->

Bludit is not strictly designed to work on this platform, however, with proper configuration, it is posible to host Bludit on an IIS web server running [PHP](https://docs.microsoft.com/en-us/iis/application-frameworks/scenario-build-a-php-website-on-iis/configuring-step-1-install-iis-and-php) 5.6+ with the WebExt module [URL Rewrite](https://www.iis.net/downloads/microsoft/url-rewrite).

First, we need to translate the Apache `.htaccess` file, that stores required rewrite rules, to a corresponding `web.config` file.

```
<?xml version="1.0" encoding="UTF-8"?>
<configuration>
    <system.webServer>
        <rewrite>
            <rules>
                <rule name="Rule1" stopProcessing="true">
                    <match url="^bl-content/x(.*)\.txt$" ignoreCase="false" />
                    <action type="Redirect" url="{R:0}" redirectType="Temporary" />
                </rule>
                <rule name="Rule2" stopProcessing="true">
                    <match url="^(.*)" ignoreCase="false" />
                    <conditions logicalGrouping="MatchAll">
                        <add input="{REQUEST_FILENAME}" matchType="IsFile" ignoreCase="false" negate="true" />
                    </conditions>
                    <action type="Rewrite" url="index.php" />
                </rule>
            </rules>
        </rewrite>
    </system.webServer>
</configuration>
```

Second, we need to grant the IIS service account (usually `IUSR`) full control the the folder `bl-content`.

Everything else should work out of the box.
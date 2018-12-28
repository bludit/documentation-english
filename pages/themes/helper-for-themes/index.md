# Helper for themes
<!-- position: 100 -->

<h2 id="javascript-files">Javascript files</h2>

This method generates the tag to include the Javascript file `main.js` from the folder `/bludit/themes/{THEME_NAME}/js/`.
```
<?php
	echo Theme::js('js/main.js');
?>
```

HTML output
```
<script src="https://www.example.com/bl-themes/{THEME_NAME}/js/main.js"></script>
```

Or you can include a batch of Javascript files
```
<?php
	echo Theme::js(array('js/file1.js', 'js/file2.js'));
?>
```

HTML output
```
<script src="https://www.example.com/bl-themes/{THEME_NAME}/js/file1.js"></script>
<script src="https://www.example.com/bl-themes/{THEME_NAME}/js/file2.js"></script>
```

<h2 id="favicon">Favicon</h2>

This method generates the head tag for the favicon, the favicon need to be in the root of the theme folder, ex: `/bludit/themes/{THEME_NAME}/favicon.png`.

```
<?php
	echo Theme::favicon('favicon.png');
?>
```

HTML output
```
<link rel="shortcut icon" href="https://www.example.com/bl-themes/{THEME_NAME}/favicon.png" type="image/png">
```

<h2 id="include-jquery">Include jQuery</h2>

Bludit uses [jQuery](http://jquery.com) and provides a method to include it to your theme.

```
<?php
	echo Theme::jquery();
?>
```

HTML output
```
<script charset="utf-8" src="https://www.example.com/bl-kernel/js/jquery.min.js"></script>
```

<h2 id="include-bootstrap">Include Bootstrap</h2>

Bludit uses [Bootstrap](https://getbootstrap.com/) and provides a method to include it to your theme.

Include Javascript file for Bootstrap.
```
<?php
	echo Theme::jsBootstrap();
?>
```

HTML output
```
<script charset="utf-8" src="https://www.example.com/bl-kernel/js/bootstrap.bundle.min.js"></script>
```

Include CSS file for Bootstrap.
```
<?php
	echo Theme::cssBootstrap();
?>
```

HTML output
```
<link rel="stylesheet" type="text/css" href="https://www.example.com/bl-kernel/css/bootstrap.min.css">
```

<h2 id="include-plugins">Include Plugins</h2>

Bludit supports plugins and each plugin has hooks, you can add this plugin into different places on your theme.

For example, include all plugins with a hook on the head sections.
```
<head>
...
<?php
	Theme::plugins('siteHead');
?>
...
</head>
```

Include all plugins with the hook of the beginning of the body.
```
<body>
<?php
	Theme::plugins('siteBodyBegin');
?>
...
</body>
```

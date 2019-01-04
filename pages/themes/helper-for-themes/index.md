# Helper for themes
<!-- position: 200 -->

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

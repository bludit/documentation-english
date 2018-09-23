# Helper for themes
<!-- position: 100 -->

This helper tries to help developers by making them write less code and keep it more clean.

This object has static methods (see the colon where we call the methods).

<h2 id="title">Title</h2>

Print `<title>` head tag with dynamic content from the settings of your site.
```
<?php
	echo Theme::metaTags('title');
?>
```

HTML output
```
<title>Page title | Title site</title>
```

<h2 id="description">Description</h2>

Print `<description>` head tag with the field description from your settings or from the page.
```
<?php
	echo Theme::metaTags('description');
?>
```

HTML output
```
<meta name="description" content="Description about your site">
```

<h2 id="css-files">CSS files</h2>

This method generates the head tag to include the CSS file `blog.css` from the folder `/bludit/themes/{THEME_NAME}/css/`.
```
<?php
	echo Theme::css('css/blog.css');
?>
```

HTML output
```
<link rel="stylesheet" type="text/css" href="https://www.example.com/bl-themes/{THEME_NAME}/css/blog.css">
```

Or you can include a batch of CSS files
```
<?php
	echo Theme::css(array('css/file1.css', 'css/file2.css'));
?>
```

HTML output
```
<link rel="stylesheet" type="text/css" href="https://www.example.com/bl-themes/{THEME_NAME}/css/file1.css">
<link rel="stylesheet" type="text/css" href="https://www.example.com/bl-themes/{THEME_NAME}/css/file2.css">
```

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

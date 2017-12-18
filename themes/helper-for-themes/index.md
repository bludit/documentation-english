# Title: Helper for themes
<!-- Position: 100 -->
---

This helper tries to help developers by making them write less code and keep it more clean.

This object has static methods (see the colon where we call the methods).

## Title
Print `<title>` head tag with dynamic content from the settings of your site.
```
<?php
	echo Theme::headTitle();
?>
```

```
<title>Page title | Title site</title>
```

## Description
Print `<description>` head tag with the field description from your settings or from the page.
```
<?php
	echo Theme::headDescription();
?>
```

```
<meta name="description" content="Description about your site">
```

## CSS files
This method generates the head tag to include the CSS file `blog.css` from the folder `/bludit/themes/{THEME_NAME}/css/`.
```
<?php
	echo Theme::css('css/blog.css');
?>
```

```
<link rel="stylesheet" type="text/css" href="https://example.com/bl-themes/{THEME_NAME}/css/blog.css">
```

Or include a batch of CSS files
```
<?php
	echo Theme::css(array('css/file1.css', 'css/file2.css'));
?>
```

```
<link rel="stylesheet" type="text/css" href="https://example.com/bl-themes/{THEME_NAME}/css/file1.css">
<link rel="stylesheet" type="text/css" href="https://example.com/bl-themes/{THEME_NAME}/css/file2.css">
```

## Javascript files
This method generates the tag to include the Javascript file `main.js` from the folder `/bludit/themes/{THEME_NAME}/js/`.
```
<?php
	echo Theme::js('js/main.js');
?>
```

```
<script src="https://example.com/bl-themes/{THEME_NAME}/js/main.js"></script>
```

Or include a batch of Javascript files
```
<?php
	echo Theme::js(array('js/file1.js', 'js/file2.js'));
?>
```

```
<script src="https://example.com/bl-themes/{THEME_NAME}/js/file1.js"></script>
<script src="https://example.com/bl-themes/{THEME_NAME}/js/file2.js"></script>
```

## Favicon
This method generates the head tag for the favicon, in this example the favicon is on the root of the theme `/bludit/themes/{THEME_NAME}/favicon.png`.

```
<?php
	echo Theme::favicon('favicon.png');
?>
```

```
<link rel="shortcut icon" href="https://examples.com/bl-themes/{THEME_NAME}/favicon.png" type="image/png">
```

## Include Plugins
Bludit supports plugins and each plugin has hooks, you can add this plugin into different places on your theme.

For example, include all plugins with a hook on the head sections.
<pre><code data-language="php">
<head>
...
<?php
	Theme::plugins('siteHead');
?>
...
</head>
</code></pre>

Include all plugins with the hook of the beginning of the body.
<pre><code data-language="php">
<body>
<?php
	Theme::plugins('siteBodyBegin');
?>
...
</body>
</code></pre>

## Include jQuery
Bludit uses [jQuery](http://jquery.com) and provides a method to include it to your theme.

```
<?php
	echo Theme::jquery();
?>
```

```
<script src="https://example.com/bl-kernel/js/jquery.min.js"></script>
```

Or you can add [jQuery](http://jquery.com) from the official CDN.

```
<?php
	$cdn = true;
	echo Theme::jquery($cdn);
?>
```

```
<script src="https://code.jquery.com/jquery-3.2.1.min.js" integrity="sha256-hwg4gsxgFZhOsEEamdOYGBf13FyQuiTwlAQgxVSNgt4=" crossorigin="anonymous"></script>
```

## Include FontAwesome
Bludit uses [FontAwesome](http://fontawesome.io) and provides a method to include it to your theme.

```
<?php
	echo Theme::fontAwesome();
?>
```

```
<link rel="stylesheet" href="https://example.com/bl-kernel/css/font-awesome/css/font-awesome.min.css">
```

Or you can add [FontAwesome](http://fontawesome.io) from the CDN [BootstrapCDN](https://www.bootstrapcdn.com)

```
<?php
	$cdn = true;
	echo Theme::fontAwesome($cdn);
?>
```

```
<link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/font-awesome/4.7.0/css/font-awesome.min.css">
```

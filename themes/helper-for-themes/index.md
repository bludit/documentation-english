# Title: Helper for themes
<!-- Position: 100 -->
---
This helper try to help developers to make code more clean and less code to write.

This object has static methods (see the colon when call the methods).

## Title
Print `<title>` head tag with dynamic content from the settings of your site.
<pre><code data-language="php"><?php
	echo Theme::headTitle();
?></code></pre>

```
<title>Page title | Title site</title>
```

## Description
Print `<description>` head tag with the field description from your settings or from the page.
<pre><code data-language="php"><?php
	echo Theme::headDescription();
?></code></pre>

```
<meta name="description" content="Description about your site">
```

## CSS files
This method generate the head tag to include the CSS file `blog.css` from the folder `/bludit/themes/{THEME_NAME}/css/`.
<pre><code data-language="php"><?php
	echo Theme::css('css/blog.css');
?></code></pre>

```
<link rel="stylesheet" type="text/css" href="https://example.com/bl-themes/{THEME_NAME}/css/blog.css">
```

Or include a batch of CSS files
<pre><code data-language="php"><?php
	echo Theme::css(array('css/file1.css', 'css/file2.css'));
?></code></pre>

```
<link rel="stylesheet" type="text/css" href="https://example.com/bl-themes/{THEME_NAME}/css/file1.css">
<link rel="stylesheet" type="text/css" href="https://example.com/bl-themes/{THEME_NAME}/css/file2.css">
```

## Javascript files
This method generate the tag to include the Javascript file `main.js` from the folder `/bludit/themes/{THEME_NAME}/js/`.
<pre><code data-language="php"><?php
	echo Theme::js('js/main.js');
?></code></pre>

```
<script src="https://example.com/bl-themes/{THEME_NAME}/js/main.js"></script>
```

Or include a batch of Javascript files
<pre><code data-language="php"><?php
	echo Theme::js(array('js/file1.js', 'js/file2.js'));
?></code></pre>

```
<script src="https://example.com/bl-themes/{THEME_NAME}/js/file1.js"></script>
<script src="https://example.com/bl-themes/{THEME_NAME}/js/file2.js"></script>
```

## Favicon
This method generate the head tag for the favicon, in this example the favicon is on the root of the theme `/bludit/themes/{THEME_NAME}/favicon.png`.

<pre><code data-language="php"><?php
	echo Theme::favicon('favicon.png');
?></code></pre>

```
<link rel="shortcut icon" href="https://examples.com/bl-themes/{THEME_NAME}/favicon.png" type="image/png">
```

## Include Plugins
Bludit support plugins and each plugin have hooks, you can add this plugin into different places on your theme.

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
Bludit use [jQuery](http://jquery.com) and provide a method to include it to your theme.

<pre><code data-language="php"><?php
	echo Theme::jquery();
?></code></pre>

```
<script src="https://example.com/bl-kernel/js/jquery.min.js"></script>
```

Or you can add [jQuery](http://jquery.com) from the official CDN.

<pre><code data-language="php"><?php
	$cdn = true;
	echo Theme::jquery($cdn);
?></code></pre>

```
<script src="https://code.jquery.com/jquery-3.2.1.min.js" integrity="sha256-hwg4gsxgFZhOsEEamdOYGBf13FyQuiTwlAQgxVSNgt4=" crossorigin="anonymous"></script>
```

## Include FontAwesome
Bludit use [FontAwesome](http://fontawesome.io) and provide a method to include it to your theme.

<pre><code data-language="php"><?php
	echo Theme::fontAwesome();
?></code></pre>

```
<link rel="stylesheet" href="https://example.com/bl-kernel/css/font-awesome/css/font-awesome.min.css">
```

Or you can add [FontAwesome](http://fontawesome.io) from the CDN [BootstrapCDN](https://www.bootstrapcdn.com)

<pre><code data-language="php"><?php
	$cdn = true;
	echo Theme::fontAwesome($cdn);
?></code></pre>

```
<link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/font-awesome/4.7.0/css/font-awesome.min.css">
```
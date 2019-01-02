# CSS files
<!-- position: 5 -->

Bludit provides helpers to help developers by making them write less and keep a clean code.

For the purpose of this tutorial we will use the following names:
- `box 				- Name of the theme`
- `https://www.example.com 	- Site URL`
- `/bl-themes/box/		- Path of the theme`

Let's add a CSS file called `blog.css`, the file is located in `/bl-themes/box/blog.css`, you don't need to care about the absolute path.
```
<?php
	echo Theme::css('blog.css');
?>
```

HTML output
```
<link rel="stylesheet" type="text/css" href="https://www.example.com/bl-themes/box/blog.css">
```

<h2 id="full-example">Full example</h2>

The next HTML and PHP code is a complete example of how to include two CSS files in a theme.

```
<!DOCTYPE html>
<html>
	<head>
		<title>Hello</title>

		<?php
			echo Theme::css('blog.css');
			echo Theme::css('style.css');
		?>
	</head>
<body>

<h1>This is a Heading</h1>
<p>This is a paragraph.</p>

</body>
</html>
```

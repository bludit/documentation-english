# Favicon
<!-- position: 5 -->

Bludit provides helpers to help developers to write less code.

For the purpose of this tutorial we will use the following names:
- Name of the theme `box`
- Site URL `https://www.example.com`
- Theme path `/bl-themes/box/`
- Favicon file path `/bl-themes/box/favicon.png`

The next method from the helper `Theme::` generates the head tag for the favicon; by default, the MIME type returned is `image/png`.
```
<?php
	echo Theme::favicon('favicon.png');
?>
```

HTML output
```
<link rel="shortcut icon" href="https://www.example.com/bl-themes/box/favicon.png" type="image/png">
```

Also, you can specify the MIME type if you want to use another favicon type such as `.ico`.
```
<?php
	echo Theme::favicon('favicon.ico', 'image/x-icon');
?>
```

HTML output
```
<link rel="shortcut icon" href="https://www.example.com/bl-themes/box/favicon.ico" type="image/x-icon">
```

<h2 id="example">Example</h2>

Here's a complete example of how to include the favicon in a theme.

```
<!DOCTYPE html>
<html>
	<head>
		<title>Hello</title>

		<?php
			echo Theme::favicon('favicon.png');
		?>
	</head>
<body>

<h1>This is a Heading</h1>
<p>This is a paragraph.</p>

</body>
</html>
```

# Favicon
<!-- position: 5 -->

Bludit provides helpers to help developers to write less code.

<h2 id="usage">Usage</h2>

For the purpose of this tutorial we will use the following names:
- Theme's name `box`
- Site URL `https://www.example.com`
- Theme path `/bl-themes/box/`
- Favicon file path `/bl-themes/box/favicon.png`

The next method from the helper `HTML::` generates the head tag for the favicon; by default, the MIME type returned is `image/png`.
```
<?php
	echo HTML::favicon('favicon.png');
?>
```

HTML output.
```
<link rel="icon" href="https://www.example.com/bl-themes/box/favicon.png" type="image/png">
```

Also, you can specify the MIME type if you want to use another favicon type such as `.ico`.
```
<?php
	echo HTML::favicon('favicon.ico', 'image/x-icon');
?>
```

HTML output.
```
<link rel="icon" href="https://www.example.com/bl-themes/box/favicon.ico" type="image/x-icon">
```

<h2 id="example">Example</h2>

The next HTML and PHP snippet is a complete example of how to include the favicon.

```
<!DOCTYPE html>
<html>
	<head>
		<title>Hello</title>

		<?php
			echo HTML::favicon('favicon.png');
		?>
	</head>
<body>

<h1>This is a Heading</h1>
<p>This is a paragraph.</p>

</body>
</html>
```

# Javascript files
<!-- position: 4 -->

Bludit provides helpers for developers to write less code.

For the purpose of this tutorial we will use the following names:
- Name of the theme `box`
- Site URL `https://www.example.com`
- Theme path `/bl-themes/box/`
- Javascript file path `/bl-themes/box/main.js`

Let's add a Javascript file called `main.js`, the file is located in `/bl-themes/box/main.js`, you don't need to care about the absolute path if you the helper `Theme::`.
```
<?php
	echo Theme::js('main.js');
?>
```

HTML output
```
<script src="https://www.example.com/bl-themes/box/main.js"></script>
```

<h2 id="example">Example</h2>

The next HTML and PHP code is a complete example of how to include two Javascript files in a theme.

```
<!DOCTYPE html>
<html>
	<head>
		<title>Hello</title>
	</head>
<body>

<h1>This is a Heading</h1>
<p>This is a paragraph.</p>

<?php
	echo Theme::js('main.js');
	echo Theme::js('buttons.js');
?>

</body>
</html>
```

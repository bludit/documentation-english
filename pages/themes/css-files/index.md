# CSS files
<!-- position: 3 -->

Bludit provides helpers for developers, to help them write less code.

For the purpose of this tutorial, we will use the following names:
- Name of the theme `box`
- Site URL `https://www.example.com`
- Theme path `/bl-themes/box/`
- CSS file path `/bl-themes/box/style.css`

Let's add a CSS file called `style.css`. This file is located in `/bl-themes/box/style.css`; you don't need to worry about the absolute path if you use the `Theme::` helper.
```
<?php
	echo Theme::css('style.css');
?>
```

HTML output
```
<link rel="stylesheet" type="text/css" href="https://www.example.com/bl-themes/box/style.css">
```

<h2 id="example">Example</h2>

The next HTML and PHP snippet is a complete example of how to include two CSS files in a theme.

```
<!DOCTYPE html>
<html>
	<head>
		<title>Hello</title>

		<?php
			echo Theme::css('style.css');
			echo Theme::css('buttons.css');
		?>
	</head>
<body>

<h1>This is a Heading</h1>
<p>This is a paragraph.</p>

</body>
</html>
```

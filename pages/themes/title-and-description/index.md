# Title and description
<!-- position: 2 -->

Bludit provides helpers to help developers by making them write less and keep a clean code.

<h2 id="title">Title</h2>

Print `<title>` head tag with dynamic content. The title takes the configuration defined in the settings of your site.
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

Print `<description>` head tag with dynamic content. The description takes the configuration defined in the settings of your site.
```
<?php
	echo Theme::metaTags('description');
?>
```

HTML output
```
<meta name="description" content="Description about your site">
```

<h2 id="example">Example</h2>

The next HTML and PHP code is a complete example of how to use the title and description in a theme.

```
<!DOCTYPE html>
<html>
	<head>
		<?php
			echo Theme::metaTags('title');
			echo Theme::metaTags('description');
		?>
	</head>
<body>

<h1>This is a Heading</h1>
<p>This is a paragraph.</p>

</body>
</html>
```

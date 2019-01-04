# Include plugins
<!-- position: 6 -->

Bludit supports plugins and each plugin has hooks, the hooks are functions and these functions are executed in different places on the theme.

The list of hooks are here:
- https://docs.bludit.com/en/plugins/hooks-list

For example, for execute all plugins activated with the hook `siteHead` you can use the helper `Theme::plugins()`.
```
<?php
	Theme::plugins('siteHead');
?>
```

<h2 id="example">Example</h2>

The next HTML and PHP code is a complete example of how to include 3 types of hooks and execute in the correct place of the theme.

```
<!DOCTYPE html>
<html>
	<head>
		<title>Hello</title>

		<?php
			Theme::plugins('siteHead');
		?>
	</head>
<body>

<?php
	Theme::plugins('siteBodyBegin');
?>

<h1>This is a Heading</h1>
<p>This is a paragraph.</p>

<?php
	Theme::plugins('siteBodyEnd');
?>

</body>
</html>
```
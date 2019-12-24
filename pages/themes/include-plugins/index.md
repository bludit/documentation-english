# Include plugins
<!-- position: 6 -->

Bludit supports plugins, and each plugin has hooks; the hooks are functions, and these functions are executed in different places in the theme.

The list of hooks is here:
- https://docs.bludit.com/en/plugins/hooks-list

For example, to execute all plugins activated with the hook `siteHead`, you can use the `Theme::plugins()` helper.
```
<?php
	Theme::plugins('siteHead');
?>
```

<h2 id="example">Example</h2>

Here's a complete example of how to include 3 types of hooks, and execute them in the correct place in the theme.

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
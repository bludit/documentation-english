# Example: My first theme
<!-- position: 101 -->

Let's create a new and simple theme, which I will call `Coffee`.

- Create the theme inside the `/bl-themes/` folder; the path should look like this: `/bl-themes/coffee/`.
- Create the  `languages` folder, inside the `/bl-themes/coffee/` folder.
- Create the `en.json` file inside the `/bl-themes/coffee/languages/` folder.
- Create the `metadata.json` file inside the `/bl-themes/coffee/` folder.
- Create the `index.php`, file inside the `/bl-themes/coffee/` folder.

When done, you should have the following folder/file structure:

```
/bl-themes/coffee/
	languages/en.json
	metadata.json
	index.php
```

The next step is to create the content of the files. Let's start with the `index.php` and add the following HTML and PHP code:

```
<!DOCTYPE html>
<html>
<head>
	<meta charset="UTF-8">
	<title>Bludit</title>
</head>
<body>
	<?php foreach ($content as $page): ?>

		<h1><?php echo $page->title(); ?></h1>
		<div><?php echo $page->content(); ?></div>
		<hr>

	<?php endforeach; ?>
</body>
</html>
```

Edit the `languages/en.json` file to add the name and description of your theme.

```
{
	"theme-data":
	{
		"name": "Coffee",
		"description": "This is my first theme for Bludit."
	}
}
```

Now edit the `metadata.json` file to complete the information about the theme.

```
{
	"author": "Bludit",
	"email": "",
	"website": "",
	"version": "1.0",
	"releaseDate": "2019-01-01",
	"license": "MIT",
	"compatible": "3.0",
	"notes": ""
}
```

Congrats, you have your first theme for Bludit!. Now you can go to the Settings and activate your theme.

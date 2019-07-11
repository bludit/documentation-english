# Example: My first theme
<!-- position: 101 -->

Let's create a new and simple theme, I will call my new theme `Coffee`.

- Create the folder theme, inside the folder `/bl-themes/`, you will get `/bl-themes/coffee/`
- Create the folder `languages`, inside the folder `/bl-themes/coffee/`
- Create the file `en.json` inside the folder `/bl-themes/coffee/languages/`
- Create the file `metadata.json` inside the folder `/bl-themes/coffee/`
- Create the file `index.php`, inside the folder `/bl-themes/coffee/`

You are going to have the next folder and files structure.

```
/bl-themes/coffee/
	languages/en.json
	metadata.json
	index.php
```

Next steps are to create the content of the files. Let's start with the `index.php` and add the following HTML and PHP code.

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

Edit the file `languages/en.json` to add the name and description about the theme.

```
{
	"theme-data":
	{
		"name": "Coffee",
		"description": "This is my first theme for Bludit."
	}
}
```

Now edit the file `metadata.json` to complete the information about the theme.

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

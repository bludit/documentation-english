# Title: Example: My first theme
<!-- Position: 2 -->
---
Let's create a new and simple theme, I will call my new theme `Coffee`.

- Create the folder theme, inside the folder `/bl-themes/`, you will get `/bl-themes/coffee/`
- Create the folder `languages`, inside the folder `/bl-themes/coffee/`
- Create the file `en.json` inside the folder `/bl-themes/coffee/languages/`
- Create the file `metadata.json` inside the folder `/bl-themes/coffee/`
- Create the file `index.php`, inside the folder `/bl-themes/coffee/`

You are going to have the next folder and files structure.
```
/bl-themes/coffee/
	language/en.json
	metadata.json
	index.php
```

Next steps are create the content of the files, let's start with the `index.php` and add the follow HTML and PHP code.
<pre><code data-language="html"><!DOCTYPE html>
<html>
<head>
	<meta charset="UTF-8">
	<title>Bludit</title>
</head>
<body>
	<?php foreach ($pages as $Page): ?>

	<h1><?php echo $Page->title() ?></h1>
	<div><?php echo $Page->content() ?></div>

	<hr>

	<?php endforeach; ?>
</body>
</html>
</code></pre>

Edit the file `languages/en.json` to add the name and description about the theme.
<pre><code data-language="php">{
	"theme-data":
	{
		"name": "Coffee",
		"description": "This is my first theme for Bludit."
	}
}
</code></pre>

Now edit the file `metadata.json` to complete the information about the theme.
<pre><code data-language="php">{
	"author": "Bludit",
	"email": "",
	"website": "",
	"version": "1.0",
	"releaseDate": "2017-10-10",
	"license": "MIT",
	"compatible": "2.0",
	"notes": ""
}
</code></pre>

Congrats, you have your first theme for Bludit!

<div class="note">
<div class="title">Examples</div>
We have a Github repository with examples, take a look <a href="https://github.com/bludit/examples">Bludit Examples</a>.
</div>
# Title: Example: My second theme
<!-- Position: 3 -->
---
Second example about to create a them from scratch for Bludit, include how to add CSS, Javascript and support for plugins.

The next theme is called `Mars`.

If you are not interested in the tutorial you can download the source code of the <a href="https://github.com/bludit/examples/tree/master/themes/mars">Theme Mars</a>.

<h2 id="folder-structure">1. Folder structure</h2>
Create the folder for the theme inside the folder `/bl-themes/`, you will get `/bl-themes/mars/`.

Next, create the languages, css and js folders:
- Create the folder `languages` inside the folder `/bl-themes/mars/`
- Create the folder `css` inside the folder `/bl-themes/mars/`
- Create the folder `js` inside the folder `/bl-themes/mars/`

```
/bl-themes/mars/
	css/
	js/
	language/
```

<h2 id="name-and-information">2. Name and information</h2>
Create a file with the theme information. The file will be in the root theme folder, file `metadata.json`, with the next JSON code:

```
{
	"author": "Bludit",
	"email": "",
	"website": "",
	"version": "1.0",
	"releaseDate": "2018-02-14",
	"license": "MIT",
	"compatible": "2.0, 2.1, 2.2, 2.3",
	"notes": ""
}
```

Create another file with the name and description of the theme; create a file called `en.json` inside the folder `/bl-themes/mars/languages/`, with the next JSON code:

```
{
	"theme-data":
	{
		"name": "Mars",
		"description": "This is my second theme for Bludit."
	}
}
```
<h2 id="index">3. Index.php</h2>
Let's work on the file `index.php`, create the file inside the folder `/bl-themes/mars/`, with the next HTML code:

```
<!DOCTYPE html>
<html>
<head>
	<meta charset="UTF-8">
</head>
<body>

</body>
</html>
```

<h2 id="css-files">4. CSS files</h2>
Add some CSS files:
- Using the Helper object `Theme::css()`
- Using the HTML tag `<link href=".." rel="stylesheet" type="text/css" />`

In this case we are going to use the Helper to add the CSS file `/bl-themes/mars/css/style.css`. With the Helper you don't need to specified absolute path.

```
<!DOCTYPE html>
<html>
<head>
	<meta charset="UTF-8">

	<!-- CSS -->
	<?php echo Theme::css('css/style.css') ?>
</head>
<body>

</body>
</html>
```

<h2 id="javascript-files">5. Javascript files</h2>
Add some Javascript files:
- Using the Helper object `Theme::javascript()`
- Using the HTML tag `<script>...</script>`

In this case we are going to use the Helper to add the Javascript file `/bl-themes/mars/js/jquery.min.js`. With the Helper you don't need to specified absolute path.

```
<!DOCTYPE html>
<html>
<head>
	<meta charset="UTF-8">

	<!-- CSS -->
	<?php echo Theme::css('css/style.css') ?>

	<!-- Javascript -->
	<?php echo Theme::javascript('js/jquery.min.js') ?>
</head>
<body>

</body>
</html>
```

<h2 id="plugin-support">6. Add Plugin Support</h2>
Add support for plugins, you can use the helper `Theme::plugins()`.

The plugin hooks for the site are:
- `siteHead`, contains all the plugins which returns code for inside the `<head>...</head>`
- `siteBodyBegin`, contains all the plugins which returns code for inside the `<body>...</body>` at the beggining, could be some welcome banner, or some tool bar for the top.
- `siteBodyEnd`, contains all the plugins which returns code for inside the `<body>...</body>` at the bottom, such as javascript code.

```
<!DOCTYPE html>
<html>
<head>
	<meta charset="UTF-8">

	<!-- CSS -->
	<?php echo Theme::css('css/style.css') ?>

	<!-- Javascript -->
	<?php echo Theme::javascript('js/jquery.min.js') ?>

	<!-- Load plugins with the hook siteHead -->
	<?php Theme::plugins('siteHead') ?>
</head>
<body>
	<!-- Load plugins with the hook siteBodyBegin -->
	<?php Theme::plugins('siteBodyBegin') ?>

	<!-- Here all the rest of HTML code -->

	<!-- Load plugins with the hook siteBodyBegin -->
	<?php Theme::plugins('siteBodyEnd') ?>
</body>
</html>
```

<h2 id="site-title-and-slogan">7. Site title and slogan</h2>
You can use the Site-Object to get the title and slogan.

```
<!DOCTYPE html>
<html>
<head>
	<meta charset="UTF-8">

	<!-- CSS -->
	<?php echo Theme::css('css/style.css') ?>

	<!-- Javascript -->
	<?php echo Theme::javascript('js/jquery.min.js') ?>

	<!-- Load plugins with the hook siteHead -->
	<?php Theme::plugins('siteHead') ?>
</head>
<body>
	<!-- Load plugins with the hook siteBodyBegin -->
	<?php Theme::plugins('siteBodyBegin') ?>

	<h1><?php echo $site->title() ?></h1>
	<h2><?php echo $site->slogan() ?></h2>

	<!-- Load plugins with the hook siteBodyBegin -->
	<?php Theme::plugins('siteBodyEnd') ?>
</body>
</html>
```

<h2 id="where-am-i">8. Where Am I</h2>
Now lets works with the content of the site.

To locate what page the user is browsing on the site use the variable `$WHERE_AM_I`. For example, if the user is watching a page the value of the variable has the string `page`, and if the user is watching the main page (home page) the value of the variable is going to be `home`.

```
<!DOCTYPE html>
<html>
<head>
	<meta charset="UTF-8">

	<!-- CSS -->
	<?php echo Theme::css('css/style.css') ?>

	<!-- Javascript -->
	<?php echo Theme::javascript('js/jquery.min.js') ?>

	<!-- Load plugins with the hook siteHead -->
	<?php Theme::plugins('siteHead') ?>
</head>
<body>
	<!-- Load plugins with the hook siteBodyBegin -->
	<?php Theme::plugins('siteBodyBegin') ?>

	<h1><?php echo $site->title() ?></h1>
	<h2><?php echo $site->slogan() ?></h2>

	<?php if ($WHERE_AM_I=='page'): ?>
	<p>The user is watching a particular page</p>

	<?php elseif ($WHERE_AM_I=='home'): ?>
	<p>The user is watching the homepage</p>

	<?php endif ?>

	<!-- Load plugins with the hook siteBodyBegin -->
	<?php Theme::plugins('siteBodyEnd') ?>
</body>
</html>
```

<h2 id="main-content">9. Main Content</h2>
If the user is in the home page, Bludit generates an global array `$pages` with all the published pages, each page is a `Page Object`.

```
<!DOCTYPE html>
<html>
<head>
	<meta charset="UTF-8">

	<!-- CSS -->
	<?php echo Theme::css('css/style.css') ?>

	<!-- Javascript -->
	<?php echo Theme::javascript('js/jquery.min.js') ?>

	<!-- Load plugins with the hook siteHead -->
	<?php Theme::plugins('siteHead') ?>
</head>
<body>
	<!-- Load plugins with the hook siteBodyBegin -->
	<?php Theme::plugins('siteBodyBegin') ?>

	<h1><?php echo $site->title() ?></h1>
	<h2><?php echo $site->slogan() ?></h2>

	<?php if ($WHERE_AM_I=='page'): ?>
	<p>The user is watching a particular page</p>

	<?php elseif ($WHERE_AM_I=='home'): ?>
		<?php foreach ($pages as $page): ?>
		<h3><?php echo $page->title(); ?></h3>
		<?php endforeach ?>

	<?php endif ?>

	<!-- Load plugins with the hook siteBodyBegin -->
	<?php Theme::plugins('siteBodyEnd') ?>
</body>
</html>
```

If the user is watching a particular page, Bludit generates an global Page-Object `$page`, in this example, we are going to print the title and the content.

```
<!DOCTYPE html>
<html>
<head>
	<meta charset="UTF-8">

	<!-- CSS -->
	<?php echo Theme::css('css/style.css') ?>

	<!-- Javascript -->
	<?php echo Theme::javascript('js/jquery.min.js') ?>

	<!-- Load plugins with the hook siteHead -->
	<?php Theme::plugins('siteHead') ?>
</head>
<body>
	<!-- Load plugins with the hook siteBodyBegin -->
	<?php Theme::plugins('siteBodyBegin') ?>

	<h1><?php echo $site->title() ?></h1>
	<h2><?php echo $site->slogan() ?></h2>

	<?php if ($WHERE_AM_I=='page'): ?>
		<h3><?php echo $page->title(); ?></h3>

	<?php elseif ($WHERE_AM_I=='home'): ?>
		<?php foreach ($pages as $page): ?>
		<h3><?php echo $page->title(); ?></h3>
		<?php endforeach ?>

	<?php endif ?>

	<!-- Load plugins with the hook siteBodyBegin -->
	<?php Theme::plugins('siteBodyEnd') ?>
</body>
</html>
```

<div class="note">
<div class="title">Download</div>
Download the source code of the theme <a href="https://github.com/bludit/examples/tree/master/themes/mars">Mars</a>.
</div>

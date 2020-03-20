# Example: My second theme
<!-- position: 101 -->

Here's the second example of how to create a theme for Bludit from scratch, including CSS, Javascript, and support for plugins.

This one is called `Mars`.

If you are not interested in the tutorial, you can download the source code of the <a href="https://github.com/bludit/examples/tree/master/themes/mars">Mars theme</a>.

<h2 id="folder-structure">Folder structure</h2>
Create the folder for the theme inside the `/bl-themes/` folder; the path should look like this: `/bl-themes/mars/`.

Next, create the languages, CSS, and JS folders:
- Create the folder `languages` inside the folder `/bl-themes/mars/`
- Create the folder `css` inside the folder `/bl-themes/mars/`
- Create the folder `js` inside the folder `/bl-themes/mars/`

```
/bl-themes/mars/
	css/
	js/
	language/
```

<h2 id="name-and-information">Name and information</h2>
Create a file with the theme information. The file will be in the root theme folder, and should be named `metadata.json`. It should include the following JSON code:

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

Create another file called `en.json`, with the name and description of the theme. Put it in the `/bl-themes/mars/languages/` folder, with the following JSON code:

```
{
	"theme-data":
	{
		"name": "Mars",
		"description": "This is my second theme for Bludit."
	}
}
```
<h2 id="index">Index.php</h2>
Let's work on the `index.php` file; create the file inside the `/bl-themes/mars/` folder, with the following HTML code:

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

<h2 id="css-files">CSS files</h2>
Add some CSS files:
- Using the Helper object `Theme::css()`
- or using the HTML tag `<link href="..." rel="stylesheet" type="text/css" />`

In this case, we are going to use the Helper to add the CSS file `/bl-themes/mars/css/style.css`. With the Helper, you don't need to specify the absolute path.

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

<h2 id="javascript-files">Javascript files</h2>
Add some Javascript files:
- Using the Helper object `Theme::js()`
- or using the HTML tag `<script>...</script>`

In this case, we are going to use the Helper to add the Javascript file `/bl-themes/mars/js/mars.js`. With the Helper you don't need to specify the absolute path.

```
<!DOCTYPE html>
<html>
<head>
	<meta charset="UTF-8">

	<!-- CSS -->
	<?php echo Theme::css('css/style.css') ?>

	<!-- Javascript -->
	<?php echo Theme::js('js/mars.js') ?>
</head>
<body>

</body>
</html>
```

<h2 id="plugin-support">Add Plugin Support</h2>
To add support for plugins, you can use the helper `Theme::plugins()`.

The plugin hooks for the site are as follows:
- `siteHead` contains all the plugins, and returns code inside the `<head>...</head>` tags.
- `siteBodyBegin` contains all the plugins, and returns code inside the `<body>...</body>` tags at the top. You could use it for a welcome banner, or some tool bar for the top of the page.
- `siteBodyEnd` contains all the plugins, and returns code inside the `<body>...</body>` tags at the bottom, such as JavaScript code.

```
<!DOCTYPE html>
<html>
<head>
	<meta charset="UTF-8">

	<!-- CSS -->
	<?php echo Theme::css('css/style.css') ?>

	<!-- Javascript -->
	<?php echo Theme::js('js/mars.js') ?>

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

<h2 id="site-logo-title-and-slogan">Site logo, title and slogan</h2>
You can use the Site-Object to get the logo, title and slogan.

```
<!DOCTYPE html>
<html>
<head>
	<meta charset="UTF-8">

	<!-- CSS -->
	<?php echo Theme::css('css/style.css') ?>

	<!-- Javascript -->
	<?php echo Theme::js('js/mars.js') ?>

	<!-- Load plugins with the hook siteHead -->
	<?php Theme::plugins('siteHead') ?>
</head>
<body>
	<!-- Load plugins with the hook siteBodyBegin -->
	<?php Theme::plugins('siteBodyBegin') ?>

	<img src="<?php echo $site->logo() ?>" alt="" width="128">
	<h1><?php echo $site->title() ?></h1>
	<h2><?php echo $site->slogan() ?></h2>

	<!-- Load plugins with the hook siteBodyBegin -->
	<?php Theme::plugins('siteBodyEnd') ?>
</body>
</html>
```

<h2 id="where-am-i">Where Am I</h2>
Now let's work with the content of the site.

To locate what page the user is browsing on the site, you can use the variable `$WHERE_AM_I`. For example, if the user is viewing a page, the value of the variable has the string `page`, and if the user is viewing the front page (home page) the value of the variable is going to be `home`.

```
<!DOCTYPE html>
<html>
<head>
	<meta charset="UTF-8">

	<!-- CSS -->
	<?php echo Theme::css('css/style.css') ?>

	<!-- Javascript -->
	<?php echo Theme::js('js/mars.js') ?>

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

<h2 id="main-content">Main Content</h2>
If the user is on the home page, Bludit generates a global array `$pages` with all the published pages. Each page is a `Page Object`.

```
<!DOCTYPE html>
<html>
<head>
	<meta charset="UTF-8">

	<!-- CSS -->
	<?php echo Theme::css('css/style.css') ?>

	<!-- Javascript -->
	<?php echo Theme::js('js/mars.js') ?>

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
		<?php foreach ($content as $page): ?>
			<h3><?php echo $page->title(); ?></h3>
		<?php endforeach ?>
	<?php endif ?>

	<!-- Load plugins with the hook siteBodyBegin -->
	<?php Theme::plugins('siteBodyEnd') ?>
</body>
</html>
```

If the user is viewing a particular page, Bludit generates a global Page-Object `$page`. In this example, we are going to print the title and the content.

```
<!DOCTYPE html>
<html>
<head>
	<meta charset="UTF-8">

	<!-- CSS -->
	<?php echo Theme::css('css/style.css') ?>

	<!-- Javascript -->
	<?php echo Theme::js('js/mars.js') ?>

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
Download the source code of the <a href="https://github.com/bludit/examples/tree/master/themes/mars">Mars theme</a>.
</div>

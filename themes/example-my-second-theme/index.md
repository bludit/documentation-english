# Title: Example: My second theme
<!-- Position: 3 -->
---
## 1. Folder structure
Let's go to create the folder structure for the theme, this themes is called `Mars`.
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

## 2. Theme information
Create a file with the theme information; The file will be in the root theme folder, file `metadata.json`, with the next JSON code:

```
{
	"author": "Bludit",
	"email": "",
	"website": "",
	"version": "1.0",
	"releaseDate": "2017-10-10",
	"license": "MIT",
	"compatible": "2.0",
	"notes": ""
}
```

Now create another file with the name and description of the theme; create a file called `en.json` inside the folder `/bl-themes/mars/languages/`, with the next JSON code:

```
{
	"theme-data":
	{
		"name": "Mars",
		"description": "This is my second theme for Bludit."
	}
}
```

## 3. index.php
Let's work on the file `index.php`, create the file inside the folder `/bl-themes/mars/`, with the next HTML code:

<pre><code data-language="html"><!DOCTYPE html>
<html>
<head>
	<meta charset="UTF-8">
</head>
<body>

</body>
</html>
</code></pre>

### 3.1. CSS files
Add some CSS files, you can use the Helper `Theme::` or use the tag `link`. In this case we are going to use the Helper to add the CSS file `blog.css`.

<pre><code data-language="html"><!DOCTYPE html>
<html>
<head>
	<meta charset="UTF-8">

	<!-- CSS -->
	<?php echo Theme::css('css/blog.css') ?>
</head>
<body>

</body>
</html>
</code></pre>

### 3.2. JavaScript files
Add some JavaScript files, you can use the Helper `Theme::` or use the tag `script`. Follow the structure of CSS we are going to use the Helper here too to add the Javascript file `blog.js`.

<pre><code data-language="html"><!DOCTYPE html>
<html>
<head>
	<meta charset="UTF-8">

	<!-- CSS -->
	<?php echo Theme::css('css/blog.css') ?>

	<!-- Javascript -->
	<?php echo Theme::javascript('js/blog.js') ?>
</head>
<body>

</body>
</html>
</code></pre>

### 3.3. Plugins with the hook siteHead
Add support for plugins with the hook site head, just use the helper `Theme::plugins`.

<pre><code data-language="html"><!DOCTYPE html>
<html>
<head>
	<meta charset="UTF-8">

	<!-- CSS -->
	<?php echo Theme::css('css/blog.css') ?>

	<!-- Javascript -->
	<?php echo Theme::javascript('js/blog.js') ?>

	<!-- Load plugins with the hook siteHead -->
	<?php Theme::plugins('siteHead') ?>
</head>
<body>

</body>
</html>
</code></pre>

### 3.4. Site title
Add the title on the `head` and on the `body`.

<pre><code data-language="html"><!DOCTYPE html>
<html>
<head>
	<meta charset="UTF-8">

	<!-- Meta tag Title -->
	<title><?php echo $Site->title() ?></title>

	<!-- CSS -->
	<?php echo Theme::css('css/blog.css') ?>

	<!-- Javascript -->
	<?php echo Theme::javascript('js/blog.js') ?>

	<!-- Load plugins with the hook siteHead -->
	<?php Theme::plugins('siteHead') ?>
</head>
<body>
	<!-- Site Title -->
	<h1><?php echo $Site->title() ?></h1>
</body>
</html>
</code></pre>

### 3.5. Content
Now lets works with the content of the site.

To locate what page the user is browsing on the site use the variable `$WHERE_AM_I`. For example, if the user is watching a page the value of the variable has an string `page`, and if the user is watching the main page (home page) the value of the variable is going to be `home`.

<pre><code data-language="html"><!DOCTYPE html>
<html>
<head>
	<meta charset="UTF-8">

	<!-- Meta tag Title -->
	<title><?php echo $Site->title() ?></title>

	<!-- CSS -->
	<?php echo Theme::css('css/blog.css') ?>

	<!-- Javascript -->
	<?php echo Theme::javascript('js/blog.js') ?>

	<!-- Plugins site head -->
	<?php Theme::plugins('siteHead') ?>
</head>
<body>
	<!-- Site Title -->
	<h1><?php echo $Site->title() ?></h1>

	<?php
		if ($Url->whereAmI()=='home') {
			echo 'The user is browsing the front page';
		}
		elseif ($Url->whereAmI()=='page') {
			echo 'The user is browsing a particular page';
		}
		elseif ($Url->whereAmI()=='category') {
			echo 'The user is browsing a particular category';
		}
		elseif ($Url->whereAmI()=='tag') {
			echo 'The user is browsing a particular tag';
		}
	?>
</body>
</html>
</code></pre>

If the user is in the home page, Bludit generate an array `$pages` with all the published pages, each page is an [Page Object](https://).

<pre><code data-language="html"><!DOCTYPE html>
<html>
<head>
	<meta charset="UTF-8">

	<!-- Meta tag Title -->
	<title><?php echo $Site->title() ?></title>

	<!-- CSS -->
	<?php echo Theme::css('css/blog.css') ?>

	<!-- Javascript -->
	<?php echo Theme::javascript('js/blog.js') ?>

	<!-- Plugins site head -->
	<?php Theme::plugins('siteHead') ?>
</head>
<body>
	<!-- Site Title -->
	<h1><?php echo $Site->title() ?></h1>

	<?php
		if ($Url->whereAmI()=='home') {
			foreach ($pages as $Page) {
				echo '<h1>'.$Page->title().'</h1>';
				echo '<div>'.$Page->content().'</div>';
				echo '<hr>';
			}
		}
		elseif ($Url->whereAmI()=='page') {
			echo 'The user is browsing a particular page';
		}
		elseif ($Url->whereAmI()=='category') {
			echo 'The user is browsing a particular category';
		}
		elseif ($Url->whereAmI()=='tag') {
			echo 'The user is browsing a particular tag';
		}
	?>
</body>
</html>
</code></pre>

If the user is watching a particular page, Bludit generate an object `$Page`, on it you have a lot of methods, in this example will be use the methods `title()` and `content()`. To know other methods check the next page [Page Object](http://).

<pre><code data-language="html"><!DOCTYPE html>
<html>
<head>
	<meta charset="UTF-8">

	<!-- Meta tag Title -->
	<title><?php echo $Site->title() ?></title>

	<!-- CSS -->
	<?php echo Theme::css('css/blog.css') ?>

	<!-- Javascript -->
	<?php echo Theme::javascript('js/blog.js') ?>

	<!-- Plugins site head -->
	<?php Theme::plugins('siteHead') ?>
</head>
<body>
	<!-- Site Title -->
	<h1><?php echo $Site->title() ?></h1>

	<?php
		if ($Url->whereAmI()=='home') {
			foreach ($pages as $Page) {
				echo '<h1>'.$Page->title().'</h1>';
				echo '<div>'.$Page->content().'</div>';
				echo '<hr>';
			}
		}
		elseif ($Url->whereAmI()=='page') {
			echo '<h1>'.$Page->title().'</h1>';
			echo '<div>'.$Page->content().'</div>';
		}
		elseif ($Url->whereAmI()=='category') {
			echo 'The user is browsing a particular category';
		}
		elseif ($Url->whereAmI()=='tag') {
			echo 'The user is browsing a particular tag';
		}
	?>
</body>
</html>
</code></pre>

### 3.6. Plugins site body begins and ends
To finish the theme, add support for plugins in the body.

<pre><code data-language="html"><!DOCTYPE html>
<html>
<head>
	<meta charset="UTF-8">

	<!-- Meta tag Title -->
	<title><?php echo $Site->title() ?></title>

	<!-- CSS -->
	<?php echo Theme::css('css/blog.css') ?>

	<!-- Javascript -->
	<?php echo Theme::javascript('js/blog.js') ?>

	<!-- Plugins site head -->
	<?php Theme::plugins('siteHead') ?>
</head>
<body>
	<!-- Plugins site body begin -->
	<?php Theme::plugins('siteBodyBegin') ?>

	<!-- Site Title -->
	<h1><?php echo $Site->title() ?></h1>

	<?php
		if ($Url->whereAmI()=='home') {
			foreach ($pages as $Page) {
				echo '<h1>'.$Page->title().'</h1>';
				echo '<div>'.$Page->content().'</div>';
				echo '<hr>';
			}
		}
		elseif ($Url->whereAmI()=='page') {
			echo '<h1>'.$Page->title().'</h1>';
			echo '<div>'.$Page->content().'</div>';
		}
		elseif ($Url->whereAmI()=='category') {
			echo 'The user is browsing a particular category';
		}
		elseif ($Url->whereAmI()=='tag') {
			echo 'The user is browsing a particular tag';
		}
	?>

	<!-- Plugins site body end -->
	<?php Theme::plugins('siteBodyEnd') ?>

</body>
</html>
</code></pre>

<div class="note">
<div class="title">Examples</div>
We have a Github repository with examples, take a look at <a href="https://github.com/bludit/examples">Bludit Examples</a>.
</div>
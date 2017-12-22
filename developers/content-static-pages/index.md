# Title: Content > Static Pages
<!-- Position: 4 -->
---
Bludit has two types of content, **pages** and **static pages**.

- **Pages** are ordered by the settings defined on **Settings > Advanced > Order by**, by default is by date.
- **Static pages** are ordered by position all the time.

In this section we are going to show some snippet code to work with **static pages**.

## Show all the static pages
The easy way is using the function `buildStaticPages()`
```
<?php
	// Each static page is an Page-Object
	$staticPages = buildStaticPages();

	foreach ($staticPages as $page) {
		echo $page->title();
	}
?>
```

Or you can use the the object `$dbPages` to get the database with the keys of the static pages.
```
<?php
	// Get the keys of the static pages
	$staticPages = $dbPages->getStaticDB();

	// Foreach page key build the page and print the title
	foreach ($staticPages as $pageKey) {
		// buildPage function returns a Page-Object
		$page = buildPage($pageKey);

		echo $page->title();
	}
?>
```

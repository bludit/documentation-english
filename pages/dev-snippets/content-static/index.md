# Content: Static
<!-- position: 4 -->

In this section, we are going to show some snippet code to work with **static pages**.

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

Or you can use the the object `$dbPages` to get the database of keys of the static pages and build the pages.

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

# Content: Pages
<!-- position: 3 -->

The examples belows are for the **Pages** content type; the pages must published (visible for the users) for these examples to work.

<h2 id="list-all-pages-from-the-active-page">List all sub-pages on the active page:</h2>

Bludit provides a predefined `$content` array with all the sub-pages (or child pages) of the current page the user is viewing. This array is used for the themes. The following code prints the title and the content of the pages.

```
<?php
	foreach ($content as $page) {
		echo $page->title();
		echo $page->content();
	}
?>
```

<h2 id="list-the-latest-5-pages">List the latest 5 pages</h2>

This code snippet prints the `title` of the latest 5 pages with the status `published`.

```
<?php
	// Page number, the first page is 1
	$pageNumber = 1;

	// Number of items to return
	$numberOfItems = 5;

	// Only get the pages with the status published
	$onlyPublished = true;

	// Get the list of keys of pages
	$items = $pages->getList($pageNumber, $numberOfItems, $onlyPublished);

	foreach ($items as $key) {
		// buildPage function returns a Page-Object
		$page = buildPage($key);

		// Print the page title
		echo $page->title();
	}
?>
```

<h2 id="list-all-pages">List all the pages</h2>

This code snippet prints the `title` of all of pages in the system with the status `published`. Please note that it can affect performance, depending on the number of pages.

```
<?php
	// Page number of the paginator, the first page is 1
	$pageNumber = 1;

	// The value -1 tell to Bludit to returns all the pages on the system
	$numberOfItems = -1;

	// Only get the pages with the satus published
	$onlyPublished = true;

	// Get the list of keys of pages
	$items = $pages->getList($pageNumber, $numberOfItems, $onlyPublished);

	foreach ($items as $key) {
		// buildPage function returns a Page-Object
		$page = buildPage($key);

		// Print the page title
		echo $page->title();
	}
?>
```

## Working with subpages
Bludit supports one level of subpages.

To work properly with subpages, you need to set up the order filter by `position`.

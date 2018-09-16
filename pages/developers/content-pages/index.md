# Content > Pages
<!-- Position: 3 -->

Bludit has two types of content, **pages** and **static pages**.

- **Pages** are ordered by the settings defined on **Settings > Advanced > Order by**, by default is by date.
- **Static pages** are ordered by position all the time.

In this section, we are going to show some snippet code to work with **pages**.

## List the latest 5 pages
This snippet code prints the `title` of the latest 5 pages with the status published.

```
<?php
	// Page number of the paginator, the first page is 1
	$pageNumber = 1;
	// Amount of items to return
	$amountOfItems = 5;
	// Only get the pages with the satus published
	$onlyPublished = true;
	// Get the list of keys of pages
	$pages = $dbPages->getList($pageNumber, $amountOfItems, $onlyPublished);

	foreach ($pages as $pageKey) {
		// buildPage function returns a Page-Object
		$page = buildPage($pageKey);

		echo $page->title();
	}
?>
```

## List all the pages
This snippet code prints the `title` of all of pages in the system with the status published.

```
<?php
	// Page number of the paginator, the first page is 1
	$pageNumber = 1;
	// The value -1 tell to Bludit to returns all the pages on the system
	$amountOfItems = -1;
	// Only get the pages with the satus published
	$onlyPublished = true;
	// Get the list of keys of pages
	$pages = $dbPages->getList($pageNumber, $amountOfItems, $onlyPublished);

	foreach ($pages as $pageKey) {
		// buildPage function returns a Page-Object
		$page = buildPage($pageKey);

		echo $page->title();
	}
?>
```

## Working with subpages
Bludit supports one level of subpages.

To work properly with subpages you need to set-up the order filter by `position`.

We create a section dedicated to this topic: [Parents and Children](https://docs.bludit.com/en/developers/parents-and-children)

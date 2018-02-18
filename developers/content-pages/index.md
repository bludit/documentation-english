# Title: Content > Pages
<!-- Position: 3 -->
---
Bludit has two types of content, **pages** and **static pages**.

- **Pages** are ordered by the settings defined on **Settings > Advanced > Order by**, by default is by date.
- **Static pages** are ordered by position all the time.

In this section, we are going to show some snippet code to work with **pages**.

## List the latest 5 pages
This snippet code print the `title` of the latest 5 pages, ordered by the settings (*by date or position*) and the status published.

```
<?php
	$pageNumber = 1;
	$amountOfItems = 5;
	// Only get the pages with the satus published
	$onlyPublished = true;
	$pages = $dbPages->getList($pageNumber, $amountOfItems, $onlyPublished);

	foreach ($pages as $pageKey) {
		// buildPage function returns a Page-Object
		$page = buildPage($pageKey);

		echo $page->title();
	}
?>
```

## List all the pages
This snippet code print the `title` of all of pages in the system, ordered by the settings (by date or position) and the status published.

```
<?php
	$pageNumber = 1;
	// The value -1 tell to Bludit to returns all the pages on the system
	$amountOfItems = -1;
	// Only get the pages with the satus published
	$onlyPublished = true;
	$pages = $dbPages->getList($pageNumber, $amountOfItems, $onlyPublished);

	foreach ($pages as $pageKey) {
		// buildPage function returns a Page-Object
		$page = buildPage($pageKey);

		echo $page->title();
	}
?>
```


# Title: Content > Pages
<!-- Position: 3 -->
---
Bludit has two types of content, **pages** and **static pages**.

- **Pages** are ordered by the settings defined on **Settings > Advanced > Order by**, by default is by date.
- **Static pages** are ordered by position all the time.

In this section we are going to show some snippet code to work with **pages**.

<div class="note">
The following codes work in Bludit > v2.1
</div>

## Show the 5 latest pages
This snippet code print the `title` of the latest 5 pages ordered by the settings (by date or position) and the pages are published.
```
<?php
	$pageNumber = 1;
	$amountOfItems = 5;
	$onlyPublished = true;
	$pages = $dbPages->getList($pageNumber, $amountOfItems, $onlyPublished);

	foreach ($pages as $pageKey) {
		// buildPage function returns a Page-Object
		$page = buildPage($pageKey);

		echo $page->title();
	}
?>
```


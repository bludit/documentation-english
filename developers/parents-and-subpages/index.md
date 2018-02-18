# Title: Parents and Subpages
<!-- Position: 7 -->
---
<div class="note">
The following codes work in Bludit > v2.3
</div>

## Check if a page has children (subpages)

```
<?php
	// The variable $page is an Page-Object
	if ($page->hasChildren())) {
		echo 'The page has children';
	} else {
		echo 'The page has not children';
	}
?>
```

## List all children of a page

```
<?php
	// The variable $page is an Page-Object
	$children = $page->children();

	// Each child is a Page-Object
	foreach ($children as $child) {
		echo $child->title();
	}
?>
```

## Check if a page is a child (has a parent)

```
<?php
	// The variable $page is an Page-Object
	if ($page->isChild())) {
		echo 'The page is a child';
	} else {
		echo 'The page is not a child';
	}
?>
```

## Print the title of the parent page of a child
If a page has a child you can call the methods of the parent page with the method `parentMethod()`.

```
<?php
	// The variable $page is an Page-Object
	if ($page->isChild())) {
		echo 'Title of the parent page: ' . $page->parentMethod('title');
	} else {
		echo 'The page is not child';
	}
?>
```

## Print a Navigation Bar
This example recommend to have a structure of `pages and subpages (children)`, and the content of your site ordered by `position`.

Note: A parent page might or may not have children.

```
<?php
	// Get the list of parent pages
	$parents = buildParentPages();

	foreach ($parents as $parent) {
		echo $parent->title();

		// Check if the page has children
		if ($parent->hasChildren()) {
			// Get the list of children
			$children = $parent->children();

			foreach ($children as $child) {
				echo " > " . $child->title();
			}
		}
	}
?>
```

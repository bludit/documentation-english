# Parents and subpages
<!-- position: 7 -->

<div class="note">
The following snippets work in Bludit > v2.3
</div>

## Check if a page has children (subpages)

```
<?php
	// The variable $page is an Page-Object
	if ($page->hasChildren())) {
		echo 'The page has children';
	} else {
		echo 'The page does not have children';
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

## Print the title of the parent page from the child
If a page has a child, you can call the methods of the parent page with `parentMethod()`.

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
A parent page might or may not have children.

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

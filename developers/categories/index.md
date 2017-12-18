# Title: Categories
<!-- Position: 5 -->
---
Snipped codes to work with categories.

<div class="note">
The follow codes works on Bludit > v2.1
</div>

<div class="note">
By default, the database of categories is alphanumeric sorted.
</div>

## List all categories
```
<?php
	$categories = getCategories();

	foreach ($categories as $category) {
		echo 'Category name: '	. $category['name'];
		echo 'Category key: ' 	. $category['key'];
		echo 'Category link: ' 	. $category['link'];
		echo 'Category amount of pages: ' . count($category['list']);
	}
?>
```

## List only the categories that have pages
```
<?php
	$categories = getCategories();

	foreach ($categories as $category) {
		if (count($category['list'])>0) {
			echo 'Category name: '	. $category['name'];
			echo 'Category key: ' 	. $category['key'];
			echo 'Category link: ' 	. $category['link'];
		}
	}
?>
```

## List all categories and the pages linked to it
```
<?php
	$categories = getCategories();

	foreach ($categories as $category) {
		echo 'Category name: ' . $category['name'];

		// The variable $category['list'] contains all the pages key related to this category
		foreach ($category['list'] as $pageKey) {
			$page = buildPage($pageKey);
			echo '- Page title: ' . $page->title();
		}
	}
?>
```

## List all pages linked to a particular category
```
<?php
        // Category key
        $categoryKey = 'example';

        // Get the fields of the category
        $category = getCategory($categoryKey);

        // Print the category name
        echo 'Category name: ' . $category['name'];

        // Print the pages title linked to the category "example"
        foreach ($category['list'] as $pageKey) {
                $page = buildPage($pageKey);
                echo $page->title();
        }
?>
```

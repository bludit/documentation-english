# Title: Categories
<!-- Position: 5 -->
---
Snippet code to work with categories.

<div class="note">
The following codes work in Bludit > v2.1
</div>

<div class="note">
By default, the database of categories is alphanumeric sorted.
</div>

## List all categories
```
<?php
	// Each category is an Category-Object
	$categories = getCategories();

	foreach ($categories as $category) {
		echo 'Category name: '	. $category->name();
		echo 'Category key: ' 	. $category->key();
		echo 'Category link: ' 	. $category->permalink();
		echo 'Category amount of pages: ' . count($category->pages());
	}
?>
```

## List only the categories that have pages
```
<?php
	$categories = getCategories();

	foreach ($categories as $category) {
		// Each category is an Category-Object
		if (count($category->pages())>0) {
			echo 'Category name: '	. $category->name();
			echo 'Category key: ' 	. $category->key();
			echo 'Category link: ' 	. $category->permalink();
		}
	}
?>
```

## List all categories and the pages linked to it
```
<?php
	$categories = getCategories();

	foreach ($categories as $category) {
		// Each category is an Category-Object
		echo 'Category name: ' . $category->name();

		// The variable $category['list'] contains all the pages key related to this category
		foreach ($category->pages() as $pageKey) {
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

	// The category is an Category-Object
        $category = getCategory($categoryKey);

        // Print the category name
        echo 'Category name: ' . $category->name();

        // Print the pages title linked to the category "example"
        foreach ($category->pages() as $pageKey) {
		// buildPage function returns a Page-
                $page = buildPage($pageKey);

                echo $page->title();
        }
?>
```

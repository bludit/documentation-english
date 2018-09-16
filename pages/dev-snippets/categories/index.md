# Title: Categories
<!-- Position: 5 -->
---
Code snippet to work with categories.

Predefined variables for categories:
- `$categories` is Categories object, [here the class](https://github.com/bludit/bludit/blob/master/bl-kernel/categories.class.php)

<div class="note">
By default, the database of categories is alphanumeric sorted.
</div>

<h2 id="list-all-categories">List all categories</h2>

```
<?php
	$items = getCategories();

	foreach ($items as $category) {
		// Each category is an Category-Object
		echo 'Category name: '			. $category->name();
		echo 'Category key: ' 			. $category->key();
		echo 'Category description: ' 		. $category->description();
		echo 'Category template: ' 		. $category->template();
		echo 'Category link: ' 			. $category->permalink();
		echo 'Category number of pages: ' 	. count($category->pages());
	}
?>
```

Alternative

```
<?php
	foreach ($categories->keys() as $key) {
		// Create Category-Object
		$category = new Category($key);

		echo 'Category name: '			. $category->name();
		echo 'Category key: ' 			. $category->key();
		echo 'Category description: ' 		. $category->description();
		echo 'Category template: ' 		. $category->template();
		echo 'Category link: ' 			. $category->permalink();
		echo 'Category amount of pages: ' 	. count($category->pages());
	}
?>
```

<h2 id="list-categories-that-have-pages">List categories that have pages</h2>

```
<?php
	$items = getCategories();

	foreach ($items as $category) {
		// Each category is an Category-Object
		if (count($category->pages())>0) {
			echo 'Category name: '	. $category->name();
			echo 'Category key: ' 	. $category->key();
			echo 'Category link: ' 	. $category->permalink();
		}
	}
?>
```

<h2 id="list-all-categories-and-pages">List all categories and the pages related to the category</h2>

```
<?php
	$items = getCategories();

	foreach ($items as $category) {
		// Each category is an Category-Object
		echo 'Category name: ' . $category->name();

		// The method $category->pages() returns all the pages keys releated to the category
		foreach ($category->pages() as $pageKey) {
			$page = new Page($pageKey);
			echo '- Page title: ' . $page->title();
		}
	}
?>
```

<h2 id="list-all-pages-related-to-a-particular-category">List all pages related to a particular category</h2>

```
<?php
        // Category key
        $categoryKey = 'example';

	// The category is an Category-Object
        $category = getCategory($categoryKey);

        // Print the category name
        echo 'Category name: ' . $category->name();

        // Print the pages title related to the category "example"
        foreach ($category->pages() as $pageKey) {
		$page = new Page($pageKey);
		echo $page->title();
        }
?>
```

<h2 id="get-the-active-category">Get the active category</h2>

```
<?php
	// Check if the user is browsing a category
	if ($WHERE_AM_I=='category') {
		// Get the category key from the URL
		$categoryKey = $Url->slug();

		// Create the Category-Object
		$category = new Category($categoryKey);

		// Print the category name
		echo $category->name();

		// Print the category description
		echo $category->description();
	}
?>
```

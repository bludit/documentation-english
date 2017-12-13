# Title: Categories
<!-- Position: 3 -->
---
This section is focus on how to work with categories on your themes and your plugins.

## List all categories
```
<?php
	// $dbCategories is the object who handle the categories
	foreach ($dbCategories->db as $key=>$fields) {
		echo 'Category name: ' . $fields['name'] . PHP_EOL;
		echo 'Category key: '. $key . PHP_EOL;
		echo 'Category link: ' . DOMAIN_CATEGORIES . $key . PHP_EOL;
		echo 'Category amount of items: '.count($fields['list']) . PHP_EOL;
	}
?>
```

## List all categories containing items
```
<?php
	foreach ($dbCategories->db as $key=>$fields) {
		if (count($fields['list']) > 0) {
			echo 'Category name: ' . $fields['name'] . PHP_EOL;
			echo 'Category key: '. $key . PHP_EOL;
			echo 'Category link: ' . DOMAIN_CATEGORIES . $key . PHP_EOL;
		}
	}
?>
```

## List all categories and the pages linked to it
```
<?php
	foreach ($dbCategories->db as $key=>$fields) {

		echo 'Category name: ' . $fields['name'] . PHP_EOL;

		foreach ($fields['list'] as $pageKey) {
			$page = buildPage($pageKey);
			echo 'Page title: ' . $page->title() . PHP_EOL;
		}

		echo ' ---- ' . PHP_EOL;
	}
?>
```

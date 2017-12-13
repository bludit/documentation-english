# Title: Categories
<!-- Position: 3 -->
---
How to work with categories on your themes and plugins.

## List all categories
<pre><code data-language="php"><?php
	// $dbCategories is the object who handle the categories
	foreach ($dbCategories->db as $key=>$fields) {
		echo 'Category name: ' . $fields['name'] . PHP_EOL;
		echo 'Category key: '. $key . PHP_EOL;
		echo 'Category link: ' . DOMAIN_CATEGORIES . $key . PHP_EOL;
		echo 'Category amount of items: '.count($fields['list']) . PHP_EOL;
	}
?></code></pre>

## List all categories containing pages
<pre><code data-language="php"><?php
	// $dbCategories is the object who handle the categories
	foreach ($dbCategories->db as $key=>$fields) {
		if (count($fields['list']) > 0) {
			echo 'Category name: ' . $fields['name'] . PHP_EOL;
			echo 'Category key: '. $key . PHP_EOL;
			echo 'Category link: ' . DOMAIN_CATEGORIES . $key . PHP_EOL;
		}
	}
?></code></pre>

## List all categories and the pages linked to it
<pre><code data-language="php"><?php
	foreach ($dbCategories->db as $key=>$fields) {
		echo 'Category name: ' . $fields['name'] . PHP_EOL;

		foreach ($fields['list'] as $pageKey) {
			$page = buildPage($pageKey);
			echo 'Page title: ' . $page->title() . PHP_EOL;
		}

		echo ' ---- ' . PHP_EOL;
	}
?></code></pre>

# Title: Categories
<!-- Position: 3 -->
---
How to work with categories on your themes and plugins.

## List all categories
<pre><code data-language="php"><?php
	// $dbCategories is the object who handle the categories
	foreach ($dbCategories->db as $key=>$fields) {
		echo 'Category name: ' . $fields['name'];
		echo 'Category key: ' . $key;
		echo 'Category link: ' . DOMAIN_CATEGORIES . $key;
		echo 'Category amount of items: ' . count($fields['list']);
	}
?></code></pre>

## List only the categories that have pages
<pre><code data-language="php"><?php
	// $dbCategories is the object who handle the categories
	foreach ($dbCategories->db as $key=>$fields) {
		if (count($fields['list']) > 0) {
			echo 'Category name: ' . $fields['name'];
			echo 'Category key: ' . $key;
			echo 'Category link: ' . DOMAIN_CATEGORIES . $key;
		}
	}
?></code></pre>

## List all categories and the pages linked to it
<pre><code data-language="php"><?php
	// $dbCategories is the object who handle the categories
	foreach ($dbCategories->db as $key=>$fields) {
		echo 'Category name: ' . $fields['name'];

		// The variable $fields['list'] contains all the pages key related to this category
		foreach ($fields['list'] as $pageKey) {
			$page = buildPage($pageKey);
			echo '- Page title: ' . $page->title();
		}
	}
?></code></pre>

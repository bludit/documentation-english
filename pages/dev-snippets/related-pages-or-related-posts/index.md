# Related pages or related posts
<!-- position: 10 -->

Get the list of pages related to one page. Remember the concept of pages and posts in Bludit are the same.

## Example: Get related pages
The following example prints the title of each related page from the current page.

```php
<?php
$relatedPages = $page->related();
foreach ($relatedPages as $pageKey) {
	$related = new Page($pageKey);
	echo $related->title();
}
?>
```

## Example: Sort related pages
The method `->related()` returns the page list without any kind of sort, you can sort by date which the following example.

```php
<?php
// Insert in array by unixtimestamp
$sort = array();
$relatedPages = $page->related();
foreach ($relatedPages as $pageKey) {
	$tmp = new Page($pageKey);
	$sort[$tmp->date['U']] = new Page($pageKey);
}

// Sort array by key which is unixtimestamp
krsort($sort);

// Print related page title and date
foreach ($sort as $related) {
	echo $related->title();
	echo $related->date();
}
?>
```
# Tags
<!-- position: 6 -->

Code snippets for working with tags.

Predefined variables for tags:
- `$tags` is Tag Object, [here the class](https://github.com/bludit/bludit/blob/master/bl-kernel/tags.class.php)

<div class="note">
By default, the database of tags is alphanumerically sorted.
</div>

<h2 id="list-all-tags">List all tags</h2>

```
<?php
	// Returns an array with all the tags
	$items = getTags();

	foreach ($items as $tag) {
		// Each tag is an Tag-Object
		echo 'Tag name: '		. $tag->name();
		echo 'Tag key: ' 		. $tag->key();
		echo 'Tag link: ' 		. $tag->permalink();
		echo 'Tag number of pages: ' 	. count($tag->pages());
	}
?>
```

Alternative:

```
<?php
	foreach ($tags->keys() as $key) {
		// Create Tag-Object
		$tag = new Tag($key);

		echo 'Tag name: '		. $tag->name();
		echo 'Tag key: ' 		. $tag->key();
		echo 'Tag link: ' 		. $tag->permalink();
		echo 'Tag number of pages: ' 	. count($tag->pages());
	}
?>
```

<h2 id="list-tags-that-have-pages">List tags that have pages</h2>

```
<?php
	$items = getTags();

	foreach ($items as $tag) {
		// Each tag is an Tag-Object
		if (count($tag->pages())>0) {
			echo 'Tag name: '	. $tag->name();
			echo 'Tag key: ' 	. $tag->key();
			echo 'Tag link: ' 	. $tag->permalink();
		}
	}
?>
```

<h2 id="list-all-tags-and-pages">List all tags and the pages related to the tag</h2>

```
<?php
	$items = getTags();

	foreach ($items as $tag) {
		// Each tag is an Tag-Object
		echo 'Tag name: ' . $tag->name();

		// The method $tag->pages() returns all the pages keys releated to the tag
		foreach ($tag->pages() as $pageKey) {
			$page = new Page($pageKey);
			echo '- Page title: ' . $page->title();
		}
	}
?>
```

<h2 id="list-all-pages-related-to-a-particular-tag">List all pages related to a particular tag</h2>

```
<?php
        // Tag key
        $tagKey = 'example';

	// The tag is an Tag-Object
        $tag = getTag($tagKey);

        // Print the tag name
        echo 'Tag name: ' . $tag->name();

        // Print the pages title related to the tag "example"
        foreach ($tag->pages() as $pageKey) {
		$page = new Page($pageKey);
		echo $page->title();
        }
?>
```

<h2 id="get-the-active-tag">Get the active tag</h2>

```
<?php
	// Check if the user is browsing a tag
	if ($WHERE_AM_I=='tag') {
		// Get the tag key from the URL
		$tagKey = $Url->slug();

		// Create the Tag-Object
		$tag = new Tag($tagKey);

		// Print the tag name
		echo $tag->name();
	}
?>
```

<h2 id="print-the-tags-of-a-page">Tags of a page</h2>

Print the tags of a page:
```
<?php
	$returnsArray = true;

	$items = $page->tags($returnsArray);

	foreach ($items as $tagKey=>$tagName) {
		echo $tagName;
	}
?>
```

Print the tags and permalink:
```
<?php
	$returnsArray = true;

	$items = $page->tags($returnsArray);

	foreach ($items as $tagKey=>$tagName) {
		$tag = new Tag($tagKey);

		echo '<a href="'.$tag->permalink().'">'.$tag->name().'</a>';
	}
?>
```


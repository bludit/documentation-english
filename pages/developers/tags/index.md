# Tags
<!-- Position: 6 -->
---
Snippet code to work with tags.

<div class="note">
The following codes work in Bludit > v2.1
</div>

<div class="note">
By default, the database of tags is alphanumeric sorted.
</div>

## List all tags
```
<?php
	$tags = getTags();

	foreach ($tags as $tag) {
		echo 'Tag name: '	. $tag->name();
		echo 'Tag key: ' 	. $tag->key();
		echo 'Tag link: ' 	. $tag->permalink();
		echo 'Tag amount of pages: ' . count($tag->pages());
	}
?>
```

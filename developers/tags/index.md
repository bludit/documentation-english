# Title: Tags
<!-- Position: 6 -->
---
How to work with tags on your themes and plugins.

<div class="note">
<div class="title">Note</div>
By default, the database of tags is alphanumeric sorted.
</div>

## List all tags
```
<?php
	foreach ($dbTags->db as $key=>$tag) {
		echo 'Tag name:' . $tag['name'];
		echo 'Tag amount of linked pages:' . count($tag['list']);
		echo 'Tag key: ' . $key;
		echo 'Tag link: ' . DOMAIN_TAG . $key;
	}
?>
```

## List all pages linked to a particular tag
```
<?phpi
        // Tag key
        $tagKey = 'example';

        // Get the map from the tag database object
        $tag = $dbTags->getMap($tagKey);

        // Print the tag name
        echo 'Tag name: ' . $tag['name'];

        // Print the pages title linked to the tag "example"
        foreach ($tag['list'] as $pageKey) {
                $page = buildPage($pageKey);
                echo $page->title();
        }
?>
```


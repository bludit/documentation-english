# Title: Tags
<!-- Position: 5 -->
---
How to work with tags on your themes and plugins.

## List all tags
<pre><code data-language="php"><?php
	foreach( $dbTags->db as $key=>$tag ) {
		echo 'Tag name:' . $tag['name'];
		echo 'Tag amount of linked pages:' . count($tag['list']);
		echo 'Tag key: ' . $key;
		echo 'Tag link: ' . DOMAIN_TAG . $key;
	}
?></code></pre>

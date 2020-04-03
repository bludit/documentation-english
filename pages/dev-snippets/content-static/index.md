# Content: Static
<!-- position: 4 -->

This section is related to the content of [static pages](https://docs.bludit.com/en/content/content-basics#static).

## Show all the static pages
Bludit has a [predefined variable for static pages](https://docs.bludit.com/en/developers/predefined-variables#staticContent) named `$staticContent`. This variable is an array with all the static pages.

```
<?php
	// Each static page is an Page-Object
	foreach ($staticContent as $page) {
		echo $page->title();
	}
?>
```

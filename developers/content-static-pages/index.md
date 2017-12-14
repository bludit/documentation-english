# Title: Content > Static Pages
<!-- Position: 4 -->
---
Bludit has two types of content, **pages** and **static pages**.

- **Pages** are ordered by the settings defined on **Settings > Advanced > Order by**, by default is by date.
- **Static pages** are ordered by position all the time.

## Show all the static pages
The easy way is using the function `buildStaticPages()`
<pre><code data-language="php"><?php
	$staticPages = buildStaticPages();
	
	foreach ($staticPages as $index=>$page) {
		echo $page->title();
	}
?></code></pre>

Or you can use the the object `$dbPages` to get the database with the keys of the static pages.
<pre><code data-language="php"><?php
	// Get the keys of the static pages
	$staticPages = $dbPages->getStaticDB($onlyKeys=true);
	
	// Foreach page key, create the page and print the title
	foreach ($staticPages as $pageKey) {
		$page = buildPage($pageKey);
		
		echo $page->title();
	}
?></code></pre>

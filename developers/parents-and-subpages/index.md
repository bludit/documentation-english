# Title: Parents and Subpages
<!-- Position: 7 -->
---

This below functions are defined on `Bludit > v2.1`.

## Check if a page has subpages
<pre><code data-language="php"><?php
	// The variable $page is an object Page
	if ($page->hasSubpages())) {
		echo 'The page has subpages';
	} else {
		echo 'The page has not subpages';
	}
?></code></pre>

## List all subpages of a page
<pre><code data-language="php"><?php
        // The variable $page is an object Page
        $subpages = $page->subpages();
        if (empty($subpages)) {
                echo 'The page has not subpages';
        } else {
        	foreach ($subpages as $pageKey) {
			$subpage = buildPage($pageKey);
			echo 'Title of subpage ' . $subpage->title();
		}
        }
?></code></pre>


# Title: Parents and Subpages
<!-- Position: 7 -->
---

## Check if a page has subpages
<pre><code data-language="php"><?php
	// The variable $page is an object Page
	$children = $page->children();
	if (empty($children)) {
		echo 'The page has not subpages';
	} else {
		echo 'The page has subpages';
	}
?></code></pre>

## List all subpages of a page
<pre><code data-language="php"><?php
        // The variable $page is an object Page
        $children = $page->children();
        if (empty($children)) {
                echo 'The page has not subpages';
        } else {
        	foreach ($children as $pageKey) {
			$subpage = buildPage($pageKey);
			echo 'Title of subpage ' . $subpage->title();
		}
        }
?></code></pre>


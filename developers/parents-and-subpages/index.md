# Title: Parents and Subpages
<!-- Position: 7 -->
---
<div class="note">
The following codes work in Bludit > v2.1
</div>

## Check if a page has subpages
```
<?php
	// The variable $page is an Page-Object
	if ($page->hasSubpages())) {
		echo 'The page has subpages';
	} else {
		echo 'The page has not subpages';
	}
?>
```

## List all subpages of a page
```
<?php
        // The variable $page is an Page-Object
        $subpages = $page->subpages();
        if (empty($subpages)) {
                echo 'The page has not subpages';
        } else {
        	foreach ($subpages as $pageKey) {
			// buildPage function returns a Page-Object
			$subpage = buildPage($pageKey);

			echo 'Subpage title: ' . $subpage->title();
		}
        }
?>
```

## Check if a page is a subpage (has a parent)
```
<?php
        // The variable $page is an object Page
        if ($page->hasParent())) {
                echo 'The page is a subpage';
        } else {
                echo 'The page is not subpages';
        }
?>
```

## Print the title of parent page of a subpage
If a page has a subpage you can call the methods of the parent page with the method `parentMethod()`.
```
<?php
        // The variable $page is an object Page
        if ($page->hasParent())) {
                echo 'Title of the parent page: ' . $page->parentMethod('title');
        } else {
                echo 'The page is not subpages';
        }
?>
```


# Plugins and pages
<!-- position: 11 -->

Modify all the fields of the pages via plugins.

## Modify the content of the pages
The following code shows you how to modify the page content with a plugin.

```
<?php
class ModContent extends Plugin {

    // This hook is loaded when the pages are already set
    function beforeSiteLoad() {
        global $content;

        // Foreach loaded page, modify the page's content
        foreach ($content as $key=>$page) {
            // Get the page content
            $pageContent = $page->contentRaw();

            // Search and replace the string
            $newPageContent = str_replace("<!-- Dynamic -->", "Dynamic content", $pageContent);

            // Set the new page content
            $page->setField('content', $newPageContent);
        }
    }
}
?>
```

This plugin executes the `beforeSiteLoad` hook (which is executed before the users can see the content) then modifies the content by searching for the `<!-- Dynamic -->` string, and replacing it with the `Dynamic content` string.


## Modify the title of the pages
The following code shows how to modify the page title via a plugin.

```
<?php
class ModTitle extends Plugin {

    // This hook is loaded when the pages are already set
    function beforeSiteLoad() {
        global $content;

        // Foreach loaded page, modify the page's title
        foreach ($content as $key=>$page) {
            // Get the page title
            $title = $page->title();

            // Get the page creation date
            $date = $page->date();

            // Concatenate title and date
            $newTitle = $title.' '.$date;

            // Set the new title
            $page->setField('title', $newTitle);
        }
    }
}
?>
```

The plugin executes the `beforeSiteLoad` hook (which is executed before the users can see the content), then modifies the page title with the current title and the creation date.

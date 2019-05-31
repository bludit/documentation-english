# Plugins and pages
<!-- position: 11 -->

Modify all the fields of the pages from the plugins.

## Modify the content of the pages
The following code shows how to modify the page content from a plugin.

```
<?php
class ModContent extends Plugin {

    // This hooks is load when the pages are already setted
    function beforeSiteLoad() {
        global $content;

        // Foreach loaded page modified the page's content
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

The plugin execute the hook `beforeSiteLoad` which is executed before the users can see the content then modify the content searching the string `<!-- Dynamic -->` and replaced by the string `Dynamic content`.


## Modify the title of the pages
The following code shows how to modify the page title from a plugin.

```
<?php
class ModTitle extends Plugin {

    // This hooks is load when the pages are already setted
    function beforeSiteLoad() {
        global $content;

        // Foreach loaded page modified the page's title
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

The plugin executes the hook `beforeSiteLoad` which is executed before the users can see the content then modify the page title with the current title and the creation date.

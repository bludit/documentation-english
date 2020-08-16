# Predefined variables
<!-- position: 3 -->

Bludit provides a few predefined variables to help developers:

<h2 id="content">$content</h2>

The `$content` variable is an array with all published pages (it includes `pages` and `sticky`, but does not include `statics`). Each page included in the array is a [Page Object](https://github.com/bludit/bludit/blob/master/bl-kernel/pagex.class.php).

The array is ordered by `date` or by `position`, and you can change this behavior in the settings of your system.

Take a look at the code snippets to know how to work with this variable.
- https://docs.bludit.com/en/dev-snippets/content-pages

<h2 id="staticContent">$staticContent</h2>

The `$staticContent` variable is an array with all the `static` pages. Each page included in the array is a [Page Object](https://github.com/bludit/bludit/blob/master/bl-kernel/pagex.class.php).

The array is ordered by `position` by design.

Take a look at the code snippets to know how to work with this variable.
- https://docs.bludit.com/en/dev-snippets/content-static

<h2 id="page">$page</h2>

The `$page` variable represents whichever page the user is browsing. The variable is a [Page Object](https://github.com/bludit/bludit/blob/master/bl-kernel/pagex.class.php).

For example, if the user is browsing at `https://www.example.com/my-dog-rules`, the `$page` variable has the page object for the key, e.g. `my-dog-rules`.

<h2 id="pages">$pages</h2>

The `$pages` variable is a [Pages Object](https://github.com/bludit/bludit/blob/master/bl-kernel/pages.class.php). This object is used to manipulate the page database.

<h2 id="tags">$tags</h2>

The `$tags` variable is a [Tags Object](https://github.com/bludit/bludit/blob/master/bl-kernel/tags.class.php). This object is used to manipulate the tag database.

<h2 id="categories">$categories</h2>

The `$categories` variable is a [Categories Object](https://github.com/bludit/bludit/blob/master/bl-kernel/categories.class.php). This object is used to manipulate the category database.

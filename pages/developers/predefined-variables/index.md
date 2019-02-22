# Predefined variables
<!-- position: 3 -->

Bludit provides a few predefined variables to help developers.

<h2 id="content">$content</h2>

The variable `$content` is an array with all published pages (includes `pages` and `sticky` does not include `statics`). Each page included in the array is a [Page Object](https://github.com/bludit/bludit/blob/master/bl-kernel/pagex.class.php).

The array is ordered by `date` or by `position`, you can change this behavior in the settings of your system.

Take a look at the code snippets to know how to work with this variable.
- https://docs.bludit.com/en/dev-snippets/content-pages

<h2 id="staticContent">$staticContent</h2>

The variable `$staticContent` is an array with all the `static` pages. Each page included in the array is a [Page Object](https://github.com/bludit/bludit/blob/master/bl-kernel/pagex.class.php).

The array is ordered by `position` by design.

Take a look at the code snippets to know how to work with this variable.
- https://docs.bludit.com/en/dev-snippets/content-static

<h2 id="page">$page</h2>

The variable `$page` has the current page if the user is browsing one of them. The variables is a [Page Object](https://github.com/bludit/bludit/blob/master/bl-kernel/pagex.class.php).

For example, if the user is browsing the page `https://www.example.com/my-dog-rules` the variable `$page` has the page object for the key `my-dog-rules`.

<h2 id="pages">$pages</h2>

The variable `$pages` is a [Pages Object](https://github.com/bludit/bludit/blob/master/bl-kernel/pages.class.php). This object is to manipulate the page database.

<h2 id="tags">$tags</h2>

The variable `$tags` is a [Tags Object](https://github.com/bludit/bludit/blob/master/bl-kernel/tags.class.php). This object is to manipulate the tag database.

<h2 id="categories">$categories</h2>

The variable `$categories` is a [Categories Object](https://github.com/bludit/bludit/blob/master/bl-kernel/categories.class.php). This object is to manipulate the category database.

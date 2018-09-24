# Predefined variables
<!-- position: 3 -->

Bludit provides a few predefined variables to help to developers.

<h2 id="content">$content</h2>

The variable `$content` is an array with all published pages (includes `pages` and `sticky` does not include `statics`). Each page included in the array is a [Page Object](https://github.com/bludit/bludit/blob/master/bl-kernel/pagex.class.php).

The array is ordered by `date` or by `position`, you can change this behavior in the settings of your system.

Take a look at the code snippets to know who to work with this variable.
- https://docs.bludit.com/en/dev-snippets/content-pages

<h2 id="page">$page</h2>

The variable `$page` has the current page when the user is browsing one of the them. The variables is a [Page Object](https://github.com/bludit/bludit/blob/master/bl-kernel/pagex.class.php).

To be more clear, if the user is browsing the page `https://www.example.com/my-dog-rules` the current page is `my-dog-rules` so in the variable you are going to have that page.

<h2 id="staticContent">$staticContent</h2>

The variable `$staticContent` is an array with all `statics` pages. Each page included in the array is a [Page Object](https://github.com/bludit/bludit/blob/master/bl-kernel/pagex.class.php).

The array is ordered by `position` all the time.

Take a look at the code snippets to know who to work with this variable.
- https://docs.bludit.com/en/dev-snippets/content-static
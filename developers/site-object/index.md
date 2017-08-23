# Title: Site Object
<!-- Position: 2 -->
---

The object `$Site` has all the information from the database `/bl-content/databases/site.php`

## Methods and examples of usage

### URL filters
The returned values are the default, the user can change it.

<pre><code data-language="php"># Get the admin filter
$Site->uriFilters('admin'); # returns /admin/

#Get the post filter
$Site->uriFilters('post'); # returns /post/

#Get the page filter
$Site->uriFilters('page'); # returns /

#Get the tag filter
$Site->uriFilters('tag'); # returns /tag/

#Get the blog filter
$Site->uriFilters('blog'); # returns /blog/
</code></pre>

### Print the site title
<pre><code data-language="php">echo $Site->title();</code></pre>

### Print the site slogan
<pre><code data-language="php">echo $Site->slogan();</code></pre>

### Print the site description
<pre><code data-language="php">echo $Site->description();</code></pre>

### Print the footer text
<pre><code data-language="php">echo $Site->footer();</code></pre>

### Get the current theme for the site
<pre><code data-language="php">$theme = $Site->theme();</code></pre>

### Get the current theme for the admin panel
<pre><code data-language="php">$theme = $Site->adminTheme();</code></pre>

### Get the defined timezone
<pre><code data-language="php">echo $Site->timezone();</code></pre>

### Get the defined language
<pre><code data-language="php">echo $Site->language();</code></pre>

### Get the defined locale
<pre><code data-language="php">echo $Site->locale();</code></pre>

### Get the defined homepage
<pre><code data-language="php">echo $Site->homepage();</code></pre>

### Get the number of posts to show on one page
<pre><code data-language="php">echo $Site->postsPerPage();</code></pre>

### Get the current build of Bludit
<pre><code data-language="php">echo $Site->currentBuild();</code></pre>
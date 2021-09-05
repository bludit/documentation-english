# Structure of directories and files
<!-- position: 2 -->

## First layer of directories
```
/bl-content/    <-- Databases and images
/bl-kernel/     <-- Bludit's core
/bl-languages/  <-- Languages files for Bludit's core
/bl-plugins/    <-- Plugins
/bl-themes/	    <-- Themes
```

## bl-content
This directory is very important, as it is where Bludit store all the files, databases and images.

Before updating Bludit, it's highly recommended to make a backup of this directory.

```
/bl-content/

    databases/
        plugins/        <-- Database: plugins
        pages.php       <-- Database: pages
        security.php    <-- Database: black list, brute force protection, others
        site.php		<-- Database: site variables, name, description, slogan, others
        tags.php		<-- Database: tags
        users.php		<-- Database: users

    pages/
        about/index.txt <-- Page "about", the url match with the directory path, https://mydomain/about
        food/index.txt

    tmp/				<-- Temp files

    uploads/			<-- Uploaded files
        profiles/		<-- Profiles images
        pages/about/    <-- Files and images for the page "about"

    workspaces/			<-- Workspaces for the plugins
```

## bl-kernel
This directory contains the core of Bludit.

## bl-languages
This directory contains all language files. Each file is a JSON document, encoded in UTF-8.

```
/bl-languages/
    bg_BG.json
    cs_CZ.json
    de_CH.json
    en.json
    es.json
    ...
```

## bl-plugins
This directory contains all plugins. New plugins you download should be uploaded here.

```
/bl-plugins/
    about/
    disqus/
    rss/
    sitemap/
    tinymce/
    ...
```

## bl-themes
This directory contains all themes. New themes you download should be uploaded here.

```
/bl-themes/
    alternative/
    blogx/
    ...
```

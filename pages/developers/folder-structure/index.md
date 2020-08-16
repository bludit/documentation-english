# Folder structure
<!-- position: 2 -->

Here's the basic folder structure for Bludit.
```
/bl-content/	<-- Databases and uploaded images
/bl-kernel/		<-- Core of Bludit
/bl-languages/	<-- Languages files
/bl-plugins/	<-- Plugins
/bl-themes/		<-- Themes
```

## bl-content
This folder is very important, as it is where Bludit stores all files, as well as databases and images. Before updating your Bludit installation, it's highly recommended to make a backup of this folder.

```
/bl-content/

	databases/
		plugins/		<-- Database: plugins
		pages.php		<-- Database: pages
		security.php	<-- Database: black list, brute force protection, others
		site.php		<-- Database: site variables, name, description, slogan, others
		tags.php		<-- Database: tags
		users.php		<-- Database: users

	pages/				<-- Content: pages
		about/index.txt
		food/index.txt

	tmp/				<-- Temp files

	uploads/			<-- Uploaded files
		profiles/		<-- Profiles images
		thumbnails/		<-- Thumbnails images
		photo1.jpg
		photo2.png

	workspaces/			<-- Workspaces for the plugins
```

## bl-kernel
This folder contains the core of Bludit.

## bl-languages
This folder contains all language files. Each file is a JSON document, encoded in UTF-8.

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
This folder contains all plugins. New plugins you download should be uploaded here.

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
This folder contains all themes. New themes you download should be uploaded here.

```
/bl-themes/
	alternative/
	blogx/
	...
```

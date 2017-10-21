# Title: Folder structure
<!-- Position: 1 -->
---
This is the folder structure of Bludit.

```
bl-content/
bl-kernel/
bl-languages/
bl-plugins/
bl-themes/
```

## bl-content
This folder is very important, it is where Bludit stores all files, as well as databases and images. Before making some update it's highly recommended to make a backup of this folder.

```
bl-content/

	databases/
		plugins/		<-- Database: plugins
		pages.php		<-- Database: pages
		security.php		<-- Database: black list, brute force protection, others
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
```

## bl-kernel
This folder contains the core of Bludit.

## bl-languages
This folder contains all language files, each file is a JSON document, encoded in UTF-8.

```
bl-languages/
	bg_BG.json
	cs_CZ.json
	de_CH.json
	en.json
	es.json
	...
```

## bl-plugins
This folder contains all plugins, you can download new plugins and upload here.

```
bl-plugins/
	about/
	disqus/
	rss/
	sitemap/
	simplemde/
	...
```

## bl-themes
This folder contains all themes, you can download new themes and upload here.

```
bl-themes/
	clean-blog/
	kernel-panic/
	...
```

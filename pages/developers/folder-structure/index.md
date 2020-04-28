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

##How to import multiple pages into Bludit

###Overview

1. create a folder for each page
2. move each page into its respective folder and rename each page to index.txt
3. update ./bl-content/databases/pages.php

### Create a folder for each page
1. This will depend on what your source files look like. In the worst example, here is exporting from a different CMS where the data was in a MySQL database. Using sql, extract two text files. The first is the title of each page (called products in the script below). The second is the content, called productdescriptions. Each title or page from the old CMS is represented as a row in the two text files. Below is a short python script to convert the rows to pages
```#!/usr/bin/env python3
n=1
nstr="1"
nfpath="~/Documents/projects/python/newproducts"+nstr
nf=open(nfpath+".txt",'w')
f=open('~/Documents/projects/python/productdescriptions.txt')
line=f.readline()
while line:
	if line[0:2].isdigit():
		nf.close()
		n=n+1
		nstr=str(n)
		nfpath='~/Documents/projects/python/newproducts' + nstr
		nf=open(nfpath+".txt",'w')
	nf.write(line)
	line=f.readline()
f.close()
nf.close()
```

All the files need to be renamed to the name of the products. The name of the product was in the first line of each page, so could be extracted using the script below, limiting the name length to 20 characters.
```#!/usr/bin/env python3
n=2
x=1
nstr="2"
while n<78:
	fpath="~/Documents/projects/python/newproducts"+nstr
	f=open(fpath+".txt",'r')
	line=f.readline()
	tmpline=line[5:]
	newname=''.join(e for e in tmpline if e.isalnum())
	if len(newname)>20:	newname=newname[:20]
	nfpath="~/Documents/projects/python/"+newname+".html"
	nf=open(nfpath,'w')
	while line:
		nf.write(line)
		line=f.readline()
	f.close()
	nf.close()
	n=n+1
	nstr=str(n)
```
The file names may need to be up with a bulk file renaming tool (e.g. GPRename) to remove blank spaces, caps, etc.

2. Make a directory listing of the pages into a text file (ls>dir.txt) and open the dir.txt file in a spreadsheet. 
Column A as the file names
Column B as the product name: ```=LEFT(A2,FIND(".",A2)-1)```
Column C as the command for making a directory: ```="mkdir "&B2```
Column D as the command for moving the pages to their respective directories: ```="mv ./"&A2&" ./"&B2&"/"```
Column E as the command to rename the pages:``` ="mv ./"&B2&"/"&A2&" ./"&B2&"/index.txt"```

Create a blank text file
on the first line, put:  #!/bin/sh
copy and paste column B after that 
repeat the copying and pasting for columns C, D & E
save the file and made it executable: ```chmod u+x ./filename```
run the file
The filestructure is now correct and can be moved to the directory bludit/bl-content/pages/

3. Using the same spreadsheet in 2, Column F gave the database entry: ```="'"&B2&"':{'title':'"&B2&"','description':'"&B2&"','username':'admin','tags':[],'type':'static','date':'2020-04-24 14:43:37','datemodified':'','allowcomments':true,'position':1,'coverimage':'','md5file':'','category':'general','uuid':'','parent':'','template':'','noindex':false,'nofollow':false,'noarchive':false},"```
Copy all the columns into a text file and replace the single quotes with double quotes (i.e. change ' to ")
Open bl-content/database/pages.php
The file ends with :false}}
Between the second-last brace and the last brace, copy and paste the text from the text file, taking care to remove the comma off the last entry between the final two braces. Although the file is a single line when you open it, Bludit does not mind if there are linebreaks between each entry.

4. Now when you open your Bludit admin page and look under Content, you'll see the pages under Static.


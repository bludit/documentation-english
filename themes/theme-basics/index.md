# Title: Theme basics
<!-- Position: 1 -->
---
Themes in Bludit are very flexible, you can use any framework ([Bootstrap](http://getbootstrap.com/), [Kube](http://imperavi.com/kube/), [Pure.io](purecss.io), [Skel](https://github.com/n33/skel), [Less](http://lesscss.org/), etc), any Javascript code, whatever you want.

All themes resides into `bl-themes` folder, and they have a pre-defined structure.

### Content
1. [Themes structure](#structure)
2. [Information about the theme](#information)
3. [Name and description](#name-description)

---

## <a id="structure"></a> Theme structure
This is a simple mandatory folder structure and files for themes.
```
/bl-themes/{THEME_NAME}/
	language/en.json
	metadata.json
	index.php
```

## <a id="information"></a> Information about the theme
The information of the theme is in the JSON file `metadata.json`.
<pre><code data-language="JSON">{
	"author": "Bludit",
	"email": "",
	"website": "https://themes.bludit.com",
	"version": "2.0",
	"releaseDate": "2017-10-10",
	"license": "MIT",
	"compatible": "2.0",
	"notes": ""
}</code></pre>

## <i id="name-description"></i> Name and description
The name and description of the theme is in the JSON file `languages/en.json`.
<pre><code data-language="JSON">{
	"theme-data":
	{
		"name": "Hello World",
		"description": "My new theme"
	}
}</code></pre>

<div class="note">
<div class="title">Examples</div>
We have a Github repository with examples, take a look at <a href="https://github.com/bludit/examples">Bludit Examples</a>.
</div>
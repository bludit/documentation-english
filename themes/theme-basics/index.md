# Title: Theme basics
<!-- Position: 1 -->
---
Themes in Bludit are very flexible, you can use any framework ([Bootstrap](http://getbootstrap.com/), [Kube](http://imperavi.com/kube/), [Pure.io](purecss.io), [Skel](https://github.com/n33/skel), [Less](http://lesscss.org/), etc), any Javascript code, whatever you want.

All themes resides into `bl-themes` folder, and they have a pre-defined structure.

### Content
1. [Themes structure](#structure)
2. [Information about the theme](#information)

---

## <a id="structure"></a> Theme structure
This is a simple mandatory folder structure and files for themes.
```
/bl-themes/<THEME_NAME>/
	language/en.json
	metadata.json
	index.php
```

## <a id="information"></a> Information about the theme
Each theme has an information file `metadata.json`.
```
{
	"author": "Bludit",
	"email": "",
	"website": "https://themes.bludit.com",
	"version": "2.0",
	"releaseDate": "2017-10-10",
	"license": "MIT",
	"compatible": "2.0",
	"notes": ""
}
```

The theme **name** and **description** are in the language file `languages/en.json`.
```
{
	"theme-data":
	{
		"name": "Hello World",
		"description": "My new theme"
	}
}
```
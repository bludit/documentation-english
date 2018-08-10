# Title: Theme basics
<!-- Position: 1 -->
---
Themes in Bludit are very flexible, you can use any framework ([Bootstrap](http://getbootstrap.com/), [Foundation](https://foundation.zurb.com/), [Bulma](https://bulma.io), [UIkit](https://getuikit.com/), [Semantic UI](https://semantic-ui.com), etc), any Javascript code, whatever you want.

All themes resides into `bl-themes` folder, and they have a pre-defined structure.

<h2 id="structure">Folder and Files Structure</h2>
This is a simple mandatory folder structure and files for themes.

```
/bl-themes/{THEME_NAME}/
	languages/en.json
	metadata.json
	index.php
```

<h2 id="name-description">Name and Description</h2>
The name and description of the theme is in the JSON file `languages/en.json`.

```
{
	"theme-data":
	{
		"name": "Hello World",
		"description": "My new theme"
	}
}
```

<h2 id="information">Information</h2>
The information of the theme is in the JSON file `metadata.json`.

```
{
	"author": "Bludit",
	"email": "",
	"website": "https://themes.bludit.com",
	"version": "1.0",
	"releaseDate": "2018-08-01",
	"license": "MIT",
	"compatible": "3.0",
	"notes": ""
}
```

<h2 id="examples">Examples</h2>
We have two examples, one is simple and the second is more complex with CSS and Javascript files.

- [My First Theme](https://docs.bludit.com/en/themes/example-my-first-theme)
- [My Second Theme](https://docs.bludit.com/en/themes/example-my-second-theme)

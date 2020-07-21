# Theme basics
<!-- position: 1 -->

Themes in Bludit are very flexible, and you can use any framework ([Bootstrap](http://getbootstrap.com/), [Foundation](https://foundation.zurb.com/), [Bulma](https://bulma.io), [UIkit](https://getuikit.com/), [Semantic UI](https://semantic-ui.com), etc), any Javascript code, whatever you want.

All themes reside in the `bl-themes` folder, and they have a predefined structure.

<h2 id="structure">Folder and Files Structure</h2>
This is the simple (and mandatory) folder and file structure for themes.

```
/bl-themes/{THEME_NAME}/
	languages/en.json
	metadata.json
	index.php
```

<h2 id="name-description">Name and Description</h2>
The name and description of the theme is stored in the `languages/en.json` JSON file.

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
The basic information about the theme is stored in the `metadata.json` JSON file.

```
{
	"author": "Bludit",
	"email": "",
	"website": "https://themes.bludit.com",
	"version": "1.0",
	"releaseDate": "2020-06-01",
	"license": "MIT",
	"compatible": "3.0",
	"notes": ""
}
```

<h2 id="examples">Example Themes</h2>
We have two examples, one is simple and the second is more complex with CSS and Javascript files.

- [My First Theme](https://docs.bludit.com/en/themes/example-my-first-theme)
- [My Second Theme](https://docs.bludit.com/en/themes/example-my-second-theme)

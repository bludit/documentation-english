# Translate a theme
<!-- position: 2 -->

Each theme has a folder `languages`, inside this folder you can create the different dictionaries files for each language.

```
/bl-themes/{THEME_NAME}/languages/
	de_DE.json
	en.json
	es.json
	fr_FR.json
	...
```

<div class="note">
<div class="title">File Encoding</div>
All dictionary files are <b>JSON</b> files, and are encoded in <b>UTF-8</b>.
</div>
<div class="note">
<div class="title">File Naming</div>
Be careful with the name of your language files. You have to name the language file of your theme the same way as the main language file in the bt-languages folder (for example: for french translation, 'fr_FR.json' and not 'fr.json', but for english 'en.json')
</div>

This is an example of an English dictionary file (`en.json`). Each line in the `en.json` file is a key-value pair, with the key on the left and the value on the right.

```
{
	"theme-data":
	{
		"name": "Pure",
		"description": "Simple and clean, based on the framework Pure.css."
	}
}
```

As you can see, you have a field called `theme-data`, this has the name and description of the theme.

This is an example of a Spanish dictionary; the file is located in `/bl-themes/{THEME_NAME}/languages/es.json`.

```
{
	"theme-data":
	{
		"name": "Pure",
		"description": "Simple y minimalista, basado en el framework Pure.css."
	}
}
```

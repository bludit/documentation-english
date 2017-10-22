# Title: Translate a theme
<!-- Position: 2 -->
---
Each theme has a folder `languages`, inside this folder you have the different dictionaries files for each language.

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
All dictionary files are <b>JSON</b> files and are encoding on <b>UTF-8</b>.
</div>

---

This is an example of an English dictionary `en.json`. Each line in en.json file is a key-value pair with the key on the left and the value on the right.

<pre><code data-language="JSON">{
	"theme-data":
	{
		"name": "Pure",
		"description": "Simple and clean, based on the framework Pure.css."
	}
}</code></pre>

As you can see, you have a field called `theme-data`, this has the name and description of the theme.

This is an example of a Spanish dictionary, the file is `es.json`.

<pre><code data-language="JSON">{
	"theme-data":
	{
		"name": "Pure",
		"description": "Simple y minimalista, basado en el framework Pure.css."
	}
}</code></pre>

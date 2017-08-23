# Title: Translate a theme
<!-- Position: 2 -->
---
Each theme has a folder called `languages`, inside this folder you have the different dictionary files for each language.

```
/bl-themes/{THEME_NAME}/languages/
	de_DE.json
	en_US.json
	es_AR.json
	fr_FR.json
	...
```

<div markdown="1" class="note">
<div class="note-title">NOTE</div>
The default language in Bludit is the English from United States, the locale name is **en_US**, and the filename is **en_US.json**.
</div>

<div markdown="1" class="note">
<div class="note-title">NOTE</div>
All dictionary files are **JSON** files, and are saved by the encoding **UTF-8**.
</div>

---

This is an example of an English (United States) dictionary `en_US.json`. Each line in en_US.json file is a key-value pair with the key on the left and the value on the right.

<pre><code data-language="JSON">{
	"theme-data":
	{
		"name": "Pure",
		"description": "Simple and clean, based on the framework Pure.css."
	}
}
</code></pre>

As you can see, you have a field called `theme-data`, this has the name and description of the theme.

This is an example of a Spanish (Argentina) dictionary, the locale name is `es_AR` then the filename will be `es_AR.json`.

<pre><code data-language="JSON">{
	"theme-data":
	{
		"name": "Pure",
		"description": "Simple y minimalista, basado en el framework Pure.css."
	}
}
</code></pre>

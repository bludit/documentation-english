# Title: Translate a plugins
<!-- Position: 1 -->
---
Each plugin has a folder called `languages`, in this folder you have the different dictionary files for each language.

```
/bl-plugins/{PLUGIN_NAME}/languages/
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

<pre><code data-language="JSON"> {
	"plugin-data":
	{
		"name": "Page list",
		"description": "Shows the list of pages in order."
	},

	"home": "Home",
	"show-home-link": "Show home link"
}
</code></pre>

As you can see, you have a field called `plugin-data`, this has the name and description of the plugin, and the next fields are phrases for the plugin as `home` and `show-home-link`.

<div markdown="1" class="note">
<div class="note-title">IMPORTANT !</div>
You don't need to translate the following fields: author, email, website, version and releaseDate because Bludit takes this information from the English dictionary.
</div>

This is an example of a Spanish (Argentina) dictionary, the locale name is `es_AR` then the filename will be `es_AR.json`.

<pre><code data-language="JSON"> {
	"plugin-data":
	{
		"name": "Listado de paginas",
		"description": "Muestra el listado de paginas en orden."
	},

    "home": "Inicio",
    "show-home-link": "Mostrar link de la pagina de incio"
}
</code></pre>

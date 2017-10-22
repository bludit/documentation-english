# Title: Plugin basics
<!-- Position: 1 -->
---
Plugins in Bludit resides into `bl-plugins` folder, and they have a pre-defined structure. Each plugin is an object in Bludit, with differents hooks (methods).

### Content
1. [Hello World](#hello-world)
2. [Plugin structure](#structure)
3. [Information about the theme](#information)
4. [Name and description](#name-description)

---

## <i id="hello-world"></i> Hello World
The Hello World plugin for Bludit.
<pre><code data-language="php"><?php
	class pluginHello extends Plugin {
		public function siteSidebar() {
			echo 'Hello world';
		}
	}
?></code></pre>

## <i id="structure"></i> Plugins structure
This is a mandatory folder structure and files for a plugin.
```
/bl-plugins/{PLUGIN_NAME}/
	language/en.php
	metadata.json
	plugin.php
```

## <i id="information"></i> Information about the plugin
The information of the plugin is in the JSON file `metadata.json`.
<pre><code data-language="JSON">{
	"author": "Bludit",
	"email": "",
	"website": "https://plugins.bludit.com",
	"version": "2.0",
	"releaseDate": "2017-10-10",
	"license": "MIT",
	"compatible": "2.0",
	"notes": ""
}</code></pre>

## <i id="name-description"></i> Name and description
The name and description of the plugin is in the JSON file `languages/en.json`.
<pre><code data-language="JSON">{
	"plugin-data":
	{
		"name": "Hello World",
		"description": "Print Hello World in the sidebar"
	}
}</code></pre>

<div class="note">
<div class="title">Examples</div>
We have a Github repository with examples, take a look at <a href="https://github.com/bludit/examples">Bludit Examples</a>.
</div>
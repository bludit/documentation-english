# Title: Plugin basics
<!-- Position: 1 -->
---
Plugins in Bludit resides into `bl-plugins` folder, and they have a default structure. Each plugin is an object in Bludit, with differents hooks (methods).

### Content
1. [Hello World](#hello-world)
2. [Plugin structure](#structure)
3. [Information about the theme](#information)

---

## <i id="hello-world"></i> Hello World
The Hello World of the Bludit plugins.
```
<?php
	class pluginHello extends Plugin {
		public function siteSidebar() {
			echo 'Hello world';
		}
	}
?>
```

## <i id="structure"></i> Plugins structure
This is a mandatory folder structure and files for a plugin.
```
/bl-plugins/{PLUGIN_NAME}/
	language/en_US.php
	metadata.json
	plugin.php
```

## <i id="information"></i> Information about the plugin
Each plugin has an information file `metadata.json`.
```
{
	"author": "Bludit",
	"email": "",
	"website": "https://plugins.bludit.com",
	"version": "2.0",
	"releaseDate": "2017-10-10",
	"license": "MIT",
	"compatible": "2.0",
	"notes": ""
}
```

The plugin **name** and **description** are in the language file `languages/en_US.json`.
```
{
	"plugin-data":
	{
		"name": "Hello World",
		"description": "Print Hello World in the sidebar"
	}
}
```

<div markdown="1" class="note">
<div class="note-title">NOTE</div>
The default language in Bludit is the English from United States, the locale name is **en_US**, and the filename is **en_US.json**.
</div>
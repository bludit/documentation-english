# Plugin basics
<!-- position: 1 -->

Plugins in Bludit reside in the `bl-plugins` folder, and they have a predefined structure. Each plugin is an object in Bludit, with differents hooks (methods).

<h2 id="structure">Folder and Files Structure</h2>
These are the mandatory folder structure and files for a plugin:

```
/bl-plugins/{PLUGIN_NAME}/
	languages/en.json
	metadata.json
	plugin.php
```

<h2 id="name-and-description">Name and Description</h2>
The name and description of the plugin is located in the JSON file, `languages/en.json`.

```
{
	"plugin-data":
	{
		"name": "Hello World",
		"description": "Print Hello World in the sidebar"
	}
}
```

<h2 id="information">Information</h2>
The meta information of the plugin is located in the JSON file, `metadata.json`.

```
{
	"author": "Bludit",
	"email": "",
	"website": "https://plugins.bludit.com",
	"version": "1.0",
	"releaseDate": "2018-08-01",
	"license": "MIT",
	"compatible": "3.0",
	"notes": ""
}
```

<h2 id="hello-world">Hello World</h2>
The Hello World plugin for Bludit. The code below needs to be in the `plugin.php` file.

```
<?php
	class pluginHello extends Plugin {
		public function siteSidebar() {
			echo 'Hello world';
		}
	}
?>
```

<div class="note">
<div class="title">Download</div>
Download the source code of the plugin <a href="https://github.com/bludit/examples/tree/master/plugins/hello-world">Hello World</a>.
</div>

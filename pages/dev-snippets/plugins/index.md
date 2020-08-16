# Plugins
<!-- position: 10 -->

Snippets to help you work with plugins:

## Activate plugin

```
<?php
	// Class name of the plugin
	$className = 'pluginAbout';

	activatePlugin($className);
?>
```

## Deactivate plugin

```
<?php
	// Class name of the plugin
	$className = 'pluginAbout';

	deactivatePlugin($className);
?>
```

## Check if a plugin is activated (enabled)

```
<?php
	// Class name of the plugin
	$className = 'pluginAbout';

	if (pluginActivated($className)) {
		echo 'The plugin About is activated';
	} else {
		echo 'The plugin About is deactivated';
	}
?>
```

## Get a plugin
This function returns a [Plugin-Object](https://github.com/bludit/bludit/blob/master/bl-kernel/abstract/plugin.class.php).

The plugin needs to be activated, otherwise the `getPlugin()` function returns `false`.

```
<?php
	// Class name of the plugin
	$className = 'pluginAbout';

	// Get the Plugin-Object
	$plugin = getPlugin($className);

	// Print the plugin label
	echo $plugin->label();

	// Execute the hook siteSidebar of the plugin and print it
	echo $plugin->siteSidebar();
?>
```

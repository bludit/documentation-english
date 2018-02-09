# Title: Plugins
<<<<<<< HEAD
<!-- Position: 8 -->
---
Snippet code to work with plugins.
=======
<!-- Position: 10 -->
---
Snippet codes to work with plugins.
>>>>>>> 1d536cfe4c36293392de653643cd548e52352009

<div class="note">
The following codes work in Bludit > v2.1
</div>

<<<<<<< HEAD
## List all plugins installed
```
<?php

?>
```

## Check if a plugin is installed
```
<?php

?>
```

## Activate a plugin
```
<?php

?>
```

## Deactivate a plugin
```
<?php

?>
```
=======
## Check if a plugin is activated / enabled
```
<?php
	// Class name of the plugin
	$className = 'pluginRSS';

	if (pluginActivated($className)) {
		echo 'The plugin RSS is activated';
	}
?>
```

## Get a plugin
The function returns a Plugin-Object
```
<?php
	// Class name of the plugin
	$className = 'pluginRSS';

	// Get the Plugin-Object
	$plugin = getPlugin($className);

	// Print the plugin label
	echo $plugin->label();
?>
```

## Activate plugin
```
<?php
	// Class name of the plugin
	$className = 'pluginRSS';

	activatePlugin($className);
?>
```

## Deactivate plugin
```
<?php
	// Class name of the plugin
	$className = 'pluginRSS';

	deactivatePlugin($className);
?>
```

>>>>>>> 1d536cfe4c36293392de653643cd548e52352009

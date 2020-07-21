# Custom hooks for plugins
<!-- position: 4 -->

Bludit supports custom hooks for the plugin, you can create your own hook and call it from anywhere.

<div class="note">
This feature is implemented since Bludit v3.13
</div>

## Example
The following example creates two custom hooks `select` and `insert`.

To make it work remember to add the hooks (object methods) inside the array `$this->customHooks` inside the method `init()`.

```php
<?php

class MyHooks extends Plugin {

	public function init()
	{
        $this->customHooks = array(
            'select',
            'insert'
        );
	}

	public function select()
	{
		echo 'Custom hook select';
	}

	public function insert()
	{
		echo 'Custom hook insert';
	}
}

?>
```

After the plugin is activated you can call the custom hooks via the helper `Theme::plugins` as you do in the themes.

```php
<?php
	...
	Theme::plugins('select');
	...
	Theme::plugins('insert');
?>
```
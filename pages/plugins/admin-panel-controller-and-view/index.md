# Admin panel: Controller and View via plugins
<!-- position: 3 -->

Bludit provides an easy way to create a controller and view for the admin panel via plugins.

<div class="note">
This feature is implemented since Bludit v3.13
</div>

## Notes
- Bludit by default use [Bootstrap](https://getbootstrap.com/) for the styling, you can use it in the admin view.
- The endpoint to reach the admin view is `/admin/plugin/<plugin-name>`

## Example: Hello world!
The following plugin changes the metadata `<title>` and the view returns a simple `Hello world!`.

After activate the plugin you can reach the view `https://www.example.com/admin/plugin/hello`.

```php
<?php

class Hello extends Plugin {

	public function adminController()
	{
		global $layout;
		$layout["title"] = "Hello Plugin | Bludit";
	}

	public function adminView()
	{
		return 'Hello world!';
	}

	public function adminSidebar()
	{
		$pluginName = Text::lowercase(__CLASS__);
		$url = HTML_PATH_ADMIN_ROOT.'plugin/'.$pluginName;
		$html = '<a id="current-version" class="nav-link" href="'.$url.'">Hello world</a>';
		return $html;
	}
}
?>
```

## Example: Change settings via form
The following plugin has the ability to change the settings of Bludit. The view shows a form and the controller manages the `POST` method.

After activate the plugin you can reach the view from here `https://www.example.com/admin/plugin/settings`

```php
<?php

class CustomAdmin extends Plugin {

	public function adminController()
	{
		// Check if the form was sent
		if ($_SERVER['REQUEST_METHOD'] == 'POST') {
			global $site;
			$site->set(array('title'=>$_POST['title']));
		}
	}

	public function adminView()
	{
		// Token for send forms in Bludit
		global $security;
		$tokenCSRF = $security->getTokenCSRF();

		// Current site title
		global $site;
		$title = $site->title();

		// HTML code for the form
		$html = '
			<h2>Settings</h2>
			<form method="post">
			<input type="hidden" id="jstokenCSRF" name="tokenCSRF" value="'.$tokenCSRF.'">
			<div class="form-group">
				<label for="title">Site title</label>
				<input type="text" class="form-control" id="title" name="title" value="'.$title.'">
			</div>
			<button type="submit" class="btn btn-primary">Submit</button>
			</form>
		';
		return $html;
	}

	public function adminSidebar()
	{
		$pluginName = Text::lowercase(__CLASS__);
		$url = HTML_PATH_ADMIN_ROOT.'plugin/'.$pluginName;
		$html = '<a id="current-version" class="nav-link" href="'.$url.'">Custom Admin Form</a>';
		return $html;
	}
}
```

You can download the full example plugin from here:
- https://github.com/bludit/examples/tree/master/plugins/custom-controller-view-admin-panel

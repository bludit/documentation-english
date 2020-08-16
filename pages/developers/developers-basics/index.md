# Developer basics
<!-- position: 1 -->

Let's start by checking environment variables from your current installation. Go to your admin panel to the developer's area, located at `https://www.example.com/admin/developers`; this section is hidden from the menu.

You can see some information about your PHP configuration, environment variables such as `$_SERVER`, the extensions you have loaded, locales you have installed, Bludit constants, and some Objects properties.

## Flow of loading files for admin panel
These are the files loaded when a user goes to the admin panel:

```
index.php
	bl-kernel/boot/init.php
	bl-kernel/boot/admin.php
		bl-kernel/boot/rules/60.plugins.php
		bl-kernel/boot/rules/69.pages.php
		bl-kernel/boot/rules/99.header.php
		bl-kernel/boot/rules/99.paginator.php
		bl-kernel/boot/rules/99.themes.php
		bl-kernel/boot/rules/99.security.php
		bl-kernel/admin/themes/default/init.php
		bl-kernel/admin/controllers/{CONTROLLER}.php
		bl-kernel/admin/themes/default/index.php
			bl-kernel/admin/controllers/{VIEW}.php
```

## Flow of loading files for site
These are the files loaded when a user goes to the site:

```
index.php
	bl-kernel/boot/init.php
	bl-kernel/boot/site.php
		bl-kernel/boot/rules/60.plugins.php
		bl-kernel/boot/rules/69.pages.php
		bl-kernel/boot/rules/99.header.php
		bl-kernel/boot/rules/99.paginator.php
		bl-kernel/boot/rules/99.themes.php
		bl-kernel/boot/rules/99.security.php
		bl-themes/{THEME_NAME}/init.php
		bl-themes/{THEME_NAME}/index.php
```

## Environment variables and constants
Bludit provides different environment variables and constants with predefined configurations.

- [bl-kernel/boot/init.php](https://github.com/bludit/bludit/blob/master/bl-kernel/boot/init.php)
- [bl-kernel/boot/variables.php](https://github.com/bludit/bludit/blob/master/bl-kernel/boot/variables.php)

Another place where you can see environment variables defined is in the rules folder: `bl-kernel/boot/rules/`. For example, the variables about `content` and `pages` are defined in [bl-kernel/boot/rules/69.pages.php](https://github.com/bludit/bludit/blob/master/bl-kernel/boot/rules/69.pages.php).

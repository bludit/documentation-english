# Title: Helper for create themes
<!-- Position: 100 -->
---
This object is a Helper, this try to help developers to make code more clean and less code to write.

This object has static methods (see the colon when call the methods).

### Methods and examples of usage

Include title on HTML <head> tag
```
<!DOCTYPE html>
<html>
<head>
	<?php $Theme::title('Hello world') ?>
</head>
<body>
	<p>My Page</p>
</body>
</html>
```

Include CSS files. This method includes the files from the directory `/bludit/themes/{theme name}/css/`.
```
<!DOCTYPE html>
<html>
<head>
	<title>Hello world</title>
	<?php $Theme::css(array(('default.css', 'other.css'))) ?>
</head>
<body>
	<p>My Page</p>
</body>
</html>
```

Include Javascript files. This method includes the files from the directory `/bludit/themes/{theme name}/js/`.
```
<!DOCTYPE html>
<html>
<head>
	<title>Hello world</title>
	<?php $Theme::javascript(array(('functions.js', 'other.js'))) ?>
</head>
<body>
	<p>My Page</p>
</body>
</html>
```

Include charset, viewport, title, and description.
```
<!DOCTYPE html>
<html>
<head>
<?php
	Theme::charset('UTF-8');
	Theme::viewport();
	Theme::title('Hello world');
	Theme::description('My little description');
?>
</head>
<body>
	<p>My Page</p>
</body>
</html>
```
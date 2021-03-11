# Include frameworks (Bootstrap, Icons and jQuery)
<!-- position: 7 -->

Themes in Bludit are very flexible; you can use any framework (Bootstrap, Foundation, Bulma, UIkit, Semantic UI, etc), any Javascript code, whatever you want.

Bludit includes Boostrap, Boostrap Icons and jQuery by default and you can use it in your themes.

<h2 id="jquery">Include jQuery</h2>

Bludit keeps the latest version of jQuery in its package, you can include it with the HTML helper.
```
<?php
	echo HTML::jquery();
?>
```

HTML output.
```
<script src="https://www.example.com/bl-kernel/vendors/jquery/jquery.min.js"></script>
```

<h2 id="bootstrap">Include Bootstrap</h2>

Bludit keeps the latest version of Bootstrap in its package, you can include it with the HTML helper.

Include Javascript file for Bootstrap.
```
<?php
	echo HTML::jsBootstrap();
?>
```

HTML output.
```
<script src="https://www.example.com/bl-kernel/vendors/bootstrap/bootstrap.bundle.min.js"></script>
```

Include CSS file for Bootstrap.
```
<?php
	echo HTML::cssBootstrap();
?>
```

HTML output.
```
<link rel="stylesheet" type="text/css" href="https://www.example.com/bl-kernel/vendors/bootstrap/bootstrap.min.css">
```

<h2 id="bootstrap-icons">Include Bootstrap Icons</h2>

Bludit keeps the latest version of [Bootstrap Icons](https://icons.getbootstrap.com/) in its package, you can include it with the HTML helper.

Include CSS file for Bootstrap Icons.
```
<?php
	echo HTML::cssBootstrapIcons();
?>
```

HTML output.
```
<link rel="stylesheet" type="text/css" href="https://www.example.com/bl-kernel/vendors/bootstrap-icons/bootstrap-icons.css">
```

Display a icon next to Heading.
```
<h1><i class="bi bi-alarm"></i>Alarm</h1>
```
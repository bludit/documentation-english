# Include frameworks
<!-- position: 7 -->

Themes in Bludit are very flexible; you can use any framework (Bootstrap, Foundation, Bulma, UIkit, Semantic UI, etc), any Javascript code, whatever you want.

We include a few frameworks in the documentation, but feel free to add more of them by editing this page.

<h2 id="jquery">Include jQuery</h2>

Bludit keeps the latest version of jQuery in its package, you can include it with the helper.
```
<?php
	echo Theme::jquery();
?>
```

HTML output
```
<script src="https://www.example.com/bl-kernel/js/jquery.min.js"></script>
```

<h2 id="bootstrap">Include Bootstrap</h2>

Bludit keeps the latest version of Bootstrap in its package, you can include it with the helper.

Include Javascript file for Bootstrap.
```
<?php
	echo Theme::jsBootstrap();
?>
```

HTML output
```
<script src="https://www.example.com/bl-kernel/js/bootstrap.bundle.min.js"></script>
```

Include CSS file for Bootstrap.
```
<?php
	echo Theme::cssBootstrap();
?>
```

HTML output
```
<link rel="stylesheet" type="text/css" href="https://www.example.com/bl-kernel/css/bootstrap.min.css">
```

<h2 id="uikit">Include UIkit</h2>

This frameworks is not included in the Bludit package, but you can easily include it with the helpers `Theme::css()` and `Theme::js()`, and using the UIkit CDN or downloading the files and include them to the theme.

The following example includes UIkit from a CDN, notice the `false` at the end of the line, this tells to the function we are going to use an externally-hosted file.
```
<?php
	echo Theme::css('https://cdnjs.cloudflare.com/ajax/libs/uikit/3.0.0-rc.26/css/uikit.min.css', false);

	echo Theme::js('https://cdnjs.cloudflare.com/ajax/libs/uikit/3.0.0-rc.26/js/uikit.min.js', false);
	echo Theme::js('https://cdnjs.cloudflare.com/ajax/libs/uikit/3.0.0-rc.26/js/uikit-icons.min.js', false);
?>
```

HTML output
```
<link rel="stylesheet" type="text/css" href="https://cdnjs.cloudflare.com/ajax/libs/uikit/3.0.0-rc.26/css/uikit.min.css">

<script src="https://cdnjs.cloudflare.com/ajax/libs/uikit/3.0.0-rc.26/js/uikit.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/uikit/3.0.0-rc.26/js/uikit-icons.min.js"></script>
```
# Pages: After creation
<!-- position: 5 -->

After a page is created Bludit calls the hook `afterPageCreate`. This hooks is also called for the pages created by the scheduler.

<div class="note">
This feature is implemented since Bludit v3.13
</div>

## Example: Append string to the title
The following plugin append a string at the beginning of the page after the page is created.

```php
<?php

class TitleAppender extends Plugin {

	public function afterPageCreate($key)
	{
		$page = new Page($key);
		$currentTitle = $page->title();
		$newTitle = 'Summer: '.$currentTitle;

		global $pages;
		$pages->edit(array(
				'key'=>$key,
				'title'=>$newTitle
		));
	}

}

?>
```

You can download the full example plugin from here:
- https://github.com/bludit/examples/tree/master/plugins/title-appender

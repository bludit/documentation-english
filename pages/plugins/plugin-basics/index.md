# اصول اولیه پلاگین
<!-- position: 1 -->

پلاگین در بلودیت در فولدر `bl-plugins` قرار دارد، و برای خود ساختار از پیش تعیین شده ای دارند. هر پلاگین در بلودیت یک شی با هوک ها (متدهای) مختلفی می باشند.

<h2 id="structure">ساختار فولدر و فایل ها</h2>
این ساختار اجباری فولدر و فایل ها برای پلاگین است.

```
/bl-plugins/{PLUGIN_NAME}/
	languages/en.json
	metadata.json
	plugin.php
```

<h2 id="name-and-description">نام و توضیحات</h2>
نام و توضیحات پلاگین در فایل JSON به نام `languages/en.json` قرار دارد.

```
{
	"plugin-data":
	{
		"name": "Hello World",
		"description": "Print Hello World in the sidebar"
	}
}
```

<h2 id="information">اطلاعات</h2>
اطلاعات پلاگین در فایل JSON به نام `metadata.json` قرار دارد.

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

<h2 id="hello-world">سلام دنیا</h2>
پلاگین سلام دنیا برای بلودیت، کد پایین باید در فایلی به نام `plugin.php` قرار بگیرد.

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
<div class="title">دانلود</div>
سورس کد فایل پلاگین <a href="https://github.com/bludit/examples/tree/master/plugins/hello-world">سلام دنیا</a> را دانلود کنید.
</div>

# Custom fields
<!-- position: 7 -->

<h2 id="introduction">Introduction</h2>

Custom fields allow the user to add fields to the content database; The custom fields appear in the admin panel interface when you create or edit content.

<h2 id="quick-example">Quick example</h2>

Add a custom field called `subtitle`. Go to:
```
Admin panel > Sidebar > Settings > General > Custom fields
```

Add the following JSON text to the textarea and click in the button "Save".
```
{
    "subtitle": {
        "type": "string",
        "placeholder": "Subtitle for the page",
		"position": "bottom"
    }
}
```

Now create a new page. Go to:
```
Admin panel > Sidebar > New content
```

As you can see there is a new field at the bottom of the editor requesting a "Subtitle for the page". Complete the "Title", "Content" and the new field "Subtitle for the page" and click on the button "Save".

The new page has a custom field called `subtitle` and you can print the value from the theme. For example.
```
<?php
	echo "The title of the page is " . $page->title();
	echo "The subtitle of the page is " . $page->custom('subtitle');
?>
```

<h2 id="structure">Structure</h2>

The structure is defined in the JSON format, and supports the following keys:
- (required) `type`: Type of the custom field, supported values (`string`, `bool`).
- (optional) `label`: The label for the custom field.
- (optional) `tip`: Small text for the user to describe the custom field.
- (optional) `default`: Default value for the custom field.
- (optional) `placeholder`: Small text inside the field.
- (optional) `position`: Position in the editor, supported values (`top`, `bottom`). Default value is empty and the field apper in "Editor > Options > Custom".

<h2 id="add-custom-fields">Add custom fields</h2>

To add custom fields go to:
```
Admin panel > Sidebar > Settings > General > Custom fields
```

To define custom field, you need to generate a JSON structure. Check out the following examples:

Custom field as `string` and the key name `youtube`:
```
{
    "youtube": {
        "type": "string",
        "label": "YouTube",
        "tip": "Write the YouTube URL."
    }
}
```

Custom field as `boolean` and the key name `inStock`:
```
{
    "inStock": {
        "type": "bool",
        "label": "In Stock",
        "tip": "Select this field if you have stock."
    }
}
```

Two custom fields with different types.
```
{
    "product": {
        "type": "string",
        "label": "Product",
        "tip": "Write the product name."
    },
    "inStock": {
        "type": "bool",
        "label": "In Stock",
        "tip": "Select this field if you have stock."
    }
}
```

Three custom fields with different types and different position in the editor.
```
{
    "product": {
        "type": "string",
		"placeholder": "Product name",
		"position": "top"
    },
    "inStock": {
        "type": "bool",
        "tip": "Select this field if you have stock.",
		"position": "top"
    },
    "imageURL": {
        "type": "string",
		"placeholder": "Image URL",
		"position": "bottom"
    }
}
```

<h2 id="get-custom-field">Get custom field</h2>

The class page provides the method `custom()`, which returns the value of the field.

The following example prints the value of the field `youtube` from the above example.
```
<?php
    echo $page->custom('youtube');
?>
```

Check the boolean value from the field `inStock` from the above example.
```
<?php
    if ($page->custom('inStock')) {
        echo "There is stock!";
    } else {
        echo "No more products";
    }
?>
```

<h2 id="delete-custom-field">Delete custom field</h2>

To delete a custom field you just need to remove the entry from the JSON structure. The custom fields are not completely deleted from the database when you do this, but they are invalidated.

If you want to remove all custom fields, just set an empty JSON in the textarea, as following:
```json
{}
```

<h2 id="plugin-custom-fields-parser">Plugin "Custom fields parser"</h2>

This plugin allows you to parse the page content and change it for extra code.

Let do an example with YouTube videos and embed code.

Add a custom field called `youtube`. Go to:
```bash
Admin panel > Sidebar > Settings > General > Custom fields
```

Add the following JSON text to the textarea and click in the button "Save".
```json
{
    "youtube": {
        "type": "string",
        "placeholder": "Write a YouTube video embed link",
		"label": "YouTube"
    }
}
```

Activate the plugin `Custom fields parser`.
```bash
Admin panel > Sidebar > Plugins > Custom fields parser > Activate
```

Edit the plugin settings, you can see there is a textarea for the custom field `youtube`, add the following iframe for the custom field.
```html
<iframe width="560" height="315" src="{{ value }}" frameborder="0" allow="autoplay" allowfullscreen></iframe>
```

The variable `{{ value }}` contains the value from the custom field defined on the page.

Create a new page and write a YouTube link in the custom field `youtube`.
```bash
Admin panel > Sidebar > New content > Options > Custom > YouTube
```

Add the following YouTube embed link.
```bash
https://www.youtube.com/embed/dQw4w9WgXcQ
```

Now in the content of the page, you can define where will be the YouTube embed video, for example:
```bash
Hello, this is my first YouTube video.

{{ youtube }}

Greetings!
```

After that, you can go to the new page and see how the embed video appears inside the page. Now you can create a new page and set a different YouTube link and the parse will show the embed code with the video.

This plugin avoids change the embed code on each page where you have an embed video.
# Custom fields
<!-- position: 7 -->

<div class="note">
<div class="title">Undercontruction</div>
The following section is underconstruction and is only available for Bludit beta (Github version).
</div>

## Introduction
Custom fields allow the user to add fields to the content database; The custom fields appear when you create or edit content.

## Structure
The structure is defined as a JSON format and supports the following keys:
- `type`: Type of the custom field, supported values (`string`, `bool`).
- `label`: The label for the custom field.
- `tip`: Small text for the user to describe the custom field.
- `default`: Default value for the custom field.

## Add custom fields
To add custom fields go to:
```
Settings > General > Custom fields
```

To define custom field you need to generate a JSON structure.

The following example set a `string` field with the name `youtube`.
```
{
    "youtube": {
        "type": "string",
        "label": "YouTube",
        "tip": "Write the YouTube URL."
    }
}
```

The following example set a `boolean` field with the name `inStock`.
```
{
	"inStock": {
		"type": "bool",
		"label": "In Stock",
		"tip": "Select this field if you have stock."
	}
}
```

## Get custom field
The class page provide the method `custom()` which returns the value of the field.

The following example print the value of the field `youtube` from the example above.
```
<?php
	echo $page->custom('youtube');
?>
```

or you can check the boolean from the field `inStock`.
```
<?php
	if ($page->custom('inStock')) {
		echo "There is stock!";
	} else {
		echo "No more products";
	}
?>
```
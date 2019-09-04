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
- `placeholder`: Small text inside the field.

## Add custom fields
To add custom fields go to:
```
Settings > General > Custom fields
```

To define custom field you need to generate a JSON structure. Check the following examples.

Define a `string` field with the name `youtube`.
```
{
    "youtube": {
        "type": "string",
        "label": "YouTube",
        "tip": "Write the YouTube URL."
    }
}
```

Define a `boolean` field with the name `inStock`.
```
{
    "inStock": {
        "type": "bool",
        "label": "In Stock",
        "tip": "Select this field if you have stock."
    }
}
```

Define two custom fields with different types.
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

## Get custom field
The class page provides the method `custom()` which returns the value of the field.

The following example prints the value of the field `youtube` from the example above.
```
<?php
    echo $page->custom('youtube');
?>
```

Check the boolean value from the field `inStock` from the example above.
```
<?php
    if ($page->custom('inStock')) {
        echo "There is stock!";
    } else {
        echo "No more products";
    }
?>
```

## Delete custom field
To delete a custom field you just need to remove the entry from the JSON structure.

The database keeps the value from the field on each page, just in case you want to recreate the field.
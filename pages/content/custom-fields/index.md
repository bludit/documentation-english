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
- `type`: Type of the custom field, supported values (`string`).
- `label`: The label for the custom field.
- `tip`: Small text for the user to describe the custom field.
- `default`: Default value for the custom field.

## Add custom fields
To add custom fields go to:
```
Settings > General > Custom fields
```

To define custom field you need to generate a JSON structure.

The following example defines a `string` field with the name `youtube`.
```
{
    "youtube": {
        "type": "string",
        "label": "YouTube",
        "tip": "Write the YouTube URL"
    }
}
```


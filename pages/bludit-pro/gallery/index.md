# Gallery
<!-- position: 4 -->

Gallery is a plugin for Bludit that allows you to create and manage image galleries and embed them anywhere in your content using a simple shortcode.

Gallery is included in Bludit PRO.

## Enable Gallery

- Go to the **admin area**.
- Go to **Settings > Plugins**.
- Search for the plugin **Gallery** and click on the **Activate** button.
- A **Galleries** link appears in the admin sidebar.

## Create a Gallery

- Go to the **admin area**.
- Click **Galleries** in the sidebar.
- Enter a **Gallery Name** and an optional **Gallery Description**.
- Click the **Create Gallery** button.

## Upload Images

- Go to the **admin area**.
- Click **Galleries** in the sidebar.
- Click the **Manage Images** button next to a gallery.
- Drag and drop images onto the upload area, or click **Upload Images** to select files from your device.
- Multiple images can be uploaded at once. Thumbnails are generated automatically.

## Delete an Image

- Go to the gallery management page.
- Click the **Delete** button below the image you want to remove.

## Edit a Gallery

- Go to the **admin area**.
- Click **Galleries** in the sidebar.
- Click **Manage Images** on the gallery you want to edit.
- Update the **Gallery Name**, **Slug**, or **Description** fields and click **Edit Gallery**.

## Delete a Gallery

- Go to the **admin area**.
- Click **Galleries** in the sidebar.
- Click the **Delete** button next to the gallery.
- All images in the gallery are removed permanently.

## Embed a Gallery in Content

When editing a page or post, click the **Galleries** button in the editor toolbar. A modal will appear listing your available galleries. Click **Insert** to add the gallery shortcode to your content.

You can also type the shortcode manually:

```
[gallery:<gallery slug name>]
```

Replace `gallery slug name` with the slug of the gallery you want to display. The slug is the URL-friendly version of the gallery name, shown in the gallery management form.

## Frontend Display

Galleries are rendered on the frontend as a responsive image grid with lazy loading. Clicking an image opens the full-size version.

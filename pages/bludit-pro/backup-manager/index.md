# Backup Manager
<!-- position: 3 -->

Backup Manager is a plugin for Bludit that allows you to create, restore, and delete backups of your entire website content. Backups are compressed into ZIP files and encrypted with AES-256 to keep your data safe.

Backup Manager is included in Bludit PRO.

## Enable Backup Manager

- Go to the **admin area**.
- Go to **Settings > Plugins**.
- Search for the plugin **Backup Manager** and click on the **Activate** button.
- Go to the plugin **Settings**.
- Set a **Backup Password** — this password is used to encrypt all your backups. Keep it safe, you will need it to restore.
- Set the **Max Backups** limit (default is 10). When the limit is reached, the oldest backup is deleted automatically.

## Create a Backup

- Go to the **admin area**.
- Go to **Settings > Plugins**.
- Search for the plugin **Backup Manager** and click on the **Settings** button.
- Click the **Create Backup** button.
- The backup is created and listed in the backup table, showing the date, type, and size.

> NOTE: A backup password must be set before you can create a backup. The backup captures all content inside the `bl-content` directory and does not include the Bludit core files.

## Restore a Backup

- Go to the **admin area**.
- Go to the **Backup Manager** settings.
- Find the backup you want to restore in the list.
- Click the **Restore** button next to that backup.
- Confirm the action.

> NOTE: Before restoring, an **emergency backup** is automatically created so you can undo the restore if something goes wrong. Emergency backups are not counted toward the max backup limit.

## Delete a Backup

- Go to the **admin area**.
- Go to the **Backup Manager** settings.
- Find the backup you want to delete in the list.
- Click the **Delete** button next to that backup.
- Confirm the action.

## Backup Types

Backups are displayed in the list with one of the following type labels:

- **Compressed + Encrypted** — A ZIP file protected with AES-256 encryption using your backup password. This is the default when your PHP installation supports it.
- **Compressed** — A ZIP file without encryption (created when AES-256 is not available).
- **Folder** — A plain directory backup, created as a fallback when ZIP compression is not available.
- **Emergency** — Automatically created before a restore operation to allow recovery.

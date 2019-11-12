# Domain Migrator
<!-- position: 2 -->

This plugin allows you to move your Bludit installation to another domain or subdomain, and also allows you to migrate from HTTP to HTTPS.

The plugin is included by default for free for [Patreon](https://www.patreon.com/bludit) backers, or you can download it for free from the following link.
- https://plugins.bludit.com/plugin/domain-migrator

## How to use this plugin
We recommend that you make a new installation of Bludit on the new server where it will be migrated to. Please read all the steps first, and then try to execute them.

The plugin works in a completely isolated directory, and it is not possible to break your current Bludit installation.

> NOTE: After the migration, the **Backups** and the checkpoints in **TimemachineX** won't work anymor. It is recommended that you deactivate and activate the plugins again to start from scratch.

### Steps to execute in the old Bludit installation
1. Install the plugin.
2. Go to the plugin settings.
3. Fill in the `Old domain` field. Actually, the plugin is going to try to automatically complete this field for you, so in theory, you don't need to do anything in this field.
4. Complete the `New domain` field with the new domain or subdomain where it will be migrated.
5. Click on the `Start` button.
6. The plugin is going to generate a new folder called `/bl-content-migrator` which contains the content to be moved to your new server.

### Steps to execute in the new Bludit installation
1. Make a new installation of Bludit on the new server.
2. Delete the folder `/bl-content`.
3. Copy the folder `/bl-content-migrator` from the old Bludit installation to the new installation.
4. Rename the folder `/bl-content-migrator` to `/bl-content`.
5. The migration is complete.
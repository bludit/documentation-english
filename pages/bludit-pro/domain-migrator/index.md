# Domain Migrator
<!-- position: 2 -->

This plugin allows you to move your Bludit installation to another domain or subdomain, also allow you to migrate from HTTP to HTTPS.

The plugin is for free for [Patreon](https://www.patreon.com/bludit) or you can download from the following link.
- https://plugins.bludit.com/plugin/domain-migrator

## How to use this plugin
We recommend to make a new installation of Bludit in the new server where it will be migrated. Please read all the steps first and then try to execute them.

The plugin works in a complete isolate directory, is not possible to break the current installation.

### Steps to execute in the old Bludit installation
1. Install the plugin.
2. Go to the plugin settings.
3. Complete the field `Old domain`, the plugin is going to try to automatically complete this field for you, in the end, you don't need to do anything in this field.
4. Complete the field `New domain` with the new domain or subdomain where it will be migrated.
5. Click on the button `Start`
6. The plugin is going to generate a new folder called `/bl-content-migrator` where is the new content for your new server.

### Steps to execute in the new Bludit installation
1. Make a new installation of Bludit in the server where Bludit is going to be migrated.
2. Delete the folder `/bl-content`.
3. Copy the folder `/bl-content-migrator` from the old Bludit installation to the new installation.
4. Rename the folder `/bl-content-migrator` to `/bl-content`.
5. The migration is complete.
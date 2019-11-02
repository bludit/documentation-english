# Upgrade guide
<!-- position: 4 -->

<h2 id="upgrade-from-major-version">Upgrade from the same major version</h2>

The next steps are valid for upgrading to any version of Bludit from the same major version. The major version is the first digit in the version number, for example, `Bludit v3.x`.

1. Make a full backup, including all files and directories.
2. Remember which version of Bludit you are using for a possible roll-back.
3. Download the latest version from [the official page](https://www.bludit.com).
4. Extract the zip file.
5. Replace existing files with the new files.
6. Clean your browser cache, and please read the note bellow.
7. Log into the admin area and check your settings.
8. Done.

> Note: If your website is behind some kind of server cache system (for example, Cloudflare provides one by default) you need to purge the files there, too. It's also a good idea to clear your browser cache. Bludit tries to reload the files with the new ones, but some componenets like TinyMCE may not reload, and provoke some issues in the UI or throw out Javascript errors.

---

<h2 id="upgrade-from-bludit-2-to-bludit-3">Upgrade Bludit from v2.3.4 to Bludit v3.0</h2>

To migrate between major versions, we recommend the tool created by [@anaggh](https://github.com/anaggh). Please read the following considerations, and also read the process outlined in his repository. If you have any questions you can ask in the [forum](https://forum.bludit.org) or in the [chat](https://gitter.im/bludit/support).

### Things to consider before migration

- Remember to do a full backup before proceeding with the migration. A full backup means copying all files, not only those in the folder `bl-content`.
- The plugins `Backups` and `Timemachine X` are going to be disabled and their content deleted.
- The migration tool creates a folder called, `/migrations/` and inside is another folder called `bl-content` with all the pages and databases compatible with Bludit v3.0.
- After the process of migration, you need to remove all the files and folders except `/migrations/` and install the new version of Bludit.
- After the installation of Bludit v3.0, copy the folder `/migrations/bl-content` to your new installation.

https://github.com/anaggh/bludit-scripts/tree/master/migration-v2-to-v3

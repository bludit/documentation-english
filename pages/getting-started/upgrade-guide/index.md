# Upgrade guide
<!-- position: 4 -->

<h2 id="upgrade-from-major-version">Upgrade from the same major version</h2>

The next steps are valid for upgrade any version from the same major version. The major version is the first digit from the value, for example, `Bludit v3.x`.

1. Make a full backup, all files and directories.
2. Remember which version of Bludit you are using for a possible roll-back.
3. Download the latest version from [the official page](https://www.bludit.com).
4. Extract the zip file.
5. Replace existing files with the new files.
6. Log into the admin area and check your settings.
7. Done.

---

<h2 id="upgrade-from-bludit-2-to-bludit-3">Upgrade Bludit from v2.3.4 to Bludit v3.0</h2>

To do the migration, we recommend the tool created by [@anaggh](https://github.com/anaggh), please read the follow considerations and also read the process in his repository. If you have any question you can ask in the [forum](https://forum.bludit.org) or in the [chat](https://gitter.im/bludit/support).

### Consideration before the migration

- Remember to do a full backup before proceeding with the migration, the full backup means copy all files not only from the folder `bl-content`.
- The plugins `Backups` and `Timemachine X` are going to be disabled and their content deleted.
- The migration tool creates a folder `/migrations/` and inside, another folder called `bl-content` with all the pages and databases compatible with Bludit v3.0.
- After the processes of migration, you need to remove all the files and folders except `/migrations/` and install the new version of Bludit.
- After the installation of Bludit v3.0, copy the folder `/migrations/bl-content` to your new installation.

https://github.com/anaggh/bludit-scripts/tree/master/migration-v2-to-v3
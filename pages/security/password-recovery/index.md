# Password recovery
<!-- position: 4 -->

You can recover the password for the `admin` user using the `recovery.php` script.

<h2 id="how-to-recover-the-password">How to recover the password</h2>

1. Download the [recovery.php](https://raw.githubusercontent.com/bludit/password-recovery-tool/master/recovery.php) file.
2. Upload the `recovery.php` file to your Bludit installation, on the root folder.
3. Open the file with your browser, for example: https://example.com/recovery.php, change the `example.com` for your domain.
4. A new password for the `admin` user is generated and displayed in the browser.
5. Log in to the admin panel with the `admin` user, and the new password generated.

The recovery.php script is going to try to delete itself, but if this doesn't happen, we recommend delete the recovery.php file by hand.

---

<h2 id="how-to-recover-the-password-via-command-line">How to recover the password via command line</h2>

You can execute the `recovery.php` file via the command line.

```
# Go to the directory where you have installed Bludit
cd /var/html/bludit

# Download the file
curl -o recovery.php https://raw.githubusercontent.com/bludit/password-recovery-tool/master/recovery.php

# Execute the tool
php recovery.php
```

```
Bludit Password Recovery Tool

Username: admin
New password: 00bef4566011d2015df2786dbd094003

>> The file recovery.php was deleted automatically for security reasons. <<
```
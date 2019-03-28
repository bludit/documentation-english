# بازیابی پسورد
<!-- position: 4 -->

با استفاده از اسکریپت `recovery.php` می توانید پسورد `admin` را بازیابی کنید.

<h2 id="how-to-recover-the-password">چکونه پسورد را بازیابی کنیم</h2>

1. فایل [recovery.php](https://raw.githubusercontent.com/bludit/password-recovery-tool/master/recovery.php) را دانلود کنید.
2. فایل `recovery.php` را به محل نصب بلودیت، در فولدر ریشه آپلود کنید.
3. با استفاده از مرورگر فایل خود را بازکنید، برای مثال: https://example.com/recovery.php ،آدرس وبسایت خود را بجای  `example.com` بنویسید.
4. پسورد جدید برای کاربر`admin` ایجاد و در مرورگر نمایش داده می شود.
5. توسط نام کاربری `admin` و پسورد ایجاد شده وارد پنل مدیریت شوید.

اسکریپت  recovery.php سعی می کند خودش را حذف کند ولی اگر این اتفاق نیافتاد پیشنهاد می کنیم فایل  recovery.php را دستی حذف کنید.

---

<h2 id="how-to-recover-the-password-via-command-line">چگونه پسورد را توسط خط فرمان بازیابی کنیم</h2>

شما می توانید فایل پی اچ پی `recovery.php` را توسط خط فرمان اجرا کنید


```
# به شاخه ای که بلودیت نصب شده است بروید
cd /var/html/bludit

# فایل را دانلود کنید
curl -o recovery.php https://raw.githubusercontent.com/bludit/password-recovery-tool/master/recovery.php

# ابزار را اجرا کنید
php recovery.php
```

```
Bludit Password Recovery Tool

Username: admin
New password: 00bef4566011d2015df2786dbd094003

>> The file recovery.php was deleted automatically for security reasons. <<
```

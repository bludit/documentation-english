# راهنمای نصب
<!-- position: 3 -->

<h2 id="installation-from-zip-file">نصب از طریق فایل zip</h2>

1. آخرین نسخه را از وبسایت [فارسی](http://bludit.ir) دانلود کنید
2. فایل zip را استخراج کنید.
3. فایل استخراج شده را به سرویس دهنده یا میزبانی وب آپلود کنید. شما می توانید فایل استخارج شده را در ریشه شاخه و یا در زیرشاخه آپلود کنید مثل `/bludit/`.
4. برای آپلود به میزبانی وب می توانید از کلاینت FTP ، WebFTP و یا ابزار دیگری که توسط میزبانی وب در اختیار شما قرار گرفته استفاده کنید.
5. از دامنه خود دیدن کنید. اگر فایل های خود را در ریشه شاخه آپلود کرده باشید به آدرس https://www.example.com مراجعه کنید، اگر فایل ها را در زیرشاخه آپلود کرده اید به آدرس https://www.example.com/bludit/ مراجعه کنید.
6. نصب کننده بلودیت را برای پیکربندی وبسایت خود دنبال کنید.

---

<h2 id="php-built-in-web-server">سرویس دهنده توکار PHP</h2>

شما می توانید از طریق خط فرمان و [سرویس دهنده توکار PHP ](http://php.net/manual/en/features.commandline.webserver.php) به سرعت بلودیت را اجرا کنید


```
$ git clone https://github.com/bludit/bludit.git
$ cd bludit
$ php -S localhost:8000
```

از طریق مرورگر مورد نظر خود به آدرس `http://localhost:8000` بروید.

---

<h2 id="docker">Docker</h2>
راه اندازی بلودیت از طریق [Docker Image](https://hub.docker.com/r/bludit/docker/) رسمی.

```
$ docker run --name bludit -p 8000:80 -d bludit/docker:latest
```

از طریق مرورگر مورد نظر خود به آدرس `http://localhost:8000` بروید.

---

<div class="note">
<div class="title">وب سرور</div>
برای اطلاعات بیشتر به بخش های روبرو مراجعه کنید. <a href="https://docs.bludit.com/fa/webservers/apache">Apache</a> - <a href="https://docs.bludit.com/fa/webservers/nginx">Nginx</a>
</div>

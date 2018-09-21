# Installation guide
<!-- position: 3 -->

<h2 id="installation-from-zip-file">Installation from zip file</h2>

1. Download the latest version from [the official page](https://www.bludit.com).
2. Extract the zip file.
3. Upload the extracted content to the server or hosting. You can upload the files in the root directory or a subdirectory such as `/bludit/`.
4. For upload the files you can use an FTP client or WebFTP or some tool provided by the hosting.
4. Visit you domain, if you upload the files to the root directory is going to be `https://www.example.com`, if you upload the files in a subdirectory is going to be like `https://www.example.com/bludit/`.
5. Follow the Bludit Installer to configure the website.

---

<h2 id="php-built-in-web-server">PHP Built-in web server</h2>

You can run Bludit quickly via the command line and [PHP Built-in web server](http://php.net/manual/en/features.commandline.webserver.php).

```
$ git clone https://github.com/bludit/bludit.git
$ cd bludit
$ php -S localhost:8000
```

Visit with you favorite browser the URL `http://localhost:8000`

---

<h2 id="docker">Docker</h2>
Bludit provides his official [Docker Image](https://hub.docker.com/r/bludit/docker/).

```
$ docker run --name bludit -p 8000:80 -d bludit/docker:latest
```

Visit with you favorite browser the URL `http://localhost:8000`

---

<div class="note">
<div class="title">Web Server</div>
Check our section about web server to get extra configurations. <a href="https://docs.bludit.com/en/webservers/apache">Apache</a> - <a href="https://docs.bludit.com/en/webservers/nginx">Nginx</a>
</div>
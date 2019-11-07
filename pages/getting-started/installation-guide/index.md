# Installation guide
<!-- position: 3 -->

<h2 id="installation-from-zip-file">Installation from zip file</h2>

1. Download the latest version from [the official page](https://www.bludit.com).
2. Extract the zip file.
3. Upload the extracted content to your server or hosting. You can upload the files in the root directory, or in a subdirectory such as `/bludit/`.
4. To upload the files, use an FTP client, WebFTP, or some tool provided by your hosting company.
4. Visit your domain. If you uploaded the files in the root directory go to `https://www.example.com`, if you uploaded the files in a subdirectory `https://www.example.com/bludit/`.
5. Follow the Bludit Installer to configure the website.

---

<h2 id="php-built-in-web-server">PHP Built-in web server</h2>

You can run Bludit quickly via the command line with the [PHP Built-in web server](https://www.php.net/manual/en/features.commandline.webserver.php).

```
$ git clone https://github.com/bludit/bludit.git
$ cd bludit
$ php -S localhost:8000
```

With your favorite browser, visit the URL `http://localhost:8000`

---

<h2 id="docker">Docker</h2>
Run Bludit from the official [Docker Image](https://hub.docker.com/r/bludit/docker/).

```
$ docker run --name bludit -p 8000:80 -d bludit/docker:latest
```

With your favorite browser, visit the URL `http://localhost:8000`

---

<h2 id="vagrant">Vagrant</h2>
Run Vagrant from the official [Vagrant Build](https://pilab.dev/bludit-vagrant).

```
$ git clone https://github.com/mhancoc7/Bludit-Vagrant.git
$ cd Bludit-Vagrant
$ vagrant up
```

With your favorite browser, visit the URL `http://localhost:8080`


---

<div class="note">
<div class="title">Web Server</div>
Check our section about web servers to for additional configurations. <a href="https://docs.bludit.com/en/webservers/apache">Apache</a> - <a href="https://docs.bludit.com/en/webservers/nginx">Nginx</a>
</div>

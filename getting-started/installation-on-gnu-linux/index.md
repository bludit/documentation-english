# Title: Installation on GNU/Linux
<!-- Position: 5 -->
---
All examples are out of the box installation, with Nginx Webserver. If you have the steps for other distributions, you can publish it on the [forum](https://forum.bludit.org) or just edit this page on Github, you can find a button at the end of the page with the link.

### Content
1. [Installation on Ubuntu 16.04](#ubuntu)
2. [Installation on Centos 7 / RedHat 7](#centos)

---

## <a id="ubuntu"></a> Installation on Ubuntu 16.04 LTS

Considerations:
- PHP-FPM is running under the username `www-data`.
- PHP-FPM is listen on Unix socket on `unix:/run/php/php7.0-fpm.sock`.
- Nginx is running under the username `www-data`.
- You don't have installed any other webserver.
- This is a basic configuration, considere read more for production environments.

Install Nginx Webserver, PHP and some tools.
```
$ sudo apt install -y nginx php-fpm php-dom php-mbstring php-cli php-gd php-opcache unzip wget
```

Configure Nginx.
```
$ sudo rm -f /etc/nginx/sites-enabled/*
```

Add a new file with the virtual server block in `/etc/nginx/conf.d/bludit.conf`
```
server {
	listen 80;
	server_name _;
	root /www/bludit;
	index index.php;

	location ~ \.php$ {
		fastcgi_pass    unix:/run/php/php7.0-fpm.sock;
		include         fastcgi.conf;
	}

	location / {
		try_files $uri $uri/ /index.php?$args;
	}
}
```

Download the latest version of Bludit and uncompress it.
```
$ mkdir /www
$ cd /www
$ wget https://s3.amazonaws.com/bludit-s3/bludit-builds/bludit_latest.zip
$ unzip bludit_latest.zip
$ sudo chown -R www-data:www-data /www
```

Restart the services to load the new configurations.
```
$ sudo service php7.0-fpm restart
$ sudo service nginx restart
```

Open your browser and navigate to http://localhost, finish with the installation.

---

## <a id="centos"></a> Installation on Centos 7 / Red Hat 7

Considerations:
- PHP-FPM is running under the username `nginx`.
- PHP-FPM is listen on Unix socket on `unix:/run/php/php-fpm.sock`.
- Nginx is running under the username `nginx`.
- You don't have installed any other webserver.
- This is a basic configuration, considere read more for production environments.

```
$ sudo yum install -y epel-release
```

Install Nginx Webserver, PHP and some tools.
```
$ yum install -y nginx php-fpm php-cli php-dom php-mbstring php-zip php-gd
```

Configure Nginx, add a new file with the virtual server block in `/etc/nginx/conf.d/bludit.conf`
```
server {
	listen 80;
	server_name _;
	root /www/bludit;
	index index.php;

	location ~ \.php$ {
		fastcgi_pass    unix:/run/php/php7.0-fpm.sock;
		include         fastcgi.conf;
	}

	location / {
		try_files $uri $uri/ /index.php?$args;
	}
}
```

Download the latest version of Bludit and uncompress it.
```
$ mkdir /www
$ cd /www
$ wget https://s3.amazonaws.com/bludit-s3/bludit-builds/bludit_latest.zip
$ unzip bludit_latest.zip
$ sudo chown -R nginx:nginx /www
```

Restart the services to load the new configurations.
```
$ sudo systemctl php-fpm restart
$ sudo systemctl nginx restart
```

Open your browser and navigate to http://localhost, finish with the installation.
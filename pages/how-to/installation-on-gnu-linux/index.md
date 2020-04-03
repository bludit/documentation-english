# Installation on GNU/Linux
<!-- position: 3 -->

<h2 id="ubuntu">Installation on Ubuntu 16.04 LTS</h2>

Considerations:
- PHP version 7.0, maybe in your installation is different and updated version.
- PHP-FPM is running under the username `www-data`.
- PHP-FPM is listening on a Unix socket on `unix:/run/php/php7.0-fpm.sock`.
- Nginx is running under the username `www-data`.
- You don't have any other web server installed.
- This is a basic configuration, consider reading more before using this in production environments.

Install Nginx Webserver, PHP, and some tools.
```
$ sudo apt install -y nginx php-fpm php-dom php-mbstring php-cli php-gd php-opcache unzip
```

Configure Nginx.
```
$ sudo rm -f /etc/nginx/sites-enabled/*
```

Add a new file with the virtual server block in `/etc/nginx/conf.d/bludit.conf`.
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
$ curl https://www.bludit.com/releases/bludit-latest.zip --output bludit-latest.zip
$ unzip bludit-latest.zip
$ sudo chown -R www-data:www-data /www
```

Restart the services to load the new configuration.
```
$ sudo service php7.0-fpm restart
$ sudo service nginx restart
```

Open your browser and navigate to http://localhost to complete the installation.

<h2 id="centos">Installation on Centos 7 / Red Hat 7</h2>

Considerations:
- PHP-FPM is running under the username `nginx`.
- PHP-FPM is listen on a Unix socket on `unix:/run/php/php-fpm.sock`.
- Nginx is running under the username `nginx`.
- You don't have any other web server installed.
- This is a basic configuration, consider reading more before using this in production environments.

Install EPEL repository
```
$ sudo yum install -y epel-release
```

Install Nginx Webserver, PHP, and some tools.
```
$ yum install -y nginx php-fpm php-cli php-dom php-mbstring php-zip php-gd
```

Configure Nginx, add a new file with the virtual server block in `/etc/nginx/conf.d/bludit.conf`.
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
$ curl https://www.bludit.com/releases/bludit-latest.zip --output bludit-latest.zip
$ unzip bludit-latest.zip
$ sudo chown -R nginx:nginx /www
```

Restart the services to load the new configuration.
```
$ sudo systemctl php-fpm restart
$ sudo systemctl nginx restart
```

Open your browser and navigate to http://localhost to complete the installation.
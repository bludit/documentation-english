# Nginx
<!-- position: 2 -->

Bludit supports [Nginx](https://nginx.org/en/), and we actually recommend it as a web server.

Bludit has its own `router` which handles all requests and responses. The idea is to redirect all requests to the `index.php` file.

Considerations:
- The webserver is running PHP-FPM as CGI Process Manager.
- PHP-FPM is listening on Unix socket at `unix:/run/php/php-fpm.sock`.

## HTTP set up
In order to set up a new server block for Bludit, generate a new file with the configuration in `/etc/nginx/conf.d/bludit.conf`. The directory could be different in other distributions of GNU/Linux; for example, in Ubuntu it could be `/etc/nginx/sites-enabled/bludit.conf`.

For security reasons, don't forget to forbid access to PHP files inside the `/bl-kernel/` folder, as well as the `/bl-content/databases`, `/bl-content/pages`, and `/bl-content/workspaces` folders. Otherwise it's possible that users would have direct access to some files in these directories.

```
server {
	listen 80;
	server_name example.com;
	root /www/bludit;
	index index.php;

	access_log /var/log/nginx/example.log;
	error_log /var/log/nginx/example.log;

	location ~ \.(jpg|jpeg|gif|png|css|js|ico|svg|eot|ttf|woff|woff2|otf)$ {
		access_log        off;
		expires           30d;
	}

	location ~ \.php$ {
		fastcgi_pass    unix:/run/php/php-fpm.sock;
		fastcgi_index   index.php;
		include         fastcgi.conf;
	}

	location / {
		try_files $uri $uri/ /index.php?$args;
	}

	location ^~ /bl-content/databases/ { deny all; }
	location ^~ /bl-content/workspaces/ { deny all; }
	location ^~ /bl-content/pages/ { deny all; }
	location ^~ /bl-kernel/*.php { deny all; }
}
```

## HTTPS set up
HTTPS configuration needs some extra configuration, and of course the SSL certificate. We recommend using [LetsEncrypt](https://letsencrypt.org) to get a free certificate.

The server block uses the following configuration, and we added an extra block to redirect request from HTTP to HTTPS.
```

server {
    if ($host = example.com) {
        return 301 https://$host$request_uri;
} # managed by Certbot

        listen 80;
        listen [::]:80;
        server_name example.com;
        return 301 https://$host$request_uri;
}

server {
	listen 443 ssl;
	server_name example.com;
	root /www/bludit;
	index index.php;

	access_log /var/log/nginx/example.log;
	error_log /var/log/nginx/example.log;

	ssl_certificate         /etc/letsencrypt/live/example.com/fullchain.pem;
	ssl_certificate_key     /etc/letsencrypt/live/example.com/privkey.pem;
	ssl_dhparam             /etc/ssl/certs/dhparam.pem;

	ssl_session_cache       shared:SSL:50m;
	ssl_session_timeout     10m;

	ssl_prefer_server_ciphers	off;
	ssl_stapling			on;
	ssl_stapling_verify		on;
	ssl_protocols			TLSv1.2 TLSv1.3;
	ssl_ciphers			ECDHE-ECDSA-AES128-GCM-SHA256:ECDHE-RSA-AES128-GCM-SHA256:ECDHE-ECDSA-AES256-GCM-SHA384:ECDHE-RSA-AES256-GCM-SHA384:ECDHE-ECDSA-CHACHA20-POLY1305:ECDHE-RSA-CHACHA20-POLY1305:DHE-RSA-AES128-GCM-SHA256:DHE-RSA-AES256-GCM-SHA384;;

	add_header Strict-Transport-Security "max-age=31557600" always;

	location ~ \.(jpg|jpeg|gif|png|css|js|ico|svg|eot|ttf|woff|woff2|otf)$ {
		access_log        off;
		expires           30d;
	}

	location ~ \.php$ {
		fastcgi_pass    unix:/var/run/php-fpm/php-fpm.sock;
		fastcgi_index   index.php;
		include         fastcgi.conf;
		fastcgi_param   HTTPS on;
	}

	location / {
		try_files $uri $uri/ /index.php?$args;
	}

	location ^~ /bl-content/databases/ { deny all; }
	location ^~ /bl-content/workspaces/ { deny all; }
	location ^~ /bl-content/pages/ { deny all; }
	location ^~ /bl-kernel/*.php { deny all; }
}
```

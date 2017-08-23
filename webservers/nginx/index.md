# Title: Nginx
<!-- Position: 1 -->
<!-- Date: 2017-08-22 22:00:00 -->
---
Bludit supports Nginx and is a recommended option for a Webserver.

Bludit has hiw own `router` who handle all request and response, so the idea is give it all the request to the `index.php` file.

Considerations:
- The webserver is running PHP-FPM as CGI Process Manager
- PHP-FPM is listen on Unix socket on `unix:/run/php/php-fpm.sock`.

## HTTP set up
In order to set up a new server block for Bludit, generate a new file with the configuration in `/etc/nginx/conf.d/bludit.conf`, this directory could be different in other distributions of GNU/Linux, for example, in Ubuntu could be `/etc/nginx/sites-enabled/bludit.conf`.

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
}
```

## HTTPS set up
HTTPS configuration has some extra configurations and of course the SSL certificate. We recommend use [LetsEncrypt](https://letsencrypt.org) to get a free certificate.

The server block has this configuration, and we add and extra block to redirect request from HTTP to HTTPS.
```
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

	ssl_prefer_server_ciphers	on;
	ssl_stapling			on;
	ssl_stapling_verify		on;
	ssl_protocols			TLSv1.1 TLSv1.2;
	ssl_ciphers			"ECDHE-RSA-AES256-GCM-SHA384:ECDHE-RSA-AES128-GCM-SHA256:DHE-RSA-AES256-GCM-SHA384:DHE-RSA-AES128-GCM-SHA256:ECDHE-RSA-AES256-SHA384:ECDHE-RSA-AES128-SHA256:ECDHE-RSA-AES256-SHA:ECDHE-RSA-AES128-SHA:DHE-RSA-AES256-SHA256:DHE-RSA-AES128-SHA256:DHE-RSA-AES256-SHA:DHE-RSA-AES128-SHA:ECDHE-RSA-DES-CBC3-SHA:EDH-RSA-DES-CBC3-SHA:AES256-GCM-SHA384:AES128-GCM-SHA256:AES256-SHA256:AES128-SHA256:AES256-SHA:AES128-SHA:DES-CBC3-SHA:HIGH:!aNULL:!eNULL:!EXPORT:!DES:!MD5:!PSK:!RC4";

	add_header Strict-Transport-Security "max-age=31557600; includeSubDomains";

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
}

# Redirect from HTTP to HTTPS
server {
	listen 80;
	server_name example.com;
	return 301 https://example.com$request_uri;
}
```


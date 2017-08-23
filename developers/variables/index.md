# Title: Variables
<!-- Position: 2 -->
---

## Constants

Here is a list of all constant and the default value. This constant are in the file `/bludit/bl-kernel/boot/init.php`

| Constants 			| Value 		| Type 		| Notes
| ------------------------------|-----------------------|---------------|-----------------------------------------------------|
| BLUDIT_VERSION 		| 1.0.1 		| String 	| Bludit version
| BLUDIT_CODENAME 		| Vector 		| String 	| Bludit codename
| BLUDIT_RELEASE_DATE 		| 2016-01-15 		| String 	| Bludit release date, date format YYYY-MM-DD
| BLUDIT_BUILD			| 20160115		| String 	| Bludit build number
| DEBUG_MODE			| True			| Boolean 	| False if you wan to disable all logs and warnings
| THUMBNAILS_WIDTH		| 400			| Integer 	| Thumbnails width size
| THUMBNAILS_HEIGHT		| 400			| Integer 	| Thumbnails height size
| THUMBNAILS_AMOUNT		| 6			| Integer 	| Amount of thumbnails on Quick Images
| SALT_LENGTH			| 8			| Integer 	| String length of the password salt
| PAGE_BREAK			| <\!-- pagebreak -->	| String 	| String for break a post o page
| POSTS_PER_PAGE_ADMIN		| 10			| Integer 	| Post per page for Admin panel->Manage->Posts
| DB_DATE_FORMAT		| Y-m-d H:i:s		| String 	| Database date format
| SITEMAP_DATE_FORMAT		| Y-m-d			| String 	| Sitemap date format
| SCHEDULED_DATE_FORMAT		| d M - h:i a		| String 	| Date format for dashboard schedule posts
| TOKEN_EMAIL_TTL		| +15 minutes		| String 	| Token time to live for login via email
| MB_STRING			| True / False		| Boolean 	| Multibyte string extension loaded
| SALT_LENGTH			| 8			| Integer 	| String length of the password salt

## Constants: Absolutes paths

- Web root directory: */var/www/*
- Bludit directory: */var/www/bludit/*

| Constants 			| Value 						| Type 		| Notes
| ------------------------------|-------------------------------------------------------|---------------|--------------------------|
| PATH_ROOT			| /var/www/bludit/					| String
| PATH_LANGUAGES		| /var/www/bludit/bl-languages/ 			| String
| PATH_THEMES			| /var/www/bludit/bl-themes/ 				| String
| PATH_PLUGINS			| /var/www/bludit/bl-plugins/ 				| String
| PATH_KERNEL			| /var/www/bludit/bl-kernel/ 				| String
| PATH_CONTENT			| /var/www/bludit/bl-content/ 				| String
| PATH_ABSTRACT			| /var/www/bludit/bl-kernel/abstract/ 			| String
| PATH_RULES			| /var/www/bludit/bl-kernel/boot/rules/ 		| String
| PATH_HELPERS			| /var/www/bludit/bl-kernel/helpers/ 			| String
| PATH_AJAX			| /var/www/bludit/bl-kernel/ajax/ 			| String
| PATH_JS			| /var/www/bludit/bl-kernel/js/ 			| String
| PATH_POSTS			| /var/www/bludit/bl-content/posts/ 			| String
| PATH_PAGES			| /var/www/bludit/bl-content/pages/ 			| String
| PATH_DATABASES		| /var/www/bludit/bl-content/databases/ 		| String
| PATH_PLUGINS_DATABASES	| /var/www/bludit/bl-content/databases/plugins/ 	| String
| PATH_TMP			| /var/www/bludit/bl-content/tmp/ 			| String
| PATH_UPLOADS			| /var/www/bludit/bl-content/uploads/ 			| String
| PATH_UPLOADS_PROFILES		| /var/www/bludit/bl-content/uploads/profiles/ 		| String
| PATH_UPLOADS_THUMBNAILS	| /var/www/bludit/bl-content/uploads/thumbnails/ 	| String
| PATH_ADMIN			| /var/www/bludit/bl-kernel/admin/ 			| String
| PATH_ADMIN_THEMES		| /var/www/bludit/bl-kernel/admin/themes/ 		| String
| PATH_ADMIN_CONTROLLERS	| /var/www/bludit/bl-kernel/admin/controllers/ 		| String
| PATH_ADMIN_VIEWS		| /var/www/bludit/bl-kernel/admin/views/ 		| String
| PATH_ADMIN_VIEWS		| /var/www/bludit/bl-kernel/admin/views/ 		| String
| PATH_THEME			| /var/www/bludit/bl-themes/{theme_name}/		| String
| PATH_THEME_PHP		| /var/www/bludit/bl-themes/{theme_name}/php/		| String
| PATH_THEME_CSS		| /var/www/bludit/bl-themes/{theme_name}/css/		| String
| PATH_THEME_JS			| /var/www/bludit/bl-themes/{theme_name}/js/		| String
| PATH_THEME_IMG		| /var/www/bludit/bl-themes/{theme_name}/img/		| String
| PATH_THEME_LANG		| /var/www/bludit/bl-themes/{theme_name}/language/	| String


## Constants: Relative paths

- Web root directory: */var/www/*
- Bludit directory: */var/www/bludit/*

| Constants 				| Value 							| Type 		| Notes
| --------------------------------------|---------------------------------------------------------------|---------------|--------------------------|
| HTML_PATH_ROOT			| /bludit/							| String
| HTML_PATH_THEMES			| /bludit/bl-themes/ 						| String
| HTML_PATH_THEME			| /bludit/bl-themes/{theme_name}/ 				| String
| HTML_PATH_THEME_CSS			| /bludit/bl-themes/{theme_name}/css/ 				| String
| HTML_PATH_THEME_JS			| /bludit/bl-themes/{theme_name}/js/ 				| String
| HTML_PATH_THEME_IMG			| /bludit/bl-themes/{theme_name}/img/ 				| String
| HTML_PATH_ADMIN_ROOT			| /bludit/admin/ 						| String
| HTML_PATH_ADMIN_THEME			| /bludit/bl-kernel/admin/themes/{admin_theme_name}/ 		| String
| HTML_PATH_ADMIN_THEME_JS		| /bludit/bl-kernel/admin/themes/{admin_theme_name}/js/ 	| String
| HTML_PATH_ADMIN_THEME_CSS		| /bludit/bl-kernel/admin/themes/{admin_theme_name}/css/ 	| String
| HTML_PATH_ADMIN_THEME_IMG		| /bludit/bl-kernel/admin/themes/{admin_theme_name}/img/ 	| String
| HTML_PATH_UPLOADS			| /bludit/bl-content/uploads/					| String
| HTML_PATH_UPLOADS_PROFILES		| /bludit/bl-content/uploads/profiles/				| String
| HTML_PATH_UPLOADS_THUMBNAILS		| /bludit/bl-content/uploads/thumbnails/			| String
| HTML_PATH_PLUGINS			| /bludit/bl-plugins/						| String


## Constants: Domain and base path

- Protocol: *http or https*
- Domain: *www.domain.com*
- Base path: */bludit/*

| Constants 			| Value 								| Type 		| Notes
| ------------------------------|-----------------------------------------------------------------------|---------------|--------------------------|
| DOMAIN			| {protocol}://www.domain.com						| String
| DOMAIN_BASE			| {protocol}://www.domain.com/bludit/					| String
| DOMAIN_THEME_CSS		| {protocol}://www.domain.com/bludit/bl-themes/{theme_name}/css/	| String
| DOMAIN_THEME_JS		| {protocol}://www.domain.com/bludit/bl-themes/{theme_name}/js/		| String
| DOMAIN_THEME_IMG		| {protocol}://www.domain.com/bludit/bl-themes/{theme_name}/img/	| String
| DOMAIN_UPLOADS		| {protocol}://www.domain.com/bludit/bl-content/uploads/		| String
| DOMAIN_UPLOADS_PROFILES	| {protocol}://www.domain.com/bludit/bl-content/uploads/profiles/	| String
| DOMAIN_UPLOADS_THUMBNAILS	| {protocol}://www.domain.com/bludit/bl-content/uploads/thumbnails/	| String



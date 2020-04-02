# Apache Notes


## Rewrite requests

.htaccess file to rewrite requests.

Example given shows how to intercept requests made to <host>/api and rewrite them to example.com/api/ 

~~~~
# Configure
RewriteEngine on

# Rewrite non-www requests
RewriteCond %{HTTP_HOST} !^www\.
RewriteRule ^(.*)$ https://www.%{HTTP_HOST}%{REQUEST_URI} [L,R=302]

# Rewrite API requests
RewriteCond $1 ^(api)
RewriteRule ^(.*)$ https://example.com.com/api/$1 [L,R=302]
~~~~

## Xampp Virtual hosts

X:/somefolder/xampp2/apache/conf/extra/httpd-vhosts.conf

~~~~
<VirtualHost *:80>
	# Virtual host for localhost
	ServerName localhost
	ServerAlias localhost
	DocumentRoot X:/somefolder/xampp2/htdocs/
</VirtualHost>

<VirtualHost *:80>
	# Virtual host for mysite.myext
	ServerName www.mysite.myext
	ServerAlias mysite.myext
	DocumentRoot X:/somefolder/xampp2/htdocs/mysite.myext
</VirtualHost>
~~~~

# Free Port 80

* https://stackoverflow.com/questions/20558410/xampp-port-80-in-use-by-unable-to-open-process-with-pid-4-12
** net stop was /y
*  https://shellcreeper.com/how-to-create-valid-ssl-in-localhost-for-xampp/


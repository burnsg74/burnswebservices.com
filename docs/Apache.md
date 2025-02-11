# Apache

User Folder Permissions

mod_rewrite is a very powerful tool, but the wrong one for this job as it alters redirects-requested URLs based on regular expressions. You were right with your first choice of the userdir module. Your problem boils down to making sure the HTML and other files that users drop into their web space are readable by the server without making the whole user directory world readable, which is easily done with some carefully chosen ownerships and permissions. Working with the default Apache userdir configuration, http://hostname/~username/ is mapped to /home/username/public_html/. The first step is to make sure that the user directories are readable by the users only:

```

```
chmod 711 /home/*

```
Then the public_html directories need to be readable by the group under which Apache is run. This is usually 'apache', but some distros run the server as 'nobody' Look for the Group directive in the httpd.conf file:
```
chgrp apache /home/*/public_html
chmod 750 /home/*/public_html
chmod g+s /home/*/public_html

```
Now the users' directories can only be read by the users themselves (chmod 711) while the public_html directories belong to the 'apache' group and can be read (but not written) by members of that group. The third command makes the directory setgid, so any files created in here will automatically belong to the apache group instead of the user's normal group. Ownership of the file is still with the user. If you want to use a different directory for the user's file instead of public_html, edit the relevant part of your Apache configuration. This can vary from one distro to another but one of your config files will contain the line:
```
UserDir public_html

```
Change this to wherever you want the HTML files to be kept in each user's home directory.
```

.htaccess Sample

```
RewriteEngine On 
RewriteCond %{HTTP_HOST} !^www\. [NC]
RewriteRule ^ http://www.%{HTTP_HOST}%{REQUEST_URI} [R=301,L]

RewriteEngine On
# The following rule tells Apache that if the requested filename
# exists, simply serve it.
RewriteCond %{REQUEST_FILENAME} -s [OR]
RewriteCond %{REQUEST_FILENAME} -l [OR]
RewriteCond %{REQUEST_FILENAME} -d
RewriteRule ^.*$ - [NC,L]
# The following rewrites all other queries to index.php. The
# condition ensures that if you are using Apache aliases to do
# mass virtual hosting, the base path will be prepended to
# allow proper resolution of the index.php file; it will work
# in non-aliased environments as well, providing a safe, one-size
# fits all solution.
RewriteCond %{REQUEST_URI}::$1 ^(/.+)(.+)::^B$
RewriteRule ^(.*)$ - [E=BASE:%1]
RewriteRule ^(.*)$ %{ENV:BASE}index.php [NC,L]

## EXPIRES CACHING ##
<IfModule mod_expires.c>
ExpiresActive On
ExpiresByType image/jpg "access 1 year"
ExpiresByType image/jpeg "access 1 year"
ExpiresByType image/gif "access 1 year"
ExpiresByType image/png "access 1 year"
ExpiresByType text/css "access 1 month"
ExpiresByType text/html "access 1 month"
ExpiresByType application/pdf "access 1 month"
ExpiresByType text/x-javascript "access 1 month"
ExpiresByType application/x-shockwave-flash "access 1 month"
ExpiresByType image/x-icon "access 1 year"
ExpiresDefault "access 1 month"
</IfModule>
## EXPIRES CACHING ##

AddOutputFilterByType DEFLATE text/plain
AddOutputFilterByType DEFLATE text/html
AddOutputFilterByType DEFLATE text/xml
AddOutputFilterByType DEFLATE text/css
AddOutputFilterByType DEFLATE application/xml
AddOutputFilterByType DEFLATE application/xhtml+xml
AddOutputFilterByType DEFLATE application/rss+xml
AddOutputFilterByType DEFLATE application/javascript
AddOutputFilterByType DEFLATE application/x-javascript
```

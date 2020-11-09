#Cómo instalar un certificado SSL en webfaction



archivo #.htaccess

Options +FollowSymLinks
RewriteEngine on
RewriteCond %{HTTP_HOST} ^lamascada.cl$ [NC]
RewriteRule ^(.*)$ https://www.lamascada.cl/$1 [R=301,L]

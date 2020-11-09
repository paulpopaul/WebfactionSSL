#Cómo instalar un certificado SSL en Webfaction? <br>
Apache / Django <br>



archivo #.htaccess

Options +FollowSymLinks
RewriteEngine on
RewriteCond %{HTTP_HOST} ^lamascada.cl$ [NC]
RewriteRule ^(.*)$ https://www.lamascada.cl/$1 [R=301,L]

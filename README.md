# Cómo instalar un certificado SSL en Webfaction? <br>

www.webfaction.com <br>
DOMAINS / WEBSITE <br>
> Website

entrar al nombre de la aplicacion ej: lamascadaweb <br>
seguridad: change http to https <br>

certificate type: Let's Encrypt certificate



archivo #.htaccess  <br>
 <br>
Options +FollowSymLinks <br>
RewriteEngine on <br>
RewriteCond %{HTTP_HOST} ^lamascada.cl$ [NC] <br>
RewriteRule ^(.*)$ https://www.lamascada.cl/$1 [R=301,L] <br>

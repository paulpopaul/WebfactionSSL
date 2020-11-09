# Certificado SSL en Servidor Webfaction <br>

www.webfaction.com <br>
DOMAINS / WEBSITE <br>
>> Website
 <br>
entrar al nombre de la aplicacion ej: lamascadaweb <br>
seguridad: cambiar http to https <br>
 <br>
certificado tipo: Let's Encrypt certificate  <br>
 <br>


archivo #.htaccess  <br>
 <br>
Options +FollowSymLinks <br>
RewriteEngine on <br>
RewriteCond %{HTTP_HOST} ^lamascada.cl$ [NC] <br>
RewriteRule ^(.*)$ https://www.lamascada.cl/$1 [R=301,L] <br>

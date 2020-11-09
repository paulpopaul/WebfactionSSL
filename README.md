# Certificado SSL en Servidor Webfaction <br>

www.webfaction.com <br>
[ DOMAINS / WEBSITE ] <br>
[ Website ]
 <br>
Entrar al nombre de la aplicacion ej: lamascadaweb <br>
Seguridad: http to https <br>
 <br>
Certificado tipo: Let's Encrypt certificate  <br>
 <br>
 <br>
# .htaccess (1) <br>
RewriteEngine On
RewriteCond %{HTTP:X-Forwarded-SSL} !on
RewriteCond %{REQUEST_URI} !^/(.well-known)(/|$)
RewriteRule ^(.*)$ https://%{HTTP_HOST}%{REQUEST_URI} [R=301,L]


# .htaccess (2) <br>
 <br>
Options +FollowSymLinks <br>
RewriteEngine on <br>
RewriteCond %{HTTP_HOST} ^lamascada.cl$ [NC] <br>
RewriteRule ^(.*)$ https://www.lamascada.cl/$1 [R=301,L] <br>

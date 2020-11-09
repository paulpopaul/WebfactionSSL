# Certificado SSL en Servidor Webfaction <br>

1) Ir a www.webfaction.com <br>
<br>

2) Pestaña [ DOMAINS / WEBSITE ] <br>
<br>

3) Pestaña [ Website ]  <br>

A) Entrar al nombre de la aplicacion ej: lamascadaweb <br>
B) Seguridad: http to https <br>
C) Certificado tipo: Let's Encrypt certificate  <br>
D) Guardar <br>
 <br>
4) + Nuevo website  <br>

 A) Nombre: redireccion_lamascada2  <br>
 B) Seguridad: http <br>
 C) Agregar Dominios www.lamascada.cl / lamascada.cl <br>
 D) Crear nueva aplicacion, Nombre: redireccion_lamascada2, Tipo: Static/CGI/PHP  <br>
 
 
5) Crear archivo htaccess y agregar a carpeta raiz de nueva app <br>
# .htaccess (1) <br>
RewriteEngine On <br>
RewriteCond %{HTTP:X-Forwarded-SSL} !on <br> 
RewriteCond %{REQUEST_URI} !^/(.well-known)(/|$) <br>
RewriteRule ^(.*)$ https://%{HTTP_HOST}%{REQUEST_URI} [R=301,L] <br>
<br>
<br>
# .htaccess (2) <br>
 <br>
Options +FollowSymLinks <br>
RewriteEngine on <br>
RewriteCond %{HTTP_HOST} ^lamascada.cl$ [NC] <br>
RewriteRule ^(.*)$ https://www.lamascada.cl/$1 [R=301,L] <br>

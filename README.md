# demo-proxy
Ambiente demo para demostrar la funcionalidad de un reverse-proxy seguro dentro de un ambiente de contenedores

Topologia:
Internet ---->RevProxy<---->Web Server

Objetivo:
Demostrar la implementación de una instancia tipo contenedor (containers) bajo la funcionalidad de reverse-proxy para balancear el acceso hacia un servidor web de forma segura ingresando un Token Estatico (vía URL) y autenticación simple de usuario para poder acceder al sitio web.

Flujo:
1) Instalar certificados locales (vease carpeta "certificados")
2) Editar resolución de nombre de dominio "localhost.com" dentro de equipo local donde se realizaran las pruebas.Favor de referir: 
    -Windows: https://gist.github.com/zenorocha/18b10a14b2deb214dc4ce43a2d2e2992
    -Linux: https://linuxize.com/post/how-to-edit-your-hosts-file/
4) Petición de navegación por navegador via HTTP hacia localhost.com
5) Redireccionamiento HTTP--->HTTPS
6) 








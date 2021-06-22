#################Demo-Proxy########################

Ambiente demo para demostrar la funcionalidad de un reverse-proxy seguro dentro de un ambiente de contenedores.

Topologia:
Internet ---->RevProxy<---->Web Server

Objetivo:
Demostrar la implementación de una instancia tipo contenedor (containers) bajo la funcionalidad de reverse-proxy para balancear el acceso hacia un servidor web de forma segura ingresando un Token Estatico (vía URL) y autenticación simple de usuario para poder acceder al sitio web.

Plataforma:
-Docker-desktop: https://www.docker.com/products/docker-desktop

Elementos:
-Web Server NGINX. https://hub.docker.com/_/nginx
-Archivo tipo .httpasswrd. https://clouding.io/hc/es/articles/360010325199-Proteger-directorios-con-htpasswd-y-htaccess

Variables de entorno:
-Dentro del archivo de "docker-compose.yml" editar/sustituir la cadena "path local de carpeta de usuario con archivo" con el path de ubicación de archivos para referencia de volumenes dentro de cada contenedor para edición de archivos locales.Ejemplo:
    - Para el volumen de la carpeta de certificados "//c/Users/demo/Documents/GitHub/demo/certs:/usr/share/nginx/html/certs:rw"

Configuración:
-Crear una carpeta local "MiCarpeta" para descargar todos los archivos de este repositorio en la misma
-Editar las variables de entorno dentro del archivo "docker-compose.yml"
-Iniciar Docker-Desktop
-Via consola/ssh ejecutar dentro de la carpeta previamente creada con los archivos "C:\MiCarpeta> docker-compose up -d".
    
Flujo:
1) Instalar certificados locales (vease carpeta "certificados") con finalidad de prueba para este ambiente demo. Favor de referir:
    -Windows: https://techcommunity.microsoft.com/t5/windows-server-essentials-and/installing-a-self-signed-certificate-as-a-trusted-root-ca-in/ba-p/396105
    -Linux: https://ubuntu.com/server/docs/security-certificates
3) Editar resolución de nombre de dominio "localhost.com" dentro de equipo local donde se realizaran las pruebas.Favor de referir: 
    -Windows: https://gist.github.com/zenorocha/18b10a14b2deb214dc4ce43a2d2e2992
    -Linux: https://linuxize.com/post/how-to-edit-your-hosts-file/
4) Petición de navegación por navegador via HTTP hacia localhost.com
5) Redireccionamiento HTTP--->HTTPS
6) Ingresar localhost.com/token-estatico (Token estático se provisionara directamente al cliente)
7) Solicitud autenticación simple hacia servidor web interno (Credenciales por defecto se proporcionaran directamente al cliente)
9) Acceso hacia servidor web interno https://localhost.com/token-estatico







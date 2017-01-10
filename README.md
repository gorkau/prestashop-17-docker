# prestashop-17-docker
Paquete para crear un entorno para PrestaShop 1.7 con PHP7 y Nginx.

## Requisitos

* Docker: https://www.docker.com/
* Docker Compose: https://docs.docker.com/compose/install/

## Configuración previa

(NOTA: Estas instrucciones están escritas pensando en un entorno Linux (Ubuntu) pero no sería complicado adaptarlas a Mac o Windows).

Deberás editar el fichero docker-compose.yml para ajustarlo a tu forma de trabajar:

En el servicio _nginx-prestashop_ (sección nginx-prestashop):

* Cambia el puerto 80 por el que quieras usar (si no tienes ningún otro servidor web lo normal es usar el puerto 80). Si tienes el puerto 80 ocupado puedes usar, por ejemplo el 81. En ese caso cambia "80:80" por "81:80".
* Cambia el volumen por la ruta donde quieras instalar PrestaShop. Si lo tienes, por ejemplo, en /var/www/prestashop deberías cambiar /home/gorka/webs/prestashop-1.7 por /var/www/prestashop.

En el servicio _php_ (sección php):

* Cambia el volumen por la ruta donde quieras instalar PrestaShop. Si lo tienes, por ejemplo, en /var/www/prestashop deberías cambiar /home/gorka/webs/prestashop-1.7 por /var/www/prestashop.

## Instalación 

### Descarga PrestaShop

Descarga el PrestaShop y descomprime el fichero zip en la carpeta donde quieras instalarlo. Deberías tener tres ficheros:

* prestahop.zip
* index.php
* Install_PrestaShop.html

### Instalación del entorno (servidor Nginx, PHP y MySQL)

Una vez has modificado el fichero docker-compose.yml y estén instalador Docker y Docker Compose descarga este paquete. No es necesario que lo descargues en la carpeta donde vayas a instalar PrestaShop.

Para descargarlo puedes hacer, por ejemplo:

git clone https://github.com/gorkau/prestashop-17-docker.git

Una vez descargado el siguiente paso es instalar. Desde la carpeta del paso anterior donde has descargado el fichero ejecuta el comando:

docker-compose up -d

(NOTA: Cuando reinicies el navegador tendrás que volver a ejecutar este comando desde la carpeta donde tengas el fichero docker-compose.yml).

Ahora abre el navegador y entra en la dirección:

http://localhost

Si has usado un puerto diferente del 80 deberás ir a (en caso de usar el 83):

http://localhost:83

(NOTA: Si usas un puerto distinto del 80, si en algún momento ves el mensaje "Not found" comprueba que no falte el puerto).

### Instalación de PrestaShop

Ahora basta con seguir las instrucciones para la instalación.

(NOTA: Si el instalador se queda bloqueado en la barra de progreso y ves que se repite una y otra vez será que tienes un problema de permisos, revísalo).

Los datos de acceso a la base de datos que tendrás que usar son:

Dirección del servidor de base de datos: db
Nombre de la base de datos: prestashop
Sistema de acceso de la base de datos: root
Contraseña de la base de datos: secret
Prefijo de las tablas: ps_



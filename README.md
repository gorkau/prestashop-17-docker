# prestashop-17-docker
Paquete para crear un entorno para PrestaShop 1.7 con PHP7 y Nginx.

## Requisitos

* Docker: https://www.docker.com/
* Docker Compose: https://docs.docker.com/compose/install/

## Configuración previa

(NOTA: Estas instrucciones están escritas pensando en un entorno Linux (Ubuntu) pero no sería complicado adaptarlas a Mac o Windows).

Deberás editar el fichero docker-compose.yml para ajustarlo a tu forma de trabajar:

En el servicio _nginx-prestashop_ (sección nginx-prestashop):

* Cambia el puerto 83 por el que quieras usar (si no tienes ningún otro servidor web lo normal es usar el puerto 80. En ese caso cambia "83:80" por "80:80".
* Cambia el volumen por la ruta donde tengas el instalador de PrestaShop. Si lo tienes, por ejemplo, en /var/www/prestashop deberías cambiar /home/gorka/webs/prestashop-1.7 por /var/www/prestashop.

En el servicio _php_ (sección php):

* Cambia el volumen por la ruta donde tengas el instalador de PrestaShop. Si lo tienes, por ejemplo, en /var/www/prestashop deberías cambiar /home/gorka/webs/prestashop-1.7 por /var/www/prestashop.

## Instalación 

Una vez has modificado el fichero docker-compose.yml y estén instalador Docker y Docker Compose descarga este paquete. No es necesario que lo descargues en la carpeta donde vayas a instalar PrestaShop.

Para descargarlo puedes hacer, por ejemplo:

----
git clone https://github.com/gorkau/prestashop-17-docker.git
----

Una vez descargado el siguiente paso es instalar. Desde la carpeta del paso anterior donde has descargado el fichero ejecuta el comando:

docker-compose up -d

Ahora abre el navegador y entra en la dirección:

http://localhost

Si has usado un puerto diferente del 80 deberás ir a (en caso de usar el 83):

http://localhost:83

(NOTA: Si usas un puerto distinto del 80, si en algún momento ves el mensaje "Not found" comprueba que no falte el puerto).


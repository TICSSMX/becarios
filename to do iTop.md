# Instalacion de iTop 2.7.1
***
Este es un documento que servira de guia para la instalación de iTop ver 2.7.1
en el sistema ubuntu.

**-----Requerimientos minimos del SO para instalar itop-----**

```
Los comando mas usados seran
sudo apt-get install
sudo apt-get upgrate
sudo apt-get update

```

***

## Pre-requisitos necesarios para la instalación
***
```
-Servidor web apache2
-Base de datos Msql ver.8.0
-Lenguaje php ver.7.4
```
**Si va a instalar otra versión de iTop revise los requerimientos en la documentación oficial**
***
**--------Permisos de usuario---------**
### Instalación del servidor apache
***

```
apt-get install apache2

```
***

### Instalacion de Mysql y sus parametros

***
```
apt-get install mysql-server

```

***

### Instalación de php 7.4
***

```
apt-get install php php-mysql php-ldap php-cli php-soap php-json graphviz
apt-get install php-xml php-gd php-zip libapache2-mod-php php-mbstring


```
***

### Creación de usuario y contraseña para mysql
***
**--------Entrar con usuario root a mysql, errores de sintaxis por la version de mysql---------**

```
GRANT ALL PRIVILEGES ON *.* TO 'iTop'@'%' IDENTIFIED BY 'some_password';
FLUSH PRIVILEGES;

```
***

### Modificación del archivo php.ini
***
**--------Donde se encuentra ubicado ese archivo?---------**

```
memory_limit = 256M 
max_input_vars = 5000

```
***
### Modificación del archivo my.vnf
***
**--------Donde se encuentra ubicado ese archivo?, verificar las variables por la version de mysql---------**

```
innodb_buffer_pool_size = 512M
query_cache_size = 32M
query_cache_limit = 1M
innodb_default_row_format = DYNAMIC
innodb_large_prefix = true
```
***
### Instalación de iTop
*** 
** Para descargar el archivo de iTop y descomprimirlo se debe estar en la ruta var/www/html**
**--------herramienta necesaria para descomprimir zip---------**
```
sudo wget https://sourceforge.net/projects/itop/files/itop/2.7.1/iTop-2.7.1-5896.zip
sudo unzip iTop-2.7.1-5896.zip
```

**--------Mas informacion del manejo de errores---------**

***
**SE INGRESA LA IP DE NUESTRA MAQUINA VIRTUAL (10.0.0.29/web) PARA PODER ACCEDER A LA PANTALLA DE INSTALACION DE ITOP, LO MAS SEGURO ES QUE APAREZCAN 5 ERRORES DE CARPETAS QUE NO TIENEN PERMISOS DE ESCRITURA Y QUE NO EXISTEN.
SE DEBERAN CREAR EN VAR/WWW/HTML/WEB**


**Ejemplo**
```PARA CREAR LA CARPETA ES
sudo mkdir log

PARA PERMISOS ES
sudo chmod –R 777 log
```

**--------  		---------**


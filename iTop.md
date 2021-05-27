# Instalacion de iTop 2.7.1
***
Este es un documento que servira de guia para la instalación de iTop ver 2.7.1
en el sistema ubuntu.

```
Los requerimientos minimos que necesita nuestro equipo son :
1.- Ubuntu 20.04.2
2.- 2 CPU
3.- 4Gb de Memoria RAM
4.- 16Gb de Memoria HDD

```
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

### Instalación del servidor apache
***

```
sudo apt-get install apache2

```
***

### Instalacion de Mysql y sus parametros

***
```
sudo apt-get install mysql-server

```

***

### Instalación de php 7.4
***

```
sudo apt-get install php php-mysql php-ldap php-cli php-soap php-json graphviz
sudo apt-get install php-xml php-gd php-zip libapache2-mod-php php-mbstring


```
***
### Inicio de la configuracion de Mysql
***
```
Para poder empezar hacer la preparacion de mysql tenemos que ingresar el siguiente comando.
-sudo mysql_secure_installation
Se abrira un scrip donde pedira una contraseña para el usuario root pero al no tener presione ENTER.
-Seguido pedira que ingrese una contraseña para acceer a mysql.
-Confirme la contraseña para poder proseguir.
-Habilite la opción "Permitir el acceso solo desde localhost para la cuenta root."
-Niegue las siguientes opciones "acceso anónimo." y "base de datos de test, accesible por todos los usuarios, incluidos los anónimos, y eliminar los privilegios que permiten a cualquier usuario acceder a las bases de datos con nombres que empiezan por test_."

Una vez hecho esto escriba exit.

```
***

### Creación de usuario y contraseña para mysql
***
```
El siguiente paso para nuestro mysql sera crear un usuario y contraseño para acceder a nuestra base de datos una vez ya instalago itop.(la contraseña generada anteriormente solo es para poder acceder a la consola de mysql).

**Para ingresar a la consola de mysql escriba:**
sudo mysql -u root -p

Una vez dentro escriba los siguientes comando

create database itop;
create user 'itop'@'localhost' IDENTIFIED BY 'Acceso2021!';
GRANT ALL ON itop.* TO 'itop'@'localhost';
flush privileges;

Una vez hecho esto escriba exit.

```
***

### Modificación del archivo php.ini
***
```
Para acceer a este archivo dirijase a la ruta etc/php/7.4/apache2
Para poder ingresar al archivo y modificarlo escriba
-sudo vi php.ini

memory_limit = 256M 
max_input_vars = 5000

Guarde los cambios y salga

```
***
### Modificación del archivo my.cnf
***
Para acceer a este archivo dirijase a la ruta etc/mysql
Para poder ingresar al archivo y modificarlo escriba
-sudo vi my.cnf

```
innodb_buffer_pool_size = 512M
query_cache_size = 32M
query_cache_limit = 1M
innodb_default_row_format = DYNAMIC
innodb_large_prefix = true
```
Guarde los cambios y salga
***
### Instalación de iTop
*** 
** Para descargar el archivo de iTop y descomprimirlo se debe estar en la ruta var/www/html
Y obterner la herramienta unzip con el comando:
-sudo apt-get install unzip
**
	
```
sudo wget https://sourceforge.net/projects/itop/files/itop/2.7.1/iTop-2.7.1-5896.zip
sudo unzip iTop-2.7.1-5896.zip
```
***
**SE INGRESA LA IP DE NUESTRA MAQUINA VIRTUAL (10.0.0.29/web) PARA PODER ACCEDER A LA PANTALLA DE INSTALACION DE ITOP, LO MAS SEGURO ES QUE APAREZCAN 5 ERRORES DE CARPETAS QUE NO TIENEN PERMISOS DE ESCRITURA Y QUE NO EXISTEN.
SE DEBERAN CREAR EN VAR/WWW/HTML/WEB
Los cinco errores describiran el nombre de las carpetas que no tienen los permisos suficientes o no existen por lo cual no se puede proseguir con la sinstalacion de itop.
Si el mensaje de error dice que no exite la carpeta y no tiene permisos escriba los dos siguientes comando

si solo dice que no tiene permisos solo escriba el ultimo comando con el nombre de la carpeta.**


**Ejemplo**
```PARA CREAR LA CARPETA ES
sudo mkdir log

PARA PERMISOS ES
sudo chmod –R 777 log
```


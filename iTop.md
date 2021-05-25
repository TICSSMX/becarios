# Instalacion de iTop 2.7.1
***
Este es un documento que servira de guia para la instalación de iTop ver 2.7.1
en el sistema ubuntu.

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
```
GRANT ALL PRIVILEGES ON *.* TO 'iTop'@'%' IDENTIFIED BY 'some_password';
FLUSH PRIVILEGES;

```
***

### Modificación del archivo php.ini
***
```
memory_limit = 256M 
max_input_vars = 5000

```
***
### Modificación del archivo my.vnf
***
```
innodb_buffer_pool_size = 512M
query_cache_size = 32M
query_cache_limit = 1M
innodb_default_row_format = DYNAMIC
innodb_large_prefix = true
```
***


Odoo con SSL usando Docker
==========================

Este proyecto detalla la implementación de Odoo con SSL utilizando Docker y Docker Compose. El enfoque utiliza Nginx como proxy inverso y Certbot para la gestión de certificados SSL.

1\. Creación del Directorio del Proyecto
----------------------------------------

Inicialmente, crea un nuevo directorio para el proyecto en tu servidor:

```bash
mkdir odoo-project
cd odoo-project`
```


2\. Crear Archivo Docker Compose YAML
-------------------------------------

En el directorio del proyecto, crea un archivo `docker-compose.yml`:

```bash
nano docker-compose.yml`
```

3\. Creación de Configuración de ODOO
-------------------------------------

Crea la configuración personalizada de Odoo:

```bash
mkdir -p etc/odoo
nano etc/odoo/odoo.conf
```

Incluye la configuración de la base de datos y otros parámetros relevantes en `odoo.conf`.

4\. Configurar NGINX
--------------------

Crea y configura el archivo predeterminado de Nginx:


```bash 
mkdir -p nginx/conf

nano nginx/conf/default.conf
```

Pega la configuración necesaria para dirigir el tráfico hacia Odoo y manejar las solicitudes SSL.

5\. Implementación de Odoo con Docker
-------------------------------------

Ejecuta los contenedores con:


```bash
docker-compose up -d
```

Usa `docker-compose ps` para verificar el estado de los contenedores.

6\. Configurar SSL para Odoo en Docker
--------------------------------------

Edita `nginx/conf/default.conf` para configurar la redirección HTTPS y especifica los certificados SSL.

```bash

sudo nano nginx/conf/default.conf
```

Realiza los cambios necesarios y reinicia el servicio Nginx:

```bash
docker-compose restart nginx
```

7\. Configurar Odoo
-------------------

Visita tu dominio en un navegador para configurar la base de datos y el usuario administrador de Odoo.

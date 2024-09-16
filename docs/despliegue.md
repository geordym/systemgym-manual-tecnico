# Despliegue de la Aplicación SystemGYM (Spring Boot / Angular / MySQL)

Este documento explica cómo desplegar la aplicación **SystemGYM**, la cual tiene un backend en **Spring Boot**, un frontend en **Angular**, y utiliza **MySQL** como base de datos. Asumimos que ya cuentas con:

- El archivo **`backend.jar`** generado por Spring Boot.
- Los archivos de construcción (`build`) de Angular.
- La base de datos **MySQL** ya creada y configurada.

## 1. Requisitos Previos

Antes de comenzar, asegúrate de que el servidor tenga instalados los siguientes programas:

- **Java 11 o superior** (JDK o JRE)
- **Node.js** (si decides servir el frontend con un servidor Node.js)
- **Nginx** o **Apache** (para servir los archivos estáticos del frontend)
- **MySQL** (el servicio debe estar corriendo)

## 2. Configuración de la Base de Datos MySQL

### Asegúrate de que la base de datos **MySQL** esté corriendo y configurada correctamente:

1. Verifica que el servicio de **MySQL** esté iniciado:
   ```bash
   sudo systemctl start mysql

### spring.datasource.url=jdbc:mysql://localhost:3306/systemgym_db
### spring.datasource.username=usuario_mysql
### spring.datasource.password=contraseña_mysql
### spring.jpa.hibernate.ddl-auto=update


3. Despliegue del Backend (Spring Boot)

    - Sube el archivo backend.jar al servidor. Puedes hacerlo usando SCP o cualquier otro método:

    - bash

- scp /ruta/local/backend.jar usuario@servidor:/ruta/remota/backend.jar

### Ejecuta el archivo JAR en el servidor:

- bash

### java -jar /ruta/remota/backend.jar

- Ejecuta el JAR en segundo plano utilizando nohup para que el proceso continúe en ejecución incluso si cierras la sesión SSH:

- bash

### nohup java -jar /ruta/remota/backend.jar > backend.log &

### Verifica que el servidor esté corriendo accediendo a la URL:

bash

   - http://<ip-servidor>:8080

## Despliegue del Frontend (Angular)
### Opción 1: Servir con Nginx

- Sube los archivos de construcción de Angular a la carpeta donde Nginx servirá los archivos:

- bash

- scp -r /ruta/local/dist/angular/ usuario@servidor:/var/www/systemgym

- Configura Nginx para servir la aplicación Angular. Edita el archivo de configuración de Nginx:

bash

- sudo nano /etc/nginx/sites-available/default

Configura el bloque server en Nginx:

nginx

server {
    listen 80;
    server_name <ip-servidor>;

    location / {
        root /var/www/systemgym;
        index index.html;
        try_files $uri $uri/ /index.html;
    }
}

### Reinicia Nginx para aplicar los cambios:

bash

- sudo systemctl restart nginx

- Verifica que el frontend esté corriendo accediendo a la URL:

bash

  ###  http://<ip-servidor>/

5. Conexión entre Backend y Frontend

Asegúrate de que la API del backend esté configurada correctamente en los archivos de configuración de Angular, generalmente en environment.ts:

export const environment = {
  production: true,
  apiUrl: 'http://<ip-servidor>:8080/api'
};

Si es necesario, ajusta las configuraciones CORS en el backend para permitir que el frontend se comunique con la API.


### Reiniciar Nginx: Si realizas algún cambio en la configuración de Nginx, asegúrate de reiniciar el servicio:


    sudo systemctl restart nginx

7. Consideraciones de Seguridad

    Configura un cortafuegos para limitar los puertos expuestos públicamente (como 8080 para el backend o 80/443 para el frontend).

    Usa HTTPS: Si estás desplegando en un entorno de producción, asegúrate de configurar HTTPS utilizando certbot y Let's Encrypt en Nginx.
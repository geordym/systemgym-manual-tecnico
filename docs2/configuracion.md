### Configuración del Entorno

1. **Angular**
   - **APIURL**: En el archivo de configuración de Angular, define la URL base del backend.
     - Abre el archivo `src/environments/environment.ts`.
     - Configura la URL del API:
       ```typescript
       export const environment = {
         production: false,
         apiUrl: 'http://localhost:8080/api'
       };
       ```

2. **Spring Boot**
   - **Archivo de Configuración**: El archivo de configuración se encuentra en `src/main/resources/application.properties`

### Configuración del Sistema

1. **Base de Datos**
   - **URL**: La URL de la base de datos MySQL.
     ```properties
     * spring.datasource.url=jdbc:mysql://localhost:3306/sistema_gimnasio?createDatabaseIfNotExist=true
     ```
   - **Credenciales**: Usuario y contraseña de la base de datos.
     ```properties
     * spring.datasource.username=root
     * spring.datasource.password=
     ```

2. **Servicios Externos**
   - **SMTP para Email (Gmail)**
     - Configura las credenciales de Gmail para el envío de correos.
     ```properties
     * smtp.gmail.user=
     * smtp.gmail.password=
     ```

3. **Migración de Base de Datos (Flyway)**
     * spring.flyway.enabled=true
     * spring.flyway.locations=classpath:db/migration
     * spring.flyway.url=jdbc:mysql://localhost:3306/sistema_gimnasio
     * spring.flyway.user=root
     * spring.flyway.password=
     * spring.flyway.group=true
     * spring.flyway.clean-disabled=true
     * spring.flyway.validate-on-migrate=true
     * logging.level.org.flywaydb=debug
     ```

4. **Documentación API (Swagger)**
   - **Habilitar Swagger UI**
     ```properties
     * springdoc.api-docs.enabled=true
     * springdoc.swagger-ui.enabled=true
     * springdoc.swagger-ui.path=/doc/swagger-ui.html
     ```

### Variables de Entorno y Archivos de Configuración

1. **Variables de Entorno**
   - **Angular**
     - `APIURL`: Configurado en `src/environments/environment.ts`.

   - **Spring Boot**
     - `spring.jpa.hibernate.ddl-auto=none`
     - `spring.datasource.url=jdbc:mysql://localhost:3306/sistema_gimnasio?createDatabaseIfNotExist=true`
     - `spring.datasource.username=root`
     - `spring.datasource.password=`
     - `spring.datasource.driver-class-name=com.mysql.cj.jdbc.Driver`
     - `spring.jpa.show-sql=true`
     - `spring.flyway.enabled=true`
     - `spring.flyway.locations=classpath:db/migration`
     - `spring.flyway.url=jdbc:mysql://localhost:3306/sistema_gimnasio`
     - `spring.flyway.user=root`
     - `spring.flyway.password=`
     - `spring.flyway.group=true`
     - `spring.flyway.clean-disabled=true`
     - `spring.flyway.validate-on-migrate=true`
     - `logging.level.org.flywaydb=debug`
     - `springdoc.api-docs.enabled=true`
     - `springdoc.swagger-ui.enabled=true`
     - `springdoc.swagger-ui.path=/doc/swagger-ui.html`
     - `smtp.gmail.user=`
     - `smtp.gmail.password=`

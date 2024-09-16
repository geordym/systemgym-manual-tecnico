## Instalación

### Instrucciones para la Instalación del Sistema

1. **Preparar el Entorno**
   - Asegúrate de que todos los prerequisitos estén instalados (Java 17, Node.js, Angular CLI, MySQL, etc.).

2. **Clonar el Repositorio**
   - Clona el repositorio del proyecto desde el sistema de control de versiones (por ejemplo, GitHub):
     ```bash
     git clone https://github.com/geordym/backend-systemgym
     ```
   - Accede al directorio del proyecto:
     ```bash
     cd backend-systemgym
     ```

3. **Configurar la Base de Datos**
   - Crea una base de datos en MySQL para el sistema, la BD por default debera llamarse "sistema_gimnasio"
   - No necesitas importar ningun SQL, el sistema implementa flyway en su funcionamiento y este se encarga de inyectar todo lo necesario en la base de datos para su funcionamiento
     

4. **Configurar el Backend**
   - Abre el archivo `application.properties` en el directorio `src/main/resources`.
   - Configura las propiedades de la base de datos, el servidor de correo y otros parámetros necesarios:
     ```properties
     * spring.datasource.url=jdbc:mysql://localhost:3306/sistema_gimnasio
     * spring.datasource.username=your_db_username
     * spring.datasource.password=your_db_password
     * spring.mail.host=smtp.gmail.com
     * spring.mail.port=587
     * spring.mail.username=your_email@gmail.com
     * spring.mail.password=your_email_password
     ```

5. **Configurar el Frontend**
   - Abre el archivo `src/environments/environment.ts` (o `environment.prod.ts` para producción).
   - Configura la URL del backend:
     ```typescript
     export const environment = {
       production: false,
       apiUrl: 'http://localhost:8080/api'
     };
     ```

### Instalación de Dependencias

1. **Backend**
   - Navega al directorio del backend y asegúrate de que Maven esté instalado.
   - Instala las dependencias del backend con el siguiente comando:
     ```bash
     ./mvnw install
     ```

2. **Frontend**
   - Navega al directorio del frontend.
   - Instala las dependencias de Angular utilizando npm:
     ```bash
     npm install
     ```

---

### Configuración Inicial

1. **Iniciar el Backend**
   - Navega al directorio del backend (`/backend_systemgym`) y ejecuta el siguiente comando para iniciar el servidor Spring Boot:
     ```bash
     ./mvnw spring-boot:run
     ```
   - Verifica que el servidor esté funcionando accediendo a `http://localhost:8080`.

2. **Iniciar el Frontend**
   - Navega al directorio del frontend (`/frontend_systemgym`) y ejecuta el siguiente comando para iniciar el servidor de desarrollo Angular:
     ```bash
     ng serve
     ```
   - Accede a la aplicación en `http://localhost:4200`.




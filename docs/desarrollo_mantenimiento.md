
### Estructura del Código Fuente

#### Frontend (Angular)

1. **Estructura de Directorios**
   - `src/pages/`
     - Contiene las páginas del sistema, como:
       - `factura/`
       - `inscripcion/`
       - `membresias/`
   - `src/services/`
     - Contiene los servicios para interactuar con el backend, como:
       - `facturaService/`
       - `authService/`
   - `src/interfaces/`
     - Define las interfaces utilizadas en el sistema, como:
       - `Factura/`
       - `Pago/`
       - `Cliente/`
   - `src/app.routing.module.ts`
     - Configura las rutas del sistema para la navegación entre páginas.

2. **Plantilla AdminLTE**
   - Carpeta adicional para los archivos relacionados con la plantilla AdminLTE, utilizados para la interfaz de usuario.

#### Backend (Spring Boot)

1. **Estructura de Paquetes**
   - **Controlador** (`Controller`)
     - Maneja las solicitudes HTTP y coordina la respuesta utilizando los servicios.
   - **DTO** (`Data Transfer Object`)
     - Define los objetos de transferencia de datos entre la capa de presentación y la capa de negocio.
   - **Mapper**
     - Transforma los datos entre las entidades y los DTOs.
   - **ExceptionHandler**
     - Maneja las excepciones globales y proporciona respuestas de error estandarizadas.
   - **Services**
     - Contiene la lógica de negocio del sistema.
   - **Repositories**
     - Interactúa con la base de datos para realizar operaciones CRUD.
   - **Seeder**
     - Proporciona datos iniciales para la base de datos, como membresías y usuarios de prueba.
   - **Enums**
     - Define enumeraciones utilizadas en el sistema.
   - **Configuration**
     - Configura aspectos específicos del sistema, como conexiones a la base de datos y seguridad.

2. **Flujo de Datos**
   - El **Controller** recibe las solicitudes y llama a los **Services**.
   - Los **Services** realizan la lógica de negocio y utilizan los **Repositories** para interactuar con la base de datos.
   - Los datos se transforman utilizando los **Mapper** y se envían al **DTO**.
   - Los **DTO** se devuelven al **Controller**, que responde a la solicitud HTTP.


### Procedimientos para la Actualización del Sistema

1. **Actualización del Frontend (Angular)**
   - **Obtener la Última Versión**: Asegúrate de tener la última versión del código fuente del frontend.
   - **Instalar Dependencias**: Ejecuta `npm install` para instalar las dependencias actualizadas.
   - **Compilar y Construir**: Ejecuta `ng build` para compilar el proyecto.
   - **Desplegar**: Copia los archivos generados en la carpeta `dist/` al servidor de producción.

2. **Actualización del Backend (Spring Boot)**
   - **Obtener la Última Versión**: Asegúrate de tener la última versión del código fuente del backend.
   - **Actualizar Dependencias**: Actualiza las dependencias en el archivo `pom.xml` o `build.gradle`.
   - **Compilar y Construir**: Ejecuta `mvn clean install` o `./gradlew build` para compilar el proyecto.
   - **Desplegar**: Despliega el archivo JAR o WAR generado al servidor de producción.

3. **Actualización de la Base de Datos**
   - **Migraciones de Flyway**: Asegúrate de que las migraciones de la base de datos estén actualizadas.
   - **Ejecutar Migraciones**: Si es necesario, ejecuta las migraciones de Flyway para aplicar cambios en la base de datos.

4. **Verificación y Pruebas**
   - **Verificar Funcionalidad**: Realiza pruebas para verificar que el sistema funcione correctamente después de la actualización.
   - **Corregir Errores**: Resuelve cualquier error que aparezca durante las pruebas.


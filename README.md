
## Ejecución con Docker

### Build de la imagen Docker

Desde la carpeta `Springboot-API-REST-DESPACHO`:

```sh
docker build -t despacho-backend .
```

Luego, ejecuta el contenedor con las variables de entorno necesarias para conectarse a la base de datos.
# despacho-devops-ev2

Microservicio Spring Boot para la gestión de despachos de productos. Permite registrar, consultar, actualizar y eliminar información de despachos, integrándose con otros servicios del sistema.

## Características

- API RESTful para operaciones CRUD de despachos.
- Conexión a base de datos MySQL.
- Documentación interactiva con Swagger.
- Configuración lista para desarrollo local y despliegue en contenedores.

## Requisitos previos

- Java 21
- Maven 3.8+
- MySQL 8+
- Git

## Instalación y ejecución

1. **Clona el repositorio:**
   ```sh
   git clone https://github.com/tu_usuario/despacho-devops-ev2.git
   cd despacho-devops-ev2

   2. **Configura la base de datos:**
   - Crea la base de datos y el usuario en MySQL:
     ```sql
     CREATE DATABASE IF NOT EXISTS despachos_db CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
     CREATE USER IF NOT EXISTS 'despachos_user'@'localhost' IDENTIFIED WITH mysql_native_password BY 'tu_contraseña';
     GRANT ALL PRIVILEGES ON despachos_db.* TO 'despachos_user'@'localhost';
     FLUSH PRIVILEGES;
     ```
   - Edita `src/main/resources/application.properties` con tus credenciales.

3. **Compila y ejecuta la aplicación:**
   ```sh
   ./mvnw clean install
   ./mvnw spring-boot:run

   3. **Compila y ejecuta la aplicación:**
   ```sh
   ./mvnw clean install
   ./mvnw spring-boot:run


---

```markdown
4. **Accede a la documentación Swagger:**
   - [http://localhost:8080/swagger-ui.html](http://localhost:8080/swagger-ui.html)

## Endpoints principales

- `GET /api/despachos` — Listar todos los despachos
- `GET /api/despachos/{id}` — Obtener un despacho por ID
- `POST /api/despachos` — Crear un nuevo despacho
- `PUT /api/despachos/{id}` — Actualizar un despacho existente
- `DELETE /api/despachos/{id}` — Eliminar un despacho

## Variables de configuración

Edita el archivo `application.properties` para ajustar la conexión a la base de datos y el puerto del servidor.

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/despachos_db?useSSL=false&serverTimezone=UTC&createDatabaseIfNotExist=true&allowPublicKeyRetrieval=true
spring.datasource.username=despachos_user
spring.datasource.password=tu_contraseña
server.port=8080

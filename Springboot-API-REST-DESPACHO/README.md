# Springboot-API-REST-DESPACHO

Microservicio Spring Boot para la gestión de despachos de productos. Permite registrar, consultar, actualizar y eliminar información de despachos, integrándose con otros servicios del sistema.

## Características
- API RESTful para operaciones CRUD de despachos.
- Conexión a base de datos MySQL.
- Documentación Swagger.
- Listo para desarrollo local y despliegue en Docker.


## Requisitos previos
- Java 21
- Maven 3.8+
- Docker
- Git

## Ejecución con Docker

1. Construye la imagen Docker:
   ```sh
   docker build -t despacho-backend .
   ```
2. Ejecuta el contenedor:
   ```sh
   docker run -d -p 8081:8081 \
     -e SPRING_DATASOURCE_URL="<jdbc_url>" \
     -e SPRING_DATASOURCE_USERNAME="<usuario>" \
     -e SPRING_DATASOURCE_PASSWORD="<contraseña>" \
     despacho-backend
   ```
   El backend estará disponible en: [http://localhost:8081](http://localhost:8081)

## Variables de entorno importantes
Debes definir las variables de entorno para la conexión a la base de datos al ejecutar el contenedor:
- `SPRING_DATASOURCE_URL`
- `SPRING_DATASOURCE_USERNAME`
- `SPRING_DATASOURCE_PASSWORD`

## Endpoints principales
- `GET /api/despachos` — Listar todos los despachos
- `GET /api/despachos/{id}` — Obtener un despacho por ID
- `POST /api/despachos` — Crear un nuevo despacho
- `PUT /api/despachos/{id}` — Actualizar un despacho existente
- `DELETE /api/despachos/{id}` — Eliminar un despacho

## Documentación Swagger
- [http://localhost:8081/swagger-ui.html](http://localhost:8081/swagger-ui.html)

## Notas
- Si ves un error 404 en la raíz (`/`), es normal: la API no sirve archivos estáticos, solo endpoints REST.
- Asegúrate de que el puerto 3306 esté libre antes de levantar los servicios.

## Despliegue y DevOps
- Incluye Dockerfile y docker-compose.yml listos para producción.
- Puedes usar este repositorio en pipelines CI/CD para construir y desplegar automáticamente.

---

## Cómo contribuir
1. Haz tus cambios en una rama nueva.
2. Realiza commit con mensajes claros.
3. Haz push y crea un Pull Request.

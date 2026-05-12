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
- Docker y Docker Compose
- Git

## Ejecución con Docker Compose

1. Construye la imagen y levanta los servicios:
   ```sh
   docker-compose up --build
   ```
2. El backend estará disponible en: [http://localhost:8081](http://localhost:8081)

## Variables de entorno importantes
Las credenciales y URL de la base de datos se configuran automáticamente en docker-compose.yml.

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

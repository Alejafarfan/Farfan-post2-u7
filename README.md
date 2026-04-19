# API REST de Productos - Spring Boot

API REST CRUD para gestión de productos usando Spring Boot y ResponseEntity con códigos HTTP correctos para cada operación.

## Tecnologías
- Java 17
- Spring Boot 3.5.13
- Maven

## Estructura del proyecto
    api-productos/
        src/main/java/com/universidad/apiproductos/
        
        ApiProductosApplication.java        # Clase principal, punto de entrada
        model/
            Producto.java                   # Modelo con id, nombre, descripcion, precio
        service/
            ProductoService.java            # Lógica CRUD con almacenamiento en memoria
        controller/
            ProductoApiController.java      # Endpoints REST con códigos HTTP correctos
            GlobalExceptionHandler.java     # Manejador global de errores en JSON
        
        src/main/resources/
            application.properties             # Configuración del servidor
    pom.xml                                # Dependencias del proyecto

## Qué hace cada componente

- Producto.java: clase modelo con los atributos del producto. Tiene getters y setters requeridos por Jackson para convertir entre Java y JSON.
- ProductoService.java: simula una base de datos usando un LinkedHashMap en memoria. Expone los métodos obtenerTodos, buscarPorId, guardar y eliminar.
- ProductoApiController.java: controlador REST que maneja las peticiones HTTP y retorna ResponseEntity con el código HTTP correcto para cada operación.
- GlobalExceptionHandler.java: captura excepciones RuntimeException y retorna un JSON con el mensaje de error en lugar de la página HTML de error por defecto.

## Cómo ejecutar

1. Clonar el repositorio:
   git clone https://github.com/Alejafarfan/Farfan-post2-u7.git

2. Abrir en IntelliJ IDEA

3. En la terminal ejecutar:
   ./mvnw spring-boot:run

4. La API estará disponible en: http://localhost:8080/api/productos

## Endpoints disponibles
- GET /api/productos: Obtener todos los productos
- GET /api/productos/{id}: Obtener un producto por ID
- POST /api/productos: Crear un nuevo producto (enviar JSON con nombre, descripcion, precio)
- PUT /api/productos/{id}: Actualizar un producto existente (enviar JSON con nombre, descripcion, precio)
- DELETE /api/productos/{id}: Eliminar un producto por ID

## captura de pantalla de postman con las operaciones CRUD
GET http://localhost:8080/api/productos
<img width="700" alt="get" src="https://res.cloudinary.com/dindlmikf/image/upload/v1776579912/Captura_de_pantalla_2026-04-19_012425_jmzozw.png">

POST http://localhost:8080/api/productos
<img width="700" alt="post" src="https://res.cloudinary.com/dindlmikf/image/upload/v1776580331/Captura_de_pantalla_2026-04-19_012908_frt9sm.png">

PUT http://localhost:8080/api/productos/3
<img width="700" alt="put" src="https://res.cloudinary.com/dindlmikf/image/upload/v1776580331/Captura_de_pantalla_2026-04-19_013104_gp4jan.png">
DELETE http://localhost:8080/api/productos/3
<img width="700" alt="delete" src="https://res.cloudinary.com/dindlmikf/image/upload/v1776580331/Captura_de_pantalla_2026-04-19_013117_tcq9s3.png">
<img width="700" alt="delete" src="https://res.cloudinary.com/dindlmikf/image/upload/v1776580331/Captura_de_pantalla_2026-04-19_013141_lrvzu6.png">

GET http://localhost:8080/api/productos/999
<img width="700" alt="get error" src="https://res.cloudinary.com/dindlmikf/image/upload/v1776580332/Captura_de_pantalla_2026-04-19_013151_tbf00f.png">


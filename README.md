# Foro Hub 

Foro Hub es una aplicación de foro diseñada para facilitar la comunicación y discusión entre usuarios. Esta aplicación permite a los usuarios crear tópicos, responder a los mismos y participar en discusiones.

<p align="center">
    <img src="https://github.com/Orliluq/ForoHub/assets/122529721/952e8461-2eac-4c28-8fd0-bb676e672528"/>
</p>


## Características ⚙️

- Registro y autenticación de usuarios.
- Creación, edición y eliminación de tópicos.
- Respuesta a tópicos existentes.
- Listado de usuarios y tópicos.
- Autenticación mediante JWT.

## Tecnologías utilizadas ⚒️

- Java
- Spring Boot
- Spring Security
- JWT (JSON Web Tokens)
- JPA (Java Persistence API)
- H2 Database (para desarrollo y pruebas)
- Postman (para pruebas de API)
- Swagger (para documentación de API)

## Estructura del proyecto 🖥️

- **Entities**: Clases de entidad que representan las tablas de la base de datos.
- **Dto**: Clases de Data Transfer Object utilizadas para transferir datos entre el cliente y el servidor.
- **Repository**: Interfaces que extienden JpaRepository para realizar operaciones CRUD en las entidades.
- **Service**: Clases de servicio que contienen la lógica de negocio.
- **Controller**: Clases de controlador que manejan las solicitudes HTTP.
- **Security**: Clases relacionadas con la configuración de seguridad y la autenticación.

## Instalación 🚧

Clona este repositorio:
```
git clone https://github.com/Orliluq/ForoHub.git
```

Navega al directorio del proyecto:
```
cd ForoHub
```
- Abre el proyecto en tu IDE favorito (por ejemplo, IntelliJ IDEA o Eclipse).
- Configuración
- Base de datos: MySQL 📈

<p align="center">
    <img src="https://github.com/Orliluq/ForoHub/assets/122529721/53acb33d-6597-4700-822e-b87425f69383"/>
</p>

Este proyecto está configurado para usar una base de datos H2 en memoria por defecto. Puedes cambiar la configuración de la base de datos en el archivo application.properties.

### Swagger 📊
Swagger está configurado para generar documentación de la API automáticamente. Puedes acceder a la interfaz de Swagger en la siguiente URL cuando el servidor esté en funcionamiento:
```
http://localhost:8080/swagger-ui/index.html
```
![swagger.png](hub%2Fswagger.png)

Ejecución
Para ejecutar la aplicación, utiliza el siguiente comando en la raíz del proyecto:
```
mvn spring-boot:run
```
La aplicación estará disponible en `http://localhost:8080`.

Endpoints principales:
- `/login`: Endpoint para autenticación de usuarios. Envía una solicitud POST con un JSON que contiene `username` y `password`.
- `/usuarios`: Endpoint para listar usuarios. Requiere autenticación mediante un token JWT.
- `/topicos`: Endpoint para manejar la creación, actualización y eliminación de tópicos.

### Ejemplos de solicitudes 📑

- Autenticación 🔐

Solicitud:
```
POST http://localhost:8080/login
```
Body:
```
{
    "username": "nombre_usuario",
    "password": "contraseña"
}
```
Respuesta:
```
{
    "token": "jwt_token_generado"
}
```
- Crear un tópico 📝

Solicitud:
```
GET http://localhost:8080/topico/topicos
```
Headers:
```
Authorization: Bearer jwt_token_generado
Content-Type: application/json
```
Body:
```
{
  "totalPages": 1,
  "totalElements": 3,
  "size": 3,
  "content": [
    {
      "id": 1,
      "title": "Temática de Ciencias Exactas",
      "message": "Exploración y comprensión de conceptos fundamentales en matemáticas, física, y química.",
      "status": "ACTIVO",
      "usuario_Id": 1,
      "curso": "Introducción a la Matemática",
      "date": "2024-07-01T08:00:00.000Z"
    },
    {
      "id": 2,
      "title": "Historia y Cultura",
      "message": "Estudio detallado de eventos históricos y desarrollo cultural a través de los tiempos.",
      "status": "ACTIVO",
      "usuario_Id": 2,
      "curso": "Civilización Antigua",
      "date": "2024-07-02T09:30:00.000Z"
    },
    {
      "id": 3,
      "title": "Arte y Diseño",
      "message": "Apreciación y creación artística, explorando diversas formas de expresión visual.",
      "status": "ACTIVO",
      "usuario_Id": 3,
      "curso": "Dibujo y Pintura",
      "date": "2024-07-03T11:00:00.000Z"
    }
  ],
  "number": 0,
  "sort": "asc",
  "first": true,
  "last": true,
  "numberOfElements": 3,
  "pageable": {
    "offset": 0,
    "sort": "asc",
    "paged": true,
    "unpaged": true,
    "pageNumber": 0,
    "pageSize": 3
  },
  "empty": false
}

```
## Contribuciones ⌨️
Las contribuciones son bienvenidas. Por favor, abre un issue para discutir el cambio que deseas realizar. Siéntete libre de hacer un fork del proyecto y enviar un pull request.

## Licencia 🚀
Este proyecto está licenciado bajo la Licencia MIT. Consulta el archivo LICENSE para más detalles.

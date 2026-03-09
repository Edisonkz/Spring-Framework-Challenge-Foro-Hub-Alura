
# 🎓 ForoHub

**ForoHub** es una API REST creada con Spring Framework que permite administrar un foro de discusión. Los usuarios pueden realizar operaciones de alta, consulta, modificación y baja de tópicos (CRUD). La API sigue el modelo REST, incluye validaciones, autenticación y autorización, y utiliza una base de datos relacional para almacenar la información.

## 🌟 Funcionalidades

- 📝 Alta de nuevos tópicos
- 📖 Listado de todos los tópicos
- 🔍 Consulta de un tópico por ID
- ✏️ Edición de tópicos
- 🗑️ Eliminación de tópicos
- ✔️ Validaciones de reglas de negocio
- 🔒 Seguridad y control de acceso

## 🛠️ Tecnologías

- Java 11
- Spring Boot
- Spring Data JPA
- Spring Security
- Hibernate
- H2 Database (desarrollo y pruebas)
- MySQL (producción)
- Maven

## 🚀 Instalación y Ejecución

### Requisitos previos

- JDK 11 o superior
- Maven
- MySQL (para producción)

### Configuración

1. Clona el repositorio:
    ```bash
    git clone https://github.com/Edisonkz/Spring-Framework-Challenge-Foro-Hub-Alura.git
    cd ForoHub
    ```

2. Configura la base de datos:

    - Para desarrollo y pruebas, se utiliza H2 Database por defecto.
    - Para producción, edita `src/main/resources/application.properties` con los datos de tu base MySQL.

    ```properties
    spring.datasource.url=jdbc:mysql://localhost:3306/forohub
    spring.datasource.username=tu-usuario
    spring.datasource.password=tu-contraseña
    spring.jpa.hibernate.ddl-auto=update
    ```

3. Compila y ejecuta la aplicación:

    ```bash
    mvn clean install
    mvn spring-boot:run
    ```

## 📚 Uso de la API

### Endpoints principales

- Crear tópico:
    ```http
    POST /api/topics
    ```
    Ejemplo de cuerpo JSON:
    ```json
    {
        "titulo": "Título del Tópico",
        "mensaje": "Contenido del Tópico",
        "autorId": 1
    }
    ```

- Listar todos los tópicos:
    ```http
    GET /api/topics
    ```

- Consultar un tópico por ID:
    ```http
    GET /api/topics/{id}
    ```

- Actualizar un tópico:
    ```http
    PUT /api/topics/{id}
    ```
    Ejemplo de cuerpo JSON:
    ```json
    {
        "titulo": "Nuevo Título del Tópico",
        "mensaje": "Nuevo Contenido del Tópico"
    }
    ```

- Eliminar un tópico:
    ```http
    DELETE /api/topics/{id}
    ```

### Seguridad

La API utiliza Spring Security para proteger los endpoints. Es necesario autenticarse para acceder a los recursos.

### Validaciones

- Todos los campos son obligatorios al crear o modificar un tópico.
- Los errores de validación se devuelven en la respuesta.

## 🤝 Cómo contribuir

1. Haz un fork del repositorio.
2. Crea una rama nueva (`git checkout -b feature/nueva-funcionalidad`).
3. Realiza tus cambios y haz commit (`git commit -m 'Agregar nueva funcionalidad'`).
4. Sube tu rama (`git push origin feature/nueva-funcionalidad`).
5. Abre un Pull Request.

## 📄 Licencia

Este proyecto está bajo la Licencia MIT. Consulta el archivo `LICENSE` para más información.

# Nombre del proyecto
PROYECTO="crud-estudiantes"

## Descripción
Proyecto de ejemplo para la Unidad 8: Persistencia con JPA/Hibernate. Permite realizar operaciones CRUD (Crear, Leer, Actualizar, Eliminar) sobre la entidad **Estudiante**, utilizando **Spring Boot**, **Spring Data JPA**, **Hibernate** y **MySQL**.

---

## Requisitos Previos
- Java 17 o superior
- MySQL 8.x instalado y en ejecución
- Maven 3.x (incluido en el wrapper de Spring Boot)
- IDE: IntelliJ IDEA o VS Code con soporte Java
- Conocimientos básicos de Spring Boot y JPA

---

## Configuración de MySQL
1. Iniciar sesión en MySQL:

\`\`\`bash
mysql -u root -p
\`\`\`

2. Crear base de datos y usuario:

\`\`\`sql
CREATE DATABASE estudiantes_db CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
CREATE USER 'appuser'@'localhost' IDENTIFIED BY 'apppass';
GRANT ALL PRIVILEGES ON estudiantes_db.* TO 'appuser'@'localhost';
FLUSH PRIVILEGES;
EXIT;
\`\`\`

---

## Configuración de \`application.properties\`
Ubicación: \`src/main/resources/application.properties\`

\`\`\`properties
# Conexión a MySQL
spring.datasource.url=jdbc:mysql://localhost:3306/estudiantes_db?useSSL=false&serverTimezone=UTC
spring.datasource.username=appuser
spring.datasource.password=apppass
spring.datasource.driver-class-name=com.mysql.cj.jdbc.Driver

# JPA / Hibernate
spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
spring.jpa.properties.hibernate.format_sql=true
spring.jpa.database-platform=org.hibernate.dialect.MySQL8Dialect

# Puerto del servidor
server.port=8080
\`\`\`

---

## Estructura del Proyecto

\`\`\`text
src/main/java/com/universidad/estudiantes/
├── EstudiantesApplication.java
├── controller/
│   └── EstudianteController.java
├── model/
│   └── Estudiante.java
├── repository/
│   └── EstudianteRepository.java
└── service/
    └── EstudianteService.java

src/main/resources/
├── application.properties
├── static/
│   └── capturas/
│       ├── lista.png
│       ├── formulario.png
│       ├── editar.png
│       └── eliminar.png
└── templates/
    └── estudiantes/
        ├── lista.html
        ├── formulario.html
        └── confirmar-eliminar.html
\`\`\`

---

## Ejecución del Proyecto

\`\`\`bash
./mvnw spring-boot:run
\`\`\`

Abrir en el navegador:

\`\`\`
http://localhost:8080/estudiantes
\`\`\`

---

## Capturas de Operaciones CRUD

1. **Tabla de Estudiantes**  
![Creacion de la tabla "estudiantes" creada por Hibernate](capturas\tablaestudiante.png)

2. **Crear Nuevo Estudiante**  
![Registrar estudiantes](capturas\registro.png)

3. **Estudiantes en MySql**  
![Tabla estudiantes](capturas\mysql.png)

4. **Editar Estudiante**  
![Estudiante editado](capturas\editar.png)

5. **Eliminar Estudiante**  
![Confirmación de eliminación](capturas\eliminar.png)


6. **Estudiante eliminado en la base de datos**  
![Estudiante eliminado](capturas\eliminado.png)

7. **Prueba de registrar correo existente**  
![Prueba de correo existente](capturas\error.png)
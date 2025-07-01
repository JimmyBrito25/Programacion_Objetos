# Sistema de Gestión de Libros en Go

Este proyecto es un sistema completo de gestión de libros digitales desarrollado con **Golang**, utilizando **GORM**, **Gorilla Mux** y **MySQL**. Permite registrar usuarios, autenticar, administrar libros, realizar compras, dejar valoraciones y visualizar una interfaz web moderna.

---

## Funcionalidades principales

### Backend API
- Registro de usuarios (`/register`)
- Inicio de sesión con JWT (`/login`)
- CRUD de libros (creación desde formulario y desde Postman)
- Comentarios y valoraciones por libro
- Cálculo de calificación promedio
- Compras protegidas con token

### Interfaz Web (HTML)
- Dashboard visual con lista de libros
- Página de detalles de cada libro (`/books/{id}`)
- Buscador por título o género (`/explore`)
- Formulario para agregar nuevos libros (`/books/new`)
- Navegación moderna con enlaces (Inicio, Mis libros, Mi cuenta, Explorar, etc.)

---

## Tecnologías y librerías usadas

- [Golang](https://golang.org/)
- [Gorilla Mux](https://github.com/gorilla/mux) – router web
- [GORM](https://gorm.io/) – ORM para MySQL
- [JWT](https://github.com/golang-jwt/jwt) – autenticación
- [html/template](https://pkg.go.dev/html/template) – plantillas HTML nativas
- MySQL (gestionado con Laragon)

## Estructura del proyecto

gestion_libros_final/
│
├── cmd/
│ └── main.go # Punto de entrada
│
├── internal/
│ ├── books/ # Módulo de libros
│ ├── users/ # Registro y login
│ ├── orders/ # Compras
│ ├── reviews/ # Comentarios y valoraciones
│ ├── database/ # Conexión a MySQL
│ └── config/ # Carga de variables de entorno
│
├── web/
│ └── templates/ # Archivos HTML
│
├── go.mod / go.sum # Dependencias
├── .env # Configuración de base de datos y JWT
└── README.md # Este documento

## Configuración del entorno

### Instalar dependencias

Asegúrate de tener Go instalado (1.20+ recomendado) y luego:
go mod tidy


## Configurar base de datos en Laragon
Crea una base de datos llamada ebook_system

Usa phpMyAdmin o HeidiSQL

Ejecuta el script SQL de estructura (estructura.sql) y datos (datos.sql)

## Configurar el archivo .env
Crea un archivo .env con este contenido:

DB_USER=root
DB_PASS=
DB_HOST=localhost
DB_NAME=ebook_system
JWT_SECRET=clave_super_segura

## Cómo ejecutar el servidor
Desde la raíz del proyecto:

go run cmd/main.go

## Verás en consola:
Conexión exitosa a MySQL
Servidor corriendo en http://localhost:8080

## Cómo navegar en el navegador
http://localhost:8080 → Dashboard con lista de libros

http://localhost:8080/books/1 → Detalles de un libro

http://localhost:8080/explore → Buscador

http://localhost:8080/books/new → Formulario para agregar libro

## Funcionalidades pendientes / futuras
Editar y eliminar libros

Biblioteca personal del usuario

Subida de portadas de libros

Filtrado por género, autor y precio

Panel de administración

### Autor
Jimmy Brito

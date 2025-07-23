# 📚 LiterAlura - Biblioteca Virtual con API de Gutendex

> Challenge del Programa ONE - Backend con Java (Alura Latam)

LiterAlura es una aplicación desarrollada como parte del **Challenge Backend Java** del programa **Oracle Next Education** en colaboración con **Alura Latam**. Su objetivo es permitir a los usuarios explorar y gestionar libros obtenidos desde la API pública [Gutendex](https://gutendx.com/), perteneciente al **Project Gutenberg**, una biblioteca digital gratuita.

---

## 🚀 Tecnologías Utilizadas

- **Java 17**
- **Spring Boot 3**
- **Spring Web** (RestTemplate)
- **Spring Data JPA**
- **Hibernate**
- **H2 Database** (Modo en memoria)
- **Lombok**
- **Postman** (para pruebas de API)
- **Maven**
- **IntelliJ IDEA**

---

## 🎯 Funcionalidades del Proyecto

- 🔍 Consultar libros desde la API de Gutendex
- 📄 Mostrar información detallada de los libros
- 💾 Guardar libros seleccionados en una base de datos local
- 🧾 Listar libros guardados por el usuario
- 💡 Buscar libros por título, autor o idioma
- ⚠️ Manejo robusto de excepciones
- ✅ Pruebas funcionales con Postman

---

## 📂 Arquitectura del Proyecto

```
📁 literAlura/
│
├── 📁 src/
│   ├── 📁 main/
│   │   ├── 📁 java/
│   │   │   └── 📁 com.literAlura/
│   │   │       ├── 📁 controller/        # Controladores REST
│   │   │       ├── 📁 model/            # Clases de entidad (Libro, Autor, etc.)
│   │   │       ├── 📁 repository/       # Interfaces JPA
│   │   │       ├── 📁 service/          # Lógica de negocio
│   │   │       └── 📄 LiterAluraApp.java # Clase principal
│   │   └── 📁 resources/
│   │       ├── 📄 application.properties # Configuración de la app
│   │       └── 📄 data.sql              # Datos de prueba (opcional)
│   └── 📁 test/                         # Tests unitarios (si aplica)
│
├── 📄 pom.xml                           # Dependencias y configuración de Maven
└── 📄 README.md                         # Documentación del proyecto
```

---

## 🌐 Consumo de API: Gutendex

Se utiliza el endpoint:
```
GET https://gutendx.com/books
```

Ejemplo de uso:
```java
RestTemplate restTemplate = new RestTemplate();
String url = "https://gutendx.com/books";
ResponseEntity<GutendexResponse> response = restTemplate.getForEntity(url, GutendexResponse.class);
```

### 📥 Ejemplo de Objeto JSON de la API

```json
{
  "results": [
    {
      "id": 1342,
      "title": "Pride and Prejudice",
      "authors": [
        {
          "name": "Austen, Jane"
        }
      ],
      "languages": ["en"],
      "download_count": 12000
    }
  ]
}
```

---

## 🧪 Pruebas en Postman

- `GET /books` → Lista todos los libros obtenidos
- `POST /books` → Guarda un nuevo libro en base de datos
- `GET /books/{id}` → Consulta libro por ID
- `GET /books/search?title=` → Búsqueda por título

---

## 🧑‍💻 Conocimientos Aplicados

- ✅ Programación Orientada a Objetos (POO)
- ✅ Desarrollo de APIs REST con Spring Boot
- ✅ Consumo de APIs externas (Gutendex)
- ✅ Manejo de excepciones personalizadas
- ✅ Inserciones y consultas con Spring Data JPA
- ✅ Uso de base de datos H2 en memoria
- ✅ Pruebas de endpoints con Postman

---

## 📌 Requisitos Previos

- Java 17+
- Maven 3.8+
- IDE IntelliJ (o cualquier otro IDE compatible)

---

## 🛠️ Instrucciones de Ejecución

```bash
# Clona el repositorio
git clone https://github.com/Rodrigo-Salva/Challenge-Literatura

# Entra al proyecto
cd Challenge-Literatura

# Compila y ejecuta
mvn spring-boot:run
```

La API estará disponible en:
```
http://localhost:8080
```

---

## 👨‍🏫 Agradecimientos

Quiero agradecer a:

**Instructores:**
- 🧑‍🏫 Genesys Rondón
- 🧑‍🏫 Eric Monné Fraga de Oliveira
- 🧑‍🏫 Brenda Souza

Por su dedicación como instructores de este módulo.

Y especialmente a:
- 🌎 **Alura Latam**
- 🧡 **Oracle Next Education**

Por brindarnos esta gran oportunidad para formarnos como desarrolladores Back-End.

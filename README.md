# Ecom-App


A lightweight Spring Boot backend for managing an e-commerce product catalog. This RESTful service supports CRUD operations on products, image uploads, and keyword-based search. Ideal as a backend foundation for an online store or as a learning project for Spring Boot, Spring Data JPA, and REST API development.
> ⚙️ **React Frontend**: The corresponding React app is available at [https://github.com/akash-belide/ecom-app-frontend](https://github.com/akash-belide/ecom-app-frontend).


## Table of Contents
- [Features](#features)
- [Technologies](#technologies)
- [Getting Started](#getting-started)
- [Configuration](#configuration)
- [API Endpoints](#api-endpoints)
- [Project Structure](#project-structure)
- [Contributing](#contributing)
- [Acknowledgments](#acknowledgments)

## Features
- Create, read, update, delete (CRUD) operations for products
- Upload and retrieve product images (multipart/form-data)
- Search products by keyword (name, description, brand, category)
- In-memory H2 database with sample data initialization
- CORS enabled for frontend integration

## Technologies
- Java 21, Spring Boot 3.4.4
- Spring Data JPA, H2 in-memory database
- Lombok for boilerplate reduction
- Maven for build and dependency management
- JUnit & Spring Boot Test for basic testing

## Getting Started
### Prerequisites
- Java 21
- Maven 3.8+

### Build and Run
1. Clone the repository:
   ```bash
   git clone https://github.com/akash-belide/ecom-app.git
   cd ecom-app
   ```
2. Build the project:
   ```bash
   ./mvnw clean package
   ```
3. Run the application:
   ```bash
   ./mvnw spring-boot:run
   ```
   The service will start on port 8080 by default.

## Configuration
Configuration is in `src/main/resources/application.properties`. The default uses an H2 in-memory database:
```properties
spring.datasource.url=jdbc:h2:mem:testdb
spring.jpa.hibernate.ddl-auto=update
```

## API Endpoints
Base path: `/api`

| Method | Endpoint                        | Description                                         |
| ------ | ------------------------------- | --------------------------------------------------- |
| GET    | `/products`                     | List all products                                   |
| GET    | `/product/{id}`                 | Get product by ID                                   |
| POST   | `/product`                      | Create product (multipart: Product JSON + image)    |
| GET    | `/product/{productId}/image`    | Download product image                              |
| PUT    | `/product/{id}`                 | Update product info and image                       |
| DELETE | `/product/{id}`                 | Delete product by ID                                |
| GET    | `/products/search?keyword=...`  | Search products by keyword                          |

## Project Structure
```
ecom-app
├── src
│   ├── main
│   │   ├── java/com/learn/ecomapp
│   │   │   ├── controller/ProductController.java
│   │   │   ├── model/Product.java
│   │   │   ├── repo/ProductRepo.java
│   │   │   ├── service/ProductService.java
│   │   │   └── EcomAppApplication.java
│   │   └── resources
│   │       ├── application.properties
│   │       └── data12.sql
│   └── test/java/com/learn/ecomapp
│       └── EcomAppApplicationTests.java
├── .mvn
├── mvnw, mvnw.cmd, pom.xml
└── README.md (this file)
```

## Contributing
Pull requests are welcome! 

## Acknowledgments
- Inspired by common e-commerce patterns and Spring Boot tutorials

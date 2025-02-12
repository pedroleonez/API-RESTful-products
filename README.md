# API RESTful products

## Overview

This is a Spring Boot application that provides a RESTful API for managing products. The application uses PostgreSQL as the database and includes basic CRUD operations.

## Technologies Used

- Java
- Spring Boot
- Spring Data JPA
- Hibernate
- PostgreSQL
- Maven

## Getting Started

### Prerequisites

- Java 17 or higher
- Maven 3.6.0 or higher
- PostgreSQL

### Installation

1. Clone the repository:
    ```sh
    git clone https://github.com/your-username/springboot-products-api.git
    cd springboot-products-api
    ```

2. Configure the PostgreSQL database in `src/main/resources/application.properties`:
    ```ini
    spring.datasource.url=jdbc:postgresql://localhost:5432/products-api
    spring.datasource.username=your-username
    spring.datasource.password=your-password
    ```

3. Build the project using Maven:
    ```sh
    mvn clean install
    ```

4. Run the application:
    ```sh
    mvn spring-boot:run
    ```

## API Endpoints

### Create a Product

- **URL:** `/products`
- **Method:** `POST`
- **Request Body:**
    ```json
    {
        "name": "Product Name",
        "value": 100.00
    }
    ```
- **Response:**
    ```json
    {
        "idProduct": "UUID",
        "name": "Product Name",
        "value": 100.00
    }
    ```

### Get All Products

- **URL:** `/products`
- **Method:** `GET`
- **Response:**
    ```json
    [
        {
            "idProduct": "UUID",
            "name": "Product Name",
            "value": 100.00,
            "_links": {
                "self": {
                    "href": "http://localhost:8080/products/UUID"
                }
            }
        }
    ]
    ```

### Get a Product by ID

- **URL:** `/products/{id}`
- **Method:** `GET`
- **Response:**
    ```json
    {
        "idProduct": "UUID",
        "name": "Product Name",
        "value": 100.00,
        "_links": {
            "Products List": {
                "href": "http://localhost:8080/products"
            }
        }
    }
    ```

### Update a Product

- **URL:** `/products/{id}`
- **Method:** `PUT`
- **Request Body:**
    ```json
    {
        "name": "Updated Product Name",
        "value": 150.00
    }
    ```
- **Response:**
    ```json
    {
        "idProduct": "UUID",
        "name": "Updated Product Name",
        "value": 150.00
    }
    ```

### Delete a Product

- **URL:** `/products/{id}`
- **Method:** `DELETE`
- **Response:**
    ```json
    {
        "message": "Product deleted successfully."
    }
    ```

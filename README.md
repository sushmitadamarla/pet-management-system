# 🐾 PetShop API

A RESTful API for managing a pet shop's inventory, built with **Spring Boot**. Supports full CRUD operations for pet records.

---

## 📋 Table of Contents

- [Features](#-features)
- [Tech Stack](#-tech-stack)
- [Getting Started](#-getting-started)
- [API Documentation](#-api-documentation)
- [Project Structure](#-project-structure)

---

## ✨ Features

- ➕ Add new pets to the inventory
- 📄 View all pets or a specific pet by ID
- ✏️ Update pet information
- 🗑️ Delete pets from the inventory

---

## 🛠 Tech Stack

| Layer      | Technology         |
|------------|--------------------|
| Language   | Java               |
| Framework  | Spring Boot        |
| Build Tool | Maven / Gradle     |
| Database   | H2 / MySQL (configure as needed) |

---

## 🚀 Getting Started

### Prerequisites

- Java 17+
- Maven or Gradle

### Installation

```bash
# Clone the repository
git clone https://github.com/your-username/petshop.git

# Navigate into the project
cd petshop

# Build the project
./mvnw clean install

# Run the application
./mvnw spring-boot:run
```

The server will start at `http://localhost:8080`.

---

## 📡 API Documentation

Base URL: `http://localhost:8080/api/pets`

### Endpoints

#### ➕ Create a Pet

```http
POST /api/pets
```

**Request Body:**

```json
{
  "name": "Buddy",
  "species": "Dog",
  "breed": "Golden Retriever",
  "age": 3,
  "price": 499.99
}
```

**Response:** `201 Created`

```json
{
  "id": 1,
  "name": "Buddy",
  "species": "Dog",
  "breed": "Golden Retriever",
  "age": 3,
  "price": 499.99
}
```

---

#### 📄 Get All Pets

```http
GET /api/pets
```

**Response:** `200 OK`

```json
[
  {
    "id": 1,
    "name": "Buddy",
    "species": "Dog",
    "breed": "Golden Retriever",
    "age": 3,
    "price": 499.99
  }
]
```

---

#### 🔍 Get Pet by ID

```http
GET /api/pets/{id}
```

**Response:** `200 OK`

```json
{
  "id": 1,
  "name": "Buddy",
  "species": "Dog",
  "breed": "Golden Retriever",
  "age": 3,
  "price": 499.99
}
```

> Returns `404 Not Found` if the pet does not exist.

---

#### ✏️ Update a Pet

```http
PUT /api/pets/{id}
```

**Request Body:**

```json
{
  "name": "Buddy",
  "species": "Dog",
  "breed": "Golden Retriever",
  "age": 4,
  "price": 549.99
}
```

**Response:** `200 OK`

```json
{
  "id": 1,
  "name": "Buddy",
  "species": "Dog",
  "breed": "Golden Retriever",
  "age": 4,
  "price": 549.99
}
```

---

#### 🗑️ Delete a Pet

```http
DELETE /api/pets/{id}
```

**Response:** `204 No Content`

> Returns `404 Not Found` if the pet does not exist.

---

## 📁 Project Structure

```
petshop/
├── src/
│   ├── main/
│   │   ├── java/com/petshop/
│   │   │   ├── controller/    # REST controllers
│   │   │   ├── model/         # Entity classes
│   │   │   ├── repository/    # JPA repositories
│   │   │   └── service/       # Business logic
│   │   └── resources/
│   │       └── application.properties
│   └── test/
├── pom.xml
└── README.md
```

---

## 📄 License

This project is for educational/portfolio purposes.

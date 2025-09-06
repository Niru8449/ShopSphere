# 🛒 ShopSphere
## 📌 Overview
This project is a **microservices-based e-commerce application** built using **Spring Boot, Spring Cloud, Spring Security, Eureka, and API Gateway**.  
It demonstrates a distributed architecture where different services (User Management, Products, Cart, Authentication, Gateway, and Eureka) work together to provide a scalable and secure e-commerce platform.

---

## ✅ Features
- Microservices architecture with **Spring Boot**  
- Centralized **service discovery** via **Eureka**  
- **API Gateway** for routing & authentication  
- Secure **OAuth2/JWT-based authentication**  
- Independent services for **Users, Products, and Cart**  
- **Feign Client** communication between services  
- Exception handling via `@ControllerAdvice`  


## ⚙️ Microservices Architecture

### 1. **Eureka Server (Service Discovery)**
- Location: `eurekaserver/`
- Registers and discovers all microservices dynamically.
- Acts as the central registry for service communication.

### 2. **API Gateway**
- Location: `gatewayserver/`
- Routes incoming requests to the correct microservice.
- Provides centralized **authentication, authorization, and request filtering**.
- **Key files:**
  - `WebSecurityConfig.java` → Configures Spring Security.
  - `JwtAuthoritiesConverter.java` → Extracts authorities from JWT.

### 3. **Auth Client**
- Location: `auth-client/`
- Handles OAuth2 and authentication client configurations.
- Provides secure interaction with **User Management** service.
- Example: `WebClientConfiguration.java` sets up a secure WebClient.

### 4. **User Management Service**
- Location: `user-management/`
- Handles **user registration, authentication, and authorization**.
- Provides APIs for creating users and checking credentials.
- Integrates with **Cart Service** via `CartFeignClient.java`.
- **Key components:**
  - `AuthorizationServerConfig.java` → OAuth2 authorization server.
  - `UserController.java` → Handles user-related REST endpoints.
  - `UserService.java` → Business logic for user management.

### 5. **Product Service**
- Location: `products/`
- Manages products and categories.
- Provides CRUD operations on products.
- **Key components:**
  - `ProductController.java` → Handles product-related requests.
  - `ProductService.java` → Contains business logic.
  - `ProductRepository.java` & `CategoryRepository.java`.

### 6. **Cart Service**
- Location: `cart/`
- Manages shopping cart functionality.
- Stores products added by users to their cart.
- **Key components:**
  - `CartController.java` → Handles cart operations.
  - `CartService.java` → Business logic for managing cart items.
  - `CartRepository.java` & `CartProductRepository.java`.

## 🔐 Security
- Authentication is handled via **OAuth2** and **JWT tokens**.  
- The **User Management Service** issues tokens after successful login/registration.  
- The **API Gateway** validates JWT tokens before routing requests.  
- Role-based access control (RBAC) is implemented using **Spring Security**.  

## 🌐 API Endpoints

| Service              | Endpoint Example                | Description                      |
|-----------------------|---------------------------------|----------------------------------|
| User Management       | `/users/register`               | Register a new user              |
| User Management       | `/users/login`                  | Authenticate & get JWT token     |
| Product Service       | `/products`                     | Get all products                 |
| Product Service       | `/products/{id}`                | Get product by ID                |
| Cart Service          | `/cart/{userId}`                | Get cart for a user              |
| Cart Service          | `/cart/{userId}/add`            | Add item to user’s cart          |

---

## 🛠️ Tech Stack
- **Backend:** Spring Boot, Spring Cloud, Spring Security, OAuth2  
- **Service Discovery:** Netflix Eureka  
- **API Gateway:** Spring Cloud Gateway  
- **Build Tool:** Maven  
- **Database:** configurable relational DB (default profile H2, can be switched to MySQL/Postgres)
- **Communication:** REST APIs, Feign Client  

---
## 📂 Project Structure
```
shopsphere/
│── auth-client/        # Handles authentication & OAuth2 client
│── cart/               # Manages shopping carts
│── eurekaserver/       # Service discovery (Eureka Server)
│── gatewayserver/      # API Gateway for routing & security
│── products/           # Product management service
│── user-management/    # User service with OAuth2 and Feign Client
```

## 🚀 Getting Started

### Prerequisites
- Java 17+
- Maven 3.8+
- Docker (optional, if containerizing)

### Running the Project
1. Clone the repository:
   ```bash
   git clone <repo-url>
   cd ecommerce-main

2. Start the Eureka Server:
   ```bash
   cd eurekaserver
   mvn spring-boot:run

3. Start the Gateway Server:
   ```bash
   cd gatewayserver
   mvn spring-boot:run

   
4. Start the Auth Client, User Management, Product, and Cart Services:
   ```bash
   cd <service-folder>
   mvn spring-boot:run

5. Access Eureka Dashboard:
   ```bash
   http://localhost:8761


   

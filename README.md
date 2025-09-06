# ShopSphere

Microservices-based e-commerce platform built with **Spring Boot** and **Spring Cloud**. Features independent services for authentication, user management, product catalog, cart, and order management, integrated via **API Gateway** and **Eureka** for service discovery, ensuring scalability and modularity.

## 🚀 Features
- **User Management**: Registration, login, profile management, and password reset.
- **Product Catalog**: Browse categories, detailed product pages, and advanced search powered by Elasticsearch.
- **Shopping Cart**: Add, update, and remove items with fast access via Redis caching.
- **Order Management**: Place orders, view history, and track delivery status.
- **Payment Integration**: Multiple payment options with secure transaction handling.
- **Notifications**: Email/SMS notifications for order updates and account activity.

## 🏗️ Architecture
- **Spring Boot Microservices**: Independent services for modular development and deployment.
- **API Gateway (Kong)**: Single entry point for routing, security, and rate limiting.
- **Service Discovery (Eureka)**: Dynamic service registration and lookup.
- **Message Broker (Kafka)**: Enables asynchronous communication and event-driven workflows.
- **Databases**:
  - **MySQL**: Structured data (users, orders, payments).
  - **MongoDB**: Flexible storage for shopping carts.
- **Redis**: In-memory caching for performance.
- **Elasticsearch**: Fast and intelligent product search.

## 📂 Project Structure
```
shopsphere/
├── auth-service
├── user-service
├── product-catalog-service
├── cart-service
├── order-service
├── payment-service
├── notification-service
├── api-gateway
└── service-discovery
```

## ⚙️ Tech Stack
- **Backend**: Java, Spring Boot, Spring Cloud
- **Databases**: MySQL, MongoDB
- **Caching**: Redis
- **Messaging**: Apache Kafka
- **Search**: Elasticsearch
- **Deployment**: Docker & Kubernetes (for containerization and orchestration)
- **Cloud**: AWS (ELB, SES, RDS)

## 📌 Getting Started
1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/shopsphere.git
   ```
2. Navigate to the project directory and build services:
   ```bash
   mvn clean install
   ```
3. Start infrastructure services (Kafka, Redis, Elasticsearch, MySQL, MongoDB) using Docker Compose or Kubernetes.
4. Run each microservice:
   ```bash
   mvn spring-boot:run
   ```
5. Access the system via API Gateway.

## 🛡️ Security
- Secure authentication and authorization.
- Encrypted communication between services.
- JWT-based session management.

## 🧪 Testing
- **Unit Tests**: Written with JUnit and Mockito.
- **Integration Tests**: Validate communication between services.
- **Load Testing**: Ensure performance and scalability under high traffic.

## 📖 Documentation
- Requirements and design details in [PRD.md](./prd.md).
- API specifications with **Swagger/OpenAPI** for each microservice.

## 🤝 Contributing
Contributions are welcome! Please fork this repository, create a feature branch, and submit a pull request.

---

💡 **ShopSphere** is designed with scalability, modularity, and resilience in mind, making it a robust foundation for any modern e-commerce platform.

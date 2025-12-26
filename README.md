# 🛒 E-Commerce Microservices Application

<!-- BADGES START -->
![Java](https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=java&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring%20Boot-6DB33F?style=for-the-badge&logo=springboot&logoColor=white)
![Microservices](https://img.shields.io/badge/Microservices-Architecture-blue?style=for-the-badge)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=for-the-badge&logo=kubernetes&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)
![Spring Cloud](https://img.shields.io/badge/Spring%20Cloud-6DB33F?style=for-the-badge&logo=spring&logoColor=white)
![JWT](https://img.shields.io/badge/JWT-Security-orange?style=for-the-badge)
![Prometheus](https://img.shields.io/badge/Prometheus-Monitoring-E6522C?style=for-the-badge&logo=prometheus&logoColor=white)
![Grafana](https://img.shields.io/badge/Grafana-Visualization-F46800?style=for-the-badge&logo=grafana&logoColor=white)
![Zipkin](https://img.shields.io/badge/Zipkin-Tracing-black?style=for-the-badge)

<!-- BADGES END -->


## 📘 Project Overview

The E-commerce Microservices Application is designed to provide a scalable and efficient architecture using Spring Boot, Java, and REST APIs. The system is containerized using Docker and orchestrated with Kubernetes to ensure high availability and scalability. Various design patterns have been implemented to enhance modularity, maintainability, and fault tolerance.

---

## 🧰 Technologies Used :- 
- Backend: Spring Boot, Java, REST API
- Containerization & Orchestration: Docker, Kubernetes
- Service Discovery: Eureka Server
- Communication: Feign Client, Circuit Breaker (Resilience4)
- Security: JWT Authentication, Proxy Client
- API Management: API Gateway
- Monitoring: Prometheus & Grafana
- Databases: MySQL

--- 

## 🎯 Key Outcomes of the Project

- Build and deploy an e-commerce platform with microservices.
- Gain hands-on experience with Eureka, Feign Client, Circuit Breaker, and JWT at the gateway layer.
- Monitor and troubleshoot microservices using Prometheus, Grafana, and Zipkin.
- Master end-to-end architecture for scalable, production-ready systems.
- Secure your microservices with best practices for authentication and authorization.
- Confidence in Building Real-World Applications
- End-to-End Development Skills

----

## 🧩 Microservices Components

1. User Microservice
2. Product Microservice
3. Order Microservice
4. Payment Microservice
5. Favourite Microservice
6. Shipping Microservice
7. Eureka Server - Service Discovery for Microservices Architecture
8. Feign Client Communication for All Microservices
9. API Gateway for E-commerce Microservices
10. Circuit Breaker Implementation in API Gateway
11. Distributed Tracing with Zipkin in Microservices
12. Monitoring E-Commerce Microservices with Prometheus & Grafana
13. Dockerizing Microservices for E-Commerce Application
14. Deploying Microservices on Kubernetes & Database Persistence
15. Proxy Client Service

---

## 👤 User Microservice:
The User Microservice is a core component of the E-commerce Microservices Application, responsible for managing user-related functionalities such as registration, authentication, and CRUD operations for user data, addresses, and credentials.

The User Microservice provides the following functionalities:
### 1. User Registration
  - Users can register with basic details:
    - userld
    - firstName
    - lastName
    - email
    - phone
  
### 2. Address Management
  - A user can have multiple addresses (One-to-Many Relationship).
  - Supports Create, Read, Update, and Delete (CRUD) operations.

### 3. Credentials Management
  - Each user has a one-to-one relationship with credentials.
  - The credentials include:
    - Username
    - Password (hashed & secured)
    - Role-Based Authority (User/Admin)

### 4. Role-Based Authorization
  - Two roles are available:
    - **USER:** Can access and modify their own data.
    - **ADMIN:** Has additional privileges for managing users.
  - Implements JWT Authentication for secure access.

### 5. CRUD Operations
  - Users can perform CRUD operations on their profile, addresses, and credentials.

### 6. DTO Pattern Implementatio
  - Uses DTOs (Data Transfer Objects) to ensure that:
    - Only necessary data is exposed in API responses.
    - Request and response objects are well-structured.

### 🗂 Database Relationship

|  Entity                             |        Relationship Type              |            Target Entity
|-------------------------------------|---------------------------------------|-------------------------------------------|
|   User → Address                    |         One-to-Many                   |     A user can have multiple addresses    | 
|   User → Credential                 |         One-to-One                    |     A user has one credential             |  
|   Credential → User                 |         One-to-One (Bidirectional)    |     Each credential belongs to one user   | 
|   Address → User                    |         Many-to-One                   |     Each address belongs to a user        |
|   Credential → RoleBasedAuthrority  |         Enum Mapping                  |     Stores role as a string               |


---

## 📦 Product Microservice:

The Product Microservice is responsible for managing products and categories in the E-commerce application. It allows vendors to create, update, delete, and retrieve products and categories while ensuring data consistency and modular design.

The Product Microservice provides the following functionalities:

### 1. Vendor Product Management 
  Vendors can create, update, delete, and retrieve products.
  Products belong to categories (Many-to-One Relationship).

### 2. Category Management
  Categories support subcategories and parent categories.
  Each category contains multiple products (One-to-Many Relationship).

---

## 🛒 Order Microservice:

The Order Microservice is responsible for managing customer orders and cart operations in the E-commerce Microservices Application. It allows users to add items to their cart, place orders, and manage their orders efficiently. This service ensures data consistency using Spring Boot, JPA, and DTO patterns.

The Order Microservice provides the following functionalities:
  - Users can place orders from their cart.
  - Multiple orders can be linked to a single cart (One-to-Many relationship).
  - Supports CRUD operations for orders.
  - Stores details like order feel date, and description.

---

## 💳 Payment Microservice:

The Payment Microservice is responsible for processing payments for orders in the E-commerce Microservices Application. It ensures that transactions are securely processed and tracks the payment status for each order. This service integrates with the Order Microservice to verify order details before processing payments.

The Payment Microservice provides the following functionalities:
  - Process Payments: Users can make payments for their orders.
  - Integration with Orders: Links payments to specific orders.
  - CRUD Operations for Payments: Allows retrieval and management of payment records.

---

## ❤️ Favourite Microservice

The Favourite Microservice is responsible for managing users' favourite products in the E-commerce Microservices Application. This service allows users to like or save products for future reference, helping enhance the shopping experience.

The Favourite Microservice provides the following functionalities:
  - Add Product to Favourites: Users can mark products as favourite.
  - Retrieve Favourite Products: Users can view a list of their saved products.
  - Remove Favourite Products: Users can rełnove products from their favourite.
  - Track Liked Date: Stores the date when a product was marked as favourite.

---

## 🌐 Eureka Server - Service Discovery for Microservices Architecture

The Eureka Server is a key component in a microservices architecture that enables service discovery and helps manage the dynamic registration and communication of all microservices. It ensures that services like User Service, Product Service, Order Service, Payment Service, Favourite Service, Shipping Service, API Gateway, and Proxy Client can discover and communicate with each other without hardcoding service locations.

### 1. Service Registration & Discovery
  - Each microservice registers itself with Eureka, making its instance discoverable.
  - When a service needs to communicate with another, it queries Eureka to get the latest instance address dynamically.

### 2. Load Balancing & Fault Tolerance
  - Eureka enables client-side load balancing by of a service. New among multiple instances
  - If one service instance goes down, Eureka removes it from the registry, ensuring that traffic is only directed to healthy instances.

### 3. High Availability & Self-Healing
  - Eureka continuously checks the health of registered services.
  - If a service stops sending heartbeats, Eureka deregisters it to prevent failures.

### 📌 Registered Services

| Service               |                        Function                            |       Registered in Eureka?    |
|-----------------------|------------------------------------------------------------|--------------------------------|
| User Service          |         Manages user authentication & profile              |                 Yes            |
| Product Service       |         Handles product & category management              |                 Yes            |
| Order Service         |         Manages orders and carts                           |                 Yes            |
| Payment Service       |         Handles payments and transactions                  |                 Yes            |
| Favourite Service     |         Manages users' favorite products                   |                 Yes            |
| Shipping Service      |         Handles order shipping and tracking                |                 Yes            |
| API Gateway           |         Routes client requests to appropriate services     |                 Yes            |
| Proxy Client          |         Secure authentication & communication              |                 Yes            |

---

## 🔗 Feign Client Communication for All Microservices:

Feign is a declarative HTTP client in Spring Boot that allows microservices to communicate with each other seamlessly without manually handling REST API calls. It simplifies service-to-service communication by automatically integrating with Eureka Server for dynamic service discovery.

In our E-commerce Microservices Application, Feign clients are used to establish communication between:
  - User Service ↔ Order Service (Fetching user details for order processing)
  - Order Service ↔ Product Service (Fetching product details for orders)
  - Order Service ↔ Payment Service (Validating payment status for orders)
  - Order Service ↔ Shipping Service (Triggering shipping after successful payment)
  - Favourite Service ↔ Product Service (Fetching product details for a user's favourite items)
  - API Gateway ↔ All Services (Routing and authentication

---

## 🚪API Gateway for E-commerce Microservices:

API Gateway acts as a single entry point for all client requests in the E-commerce Microservices Architecture. It handles:
  - Routing requests to the appropriate microservices
  - Load balancing between multiple instances of services
  - Security through JWT authentication
  - Circuit breaking & resilience with Resilience4j

In our project, the Spring Cloud Gateway is used as the API Gateway to manage requests across the following microservices:
  - User Service
  - Product Service
  - Order Service
  - Payment Service
  - Favourite Service
  - Shipping Service
  - Eureka Server (Service Discovery)

---

## ⚡Circuit Breaker Implementation in API Gateway

In microservices architecture, failures can happen at any time. If a service is unavailable or slow. it can cause cascading failures. To handle this, we use Circuit Breaker at the API Gateway layer to prevent overloading failing services and provide FallBack responses.

We implement Circuit Breaker using Resilience4j in Spring Cloud Gateway to:
  - Detect failures and prevent repeated requests to a failing service.
  - Provide a FallBack response if a microservice is down.
  - Ensure high availability and resilience of the system.

---

## 🔍 Distributed Tracing with Zipkin in Microservices

In microservices architecture, tracking requests across multiple services is challenging.
Distributed Tracing helps to monitor and debug service-to-service communication.

  - Zipkin is a distributed tracing tool that collects timing data and visualizes request flows across microservices.
  - It helps identify bottlenecks, performance issues, and failures in a system.

---

## 📊 Monitoring E-Commerce Microservices with Prometheus & Grafana

Monitoring is crucial in microservices architecture to ensure availability, detect issues, and optimize performance.
  - Prometheus: Collects and stores real-time metrics from microservices.
  - Grafana: Visualizes these metrics with dashboards for better insights.

---

## 🐳 Dockerizing Microservices for E-Commerce Application

Docker enables us to package each microservice as a lightweight, portable container. This ensures: 
  - Consistency - Works the same in development and production.
  - Scalability - Can scale microservices independently.
  - Isolation - Each microservice runs in its own container.

Each microservice will have its own Dockerfile and will be containerized separately.

---

## 🔐 Proxy Client Service

The Proxy Client Service in our E-commerce Microservices Architecture acts as an intermediary that:

  - Routes and manages requests between microservices.
  - Uses Feign Client for external API calls.
  - Implements Role-Based Access Control (RBAC) to restrict access based on user roles.
  - Secures communication with JWT-based authentication at the gateway level


---

## 🙏 Thank You

Thank you for taking the time to explore this **E-Commerce Microservices Application**.  
 Happy coding! 🚀





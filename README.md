
## 🧩 Spring Boot Microservices with Kafka – Practice Project

This project demonstrates a **Microservices Architecture** built using **Spring Boot**, where services communicate asynchronously using **Apache Kafka**. It covers real-world backend concepts like **JPA persistence, event-driven communication, multithreading, and clean service separation**.

---
<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/bbb663a9-50a1-48a0-a595-e3a77fdb5853" />

## 🏗️ Microservices in this Project

### 🔹 base-domain

* Common **DTOs, Events, and Models** shared across services
* Avoids duplication and ensures loose coupling

### 🔹 order-service

* REST APIs to create and manage orders
* Uses **Spring Data JPA** with MySQL
* Publishes **Order events** to Kafka after saving order

### 🔹 stock-service

* Consumes order events from Kafka
* Validates and updates product stock
* Publishes stock status events

### 🔹 email-service

* Consumes Kafka events
* Sends email notifications asynchronously using `@Async`
* Demonstrates **multithreading**

---

## 🔄 Event Flow

```
Client → order-service → Kafka → stock-service → Kafka → email-service
```

---

## 🖼️ Architecture Diagram

![Architecture Diagram](architecture-diagram.png)

---

## 🛠️ Tech Stack

* Java 17
* Spring Boot
* Spring Data JPA
* Apache Kafka
* MySQL
* Lombok
* Maven

---

## 🚀 Concepts Covered

* Microservices Architecture
* Kafka Producer & Consumer
* Event-Driven Communication
* JPA & Database Persistence
* Asynchronous Processing (`@Async`)
* Constructor-based Dependency Injection
* Clean project structure

---

## ▶️ How to Run

1. Start Zookeeper and Kafka
2. Create required topics:

   * `order-topic`
   * `stock-topic`
3. Run services in order:

   * order-service
   * stock-service
   * email-service
4. Use Postman to call order APIs

---

## 📌 Future Improvements

* Docker & Docker Compose
* API Gateway
* Eureka Service Discovery
* Config Server
* Monitoring & Tracing

---

## 🎯 Purpose

This project is built for **hands-on practice** and **interview preparation** to understand how real-world Spring Boot microservices communicate using Kafka.

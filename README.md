# 💳 Credit Score Analysis Tool

<p align="center">
  <img src="https://img.shields.io/badge/Java-11-orange?style=for-the-badge&logo=java" />
  <img src="https://img.shields.io/badge/Spring%20Boot-2.5.4-brightgreen?style=for-the-badge&logo=springboot" />
  <img src="https://img.shields.io/badge/Spring%20Security-OAuth2-green?style=for-the-badge&logo=springsecurity" />
  <img src="https://img.shields.io/badge/Apache%20Kafka-Event%20Driven-black?style=for-the-badge&logo=apachekafka" />
  <img src="https://img.shields.io/badge/Redis-Cache-red?style=for-the-badge&logo=redis" />
  <img src="https://img.shields.io/badge/MySQL-Database-blue?style=for-the-badge&logo=mysql" />
  <img src="https://img.shields.io/badge/Docker-Containerized-2496ED?style=for-the-badge&logo=docker" />
  <img src="https://img.shields.io/badge/Kubernetes-Orchestration-326CE5?style=for-the-badge&logo=kubernetes" />
  <img src="https://img.shields.io/badge/Jenkins-CI%2FCD-red?style=for-the-badge&logo=jenkins" />
</p>

An enterprise-style **microservices-based credit evaluation platform** designed to automate real-time credit scoring, predictive analytics, and secure report generation.

> ⚠️ Disclaimer: This is a prototype project created for educational and demonstration purposes based on enterprise architecture concepts.

---

## 🚀 Project Overview

The **Credit Score Analysis Tool** automates the process of credit score evaluation by integrating financial transaction data and external credit bureau information.

The system provides:

- ⚡ Real-time credit score updates  
- 📊 Predictive analytics  
- 📄 Automated credit report generation  
- 🔐 Secure authentication & authorization  
- 📈 Scalable microservices architecture  

The application follows a distributed architecture using Spring Boot microservices, Kafka, Redis, and OAuth2.

---

## 🏗️ Architecture

### 🔹 High-Level Flow

```
Frontend (Angular)
        ↓
Spring Cloud Gateway
        ↓
Microservices
   • Data Collection Service
   • Credit Scoring Service
   • User Management Service
   • Report Service
        ↓
MySQL Database
        ↓
Redis Cache
        ↓
Kafka (Real-time Messaging)
```

---

## 🧩 Microservices Breakdown

### 1️⃣ User Management Service
- Handles authentication & authorization
- Implements OAuth2 with JWT
- Role-Based Access Control (RBAC)
- Token validation via custom JWT filter

### 2️⃣ Data Collection Service
- Fetches financial data (transactions, loans, external bureau data)
- Validates & preprocesses data
- Publishes updates to Kafka

### 3️⃣ Credit Scoring Service
- Calculates credit scores using predefined algorithms
- Consumes Kafka topic: `credit-score-updates`
- Stores & retrieves data using Redis cache
- Sends email notifications on score updates

### 4️⃣ Report Service
- Generates PDF & HTML credit reports
- Sends reports via email
- Handles asynchronous processing

### 5️⃣ API Gateway (Spring Cloud Gateway)
- Single entry point for all requests
- Token validation
- Request routing
- CORS configuration
- Security filtering

---

## 🛠️ Tech Stack

### 🔹 Backend
- Java 11
- Spring Boot 2.5.4
- Spring Security + OAuth2
- Spring Cloud Gateway
- Spring Data JPA
- WebFlux

### 🔹 Database & Cache
- MySQL
- Redis

### 🔹 Messaging
- Apache Kafka

### 🔹 Logging & Monitoring
- Log4j2
- Splunk Integration

### 🔹 DevOps
- Maven
- Docker
- Kubernetes
- Jenkins (CI/CD)
- SonarQube (80% minimum coverage rule)
- Git (Git Flow branching strategy)

---

## 🔐 Security Implementation

- OAuth2-based authentication
- JWT token validation
- Role-Based Access Control (RBAC)
- API protection through Gateway
- Encrypted data transmission
- Token validation filter (JwtAuthenticationFilter)

---

## ⚡ Kafka Integration

- Topic: `credit-score-updates`
- Real-time score recalculation
- Asynchronous email notifications
- Partition-based load distribution

---

## 🧠 Redis Caching Strategy

Used for:
- Credit score calculation results
- External API responses
- Frequently accessed financial data

Implemented using:
- `@Cacheable`
- `@CachePut`
- `@CacheEvict`

---

## 📊 Database Schema (Major Tables)

- **Users**
- **Credit Scores**
- **Financial Records**
- **Reports**
- **Audit Logs**

Each service interacts with MySQL using Spring Data JPA repositories.

---

## 🔌 Sample REST APIs

### User Management
- `POST /users/authenticate`
- `GET /users/{userId}`

### Credit Scoring
- `POST /score/calculate`
- `GET /score/{userId}`
- `GET /score/history/{userId}`

### Reports
- `POST /reports/generate`
- `GET /reports/{userId}`

---

## 🧪 Testing Strategy

- JUnit for unit testing
- Mockito for mocking dependencies
- Integration testing
- SonarQube coverage monitoring (Minimum 80%)

---

## 🔄 CI/CD Pipeline

1. Code pushed to Git  
2. Jenkins triggers build  
3. Maven compiles project  
4. JUnit tests executed  
5. SonarQube analysis  
6. Docker image creation  
7. Deployment via Kubernetes  
8. Blue-Green deployment strategy  

---

## 🧑‍💻 My Contributions

- Implemented real-time credit scoring using Kafka  
- Integrated Redis caching for performance optimization  
- Developed secure REST APIs using Spring Boot  
- Implemented OAuth2 authentication & JWT validation  
- Configured Log4j2 and integrated Splunk for monitoring  
- Contributed to microservices architecture design  
- Followed Git Flow branching model  
- Maintained 80%+ test coverage  

---

## 📈 Key Highlights

✔ Microservices Architecture  
✔ Real-Time Processing  
✔ Secure Token-Based Authentication  
✔ Distributed Caching  
✔ Asynchronous Messaging  
✔ Enterprise-Style DevOps Setup  

---

## ▶️ How to Run

```bash
git clone https://github.com/your-username/credit-score-analysis-tool.git
cd credit-score-analysis-tool
mvn clean install
mvn spring-boot:run
```

Make sure:
- MySQL is running
- Redis server is active
- Kafka broker is running

---

## 📌 Future Enhancements

- Migrate selective services to MongoDB
- Implement centralized configuration server
- Add circuit breaker (Resilience4j)
- Improve ML-based scoring integration

---

## 📬 Contact

**Ravindra Chimkar**    
GitHub: https://github.com/ravichimkar  

---

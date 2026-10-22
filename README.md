# Hotel Booking Microservices

## Project Overview
The system is a distributed microservices application for booking hotels. It consists of four independent services that communicate via HTTP/REST. There is no direct horizontal communication between the business services; all requests are orchestrated by a single **Gateway Service**.

### Architecture & Services
The system consists of the following components:

| Service | Port | Description | Database |
| :-----------------------| :----- | :---------------------------------------------------------- | :--------------|
| **Gateway Service**     | `8080` | Single entry point. Orchestrates requests between services. | None|
| **Loyalty Service**     | `8050` | Manages user loyalty statuses and discounts.                | `balances`     |
| **Payment Service**     | `8060` | Handles payment creation and cancellation.                  | `payments`     |
| **Reservation Service** | `8070` | Manages hotels and reservations.                            | `reservations` |
| **PostgreSQL**          | `5432` | Database instance hosting 3 logical databases.              | -              |

*Note: Each service has its own logical database, and cross-database queries are strictly forbidden.*

## Technologies Used
- **Java 17** (Eclipse Temurin)
- **Spring Boot 3.2.5** (Web, Data JPA, WebFlux for WebClient)
- **PostgreSQL 13**
- **Docker & Docker Compose**
- **GitHub Actions** (CI/CD)
- **Postman & Newman** (Integration Testing)


```bash
docker compose up -d --build

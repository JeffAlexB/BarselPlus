# BarselPlus – Architecture

## Overview
BarselPlus is implemented as a **vertical slice demo** that showcases how pregnancy journals can be digitized using a modern 
full-stack architecture. The project is intentionally scoped down to demonstrate **core CRUD functionality** for key entities 
without implementing role-based access or production-level security.

---

## High-Level Design
- **Backend (Spring Boot + PostgreSQL)**  
  - Exposes a REST API under `/api/**`.  
  - Implements layered architecture (Controller → Service → Repository).  
  - Entities: Patient, Partner, Pregnancy, Medical History.  
  - Uses DTO mappers to decouple persistence from API contracts.  
  - Integration tests verify persistence and REST endpoints.  

- **Frontend (Angular + Prototype HTMX/Thymeleaf)**  
  - Angular SPA under development (planned for CRUD operations & data display).  
  - HTMX/Thymeleaf views exist as a lightweight prototype.  
  - Angular communicates with backend via REST API (`/api`).  
  - Dev proxy configuration avoids CORS issues during local development.  

- **Database (PostgreSQL)**  
  - Normalized schema with referential integrity.  
  - ERD available in [BarselPluss_ERD.png](./BarselPluss_ERD.png).  
  - Sample SQL scripts for testing constraints and relationships under `/DevProcess/DB_testing/`.  

---

## Coding Conventions
- Controllers: thin, REST endpoints under `/api/**`
- Services: business logic, stateless
- Repositories: Spring Data JPA
- DTOs: all API contracts (no entities exposed)
- Validation: Bean Validation on DTOs
- Tests: JUnit + MockMvc for REST, @DataJpaTest for repos

---

## Component Diagram (Conceptual)
```
text
+-------------------------+         +------------------------+
|     Angular Frontend    | <--->   |   Spring Boot Backend  |
| (UI, forms, CRUD views) |  REST   | (Controllers, DTOs,    |
|                         |  API    |  Services, Repos)      |
+-------------------------+         +------------------------+
                                              |
                                              | JPA / Hibernate
                                              v
                                    +------------------------+
                                    |    PostgreSQL DB       |
                                    |  (patients, partners,  |
                                    |   pregnancies, etc.)   |
                                    +------------------------+
```

---

## Deployment / Development Setup
Local Development:
 - Run backend with ./mvnw spring-boot:run.
 - Run frontend with npm start (proxy config forwards /api to backend). </br>

Optional Docker Setup (Planned):
 - Docker Compose to spin up PostgreSQL + backend.
 - Angular served as static bundle behind Nginx.

---

## Out of Scope (Not Implemented in Demo)
 - Authentication and role-based access control.
 - Production-ready deployment pipeline.
 - External integrations (hospital systems).
 - Mobile applications.

---

## Next Steps
- [ ] Finalize Angular frontend vertical slice (patients + pregnancies).
- [ ] Add Docker Compose for local dev environment.
- [ ] Expand integration testing coverage.
- [ ] Add CI workflows (GitHub Actions) for backend and frontend.








# BarselPlus – Tech Stack

## Overview
BarselPlus is a **vertical slice demo** application built to demonstrate how pregnancy journals can be digitized using a modern full-stack architecture. The stack is chosen to highlight both backend and frontend development, with a strong emphasis on maintainability, testing, and documentation.

---

## Backend
- **Java 21** – Core programming language.
- **Spring Boot 3** – Application framework (REST controllers, services, configuration).
- **Spring Data JPA (Hibernate)** – ORM for database persistence.
- **Maven** – Dependency management and build tool.
- **JUnit 5 & MockMvc** – Unit and integration testing.

---

## Frontend
- **Angular 17 (TypeScript)** – Planned SPA frontend for CRUD operations and data display.
- **Node.js & npm** – Build and dev tooling for Angular.
- **HTMX + Thymeleaf** – Existing lightweight prototype UI (server-rendered, used as an interim frontend).

---

## Database
- **PostgreSQL 16** – Relational database for persistence.
- **pgAdmin / CLI** – Management tools for testing queries and inspecting schema.
- **SQL Scripts** – Validation and constraint testing (see `/DevProcess/DB_testing/`).

---

## Infrastructure & DevOps
- **Docker** – Planned containerization for PostgreSQL and backend service.
- **Docker Compose** – Planned for local dev environment (backend + database).
- **GitHub Actions** – Continuous Integration (build & test pipelines for backend and frontend).

---

## Documentation
- **Markdown Docs** – Full product, technical, and user documentation under `/Documentation/`.
- **Diagrams** – ERD, architecture diagrams.
- **API Docs** – Generated OpenAPI/Swagger definitions (planned for backend).

---

## Out of Scope (Demo Limitations)
- No production-ready authentication or role-based access.
- No hospital system integrations.
- No mobile app deployment.

---

## Rationale
The chosen stack reflects a balance between:
- **Industry relevance** – Java/Spring Boot + Angular/PostgreSQL are widely used in enterprise applications.  
- **Portfolio demonstration** – Clear separation of concerns (backend, frontend, database) allows the project to showcase multiple skill areas.  
- **Scalability potential** – While out of scope for the demo, the stack can scale toward production readiness with added security and compliance features.

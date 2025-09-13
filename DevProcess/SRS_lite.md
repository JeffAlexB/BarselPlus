# BarselPlus — SRS (Lite)

## Purpose
Demonstrate a vertical slice for digitizing Norwegian pregnancy journals: store, validate, and display core data without authentication/RBAC.

## In Scope (demo)
- CRUD for: Patient, Partner, Pregnancy, Medical History
- REST API (`/api/**`), JSON DTOs, validation errors
- PostgreSQL schema (ERD provided)
- Basic UI prototype (Angular or HTMX) for create/list/view
- Documentation: Architecture, Tech Stack, API overview

## Out of Scope
- Authentication/authorization, RBAC
- GDPR/HIPAA workflows; audit trails
- External integrations; mobile apps; production deployment

## Actors (prototype)
- **Midwife (no login):** creates/reads patient + pregnancy data
- **Developer (you):** operates the system locally for demo/testing

## Functional Requirements (FR)
- **FR1** Create Patient with required fields (firstName, lastName, dob)
- **FR2** Create Pregnancy linked to Patient (lastMens, dueDate)
- **FR3** Read Patient, Pregnancy by ID; list patients and patient’s pregnancies
- **FR4** Validate inputs; return structured 400 errors
- **FR5** Persist data in PostgreSQL with referential integrity

## Non-Functional Requirements (NFR)
- **NFR1** Local setup ≤ 5 min (README quickstart)
- **NFR2** API stable JSON contract (documented in Swagger)
- **NFR3** Tests: unit + basic integration for each resource
- **NFR4** Code organized by layers (controller/service/repository)

## Acceptance Criteria (sample)
- AC1: POST `/api/patients` with valid payload returns 201 + body with `id`
- AC2: POST `/api/patients` missing `firstName` returns 400 with field error
- AC3: POST `/api/pregnancies` with non-existent `patientId` returns 400/404
- AC4: GET `/api/patients/{id}` returns 200 with matching fields
- AC5: `mvn test` passes in clean clone

## References
- Architecture.md, API_docs.md, DB_schema.md, BarselPluss_ERD.png

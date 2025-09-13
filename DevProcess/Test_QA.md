# BarselPlus — Test & QA (Lite)

## Test Goals
Verify the vertical slice meets SRS_Lite requirements: CRUD, validation, persistence, and JSON contract.

## Test Scope
- **Included:** REST controllers, services, repositories; DTO validation; basic UI smoke (manual)
- **Excluded:** Auth/RBAC, performance, security pen-testing, cross-browser UI

## Test Types & Tools
- **Unit tests:** services, mappers — JUnit 5
- **Web tests:** controllers — Spring MockMvc (`@WebMvcTest`)
- **JPA tests:** repositories — `@DataJpaTest`
- **Integration tests:** happy path create→read for each resource
- **Manual smoke:** UI create/list/view flows

## What We Assert
- **Validation:** required fields, formats (e.g., `dob` past date)
- **Persistence:** FK relationships; cascade behavior where used
- **Contract:** JSON field names & types; error envelope structure
- **Negative paths:** 404 for missing IDs; 400 for bad input

## How to Run
```
# Backend
./mvnw test

# Manual smoke (dev)
./mvnw spring-boot:run
# then hit /api/* or use the prototype UI
```

## Sample Cases
 - POST `/api/patients` valid → 201 (id present)
 - POST `/api/patients` missing firstName → 400 (field error)
 - POST `/api/pregnancies` with invalid patientId → 404
 - GET `/api/patients/{id}` unknown → 404
 - Repo test: saving Pregnancy with Patient persists and retrieves relation

## Quality Gates (for the demo)
 - All tests green in CI
 - No unchecked exceptions in controller layer
 - README quickstart works in a clean environment

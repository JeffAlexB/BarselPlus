# BarselPlus – Scope Statement

## Project Purpose
BarselPlus is a proof-of-concept healthcare application designed to digitize the pregnancy journals currently maintained 
on paper in Norwegian hospitals. The project focuses on building a vertical slice — 
demonstrating how patient and pregnancy information can be stored, validated, and presented digitally.

## Objectives
- Replace paper-based pregnancy journals with a digital prototype.
- Provide secure storage of patient and pregnancy data in a relational database.
- Demonstrate core CRUD functionality for key entities:
  - Patient
  - Partner
  - Pregnancy
  - Medical history
- Showcase both backend (Spring Boot + PostgreSQL) and frontend (Angular or HTMX prototype).

## Scope of Work
**In scope:**
- RESTful API for core entities.
- Database schema design and validation.
- Basic input validation and error handling.
- Documentation (architecture, schema, testing strategy, roadmap).
- Simple frontend prototype for displaying and adding records.

**Out of scope:**
- Role-based access control (RBAC).
- Production-grade authentication and authorization.
- Full regulatory compliance (GDPR, HIPAA).
- Mobile app deployment.
- Integration with external systems.

## Deliverables
- Working backend service with integration tests.
- Database schema with ERD.
- Basic frontend demo.
- Documentation of technical design, testing approach, and roadmap.

## Success Criteria
- Ability to create and retrieve patient and pregnancy records.
- Integration tests demonstrating data validation and persistence.
- Clear documentation showing how the system could be expanded.

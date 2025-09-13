# BarselPlus

Digitizing pregnancy journals for Norwegian healthcare.
BarselPlus is a healthcare application designed to replace the analog paper booklet currently used in hospitals for pregnancy tracking. The app enables patients and healthcare providers to securely track information such as medical history, prescriptions, lab results, vitals, and provider notes.

---

## Overview
Goal: Replace paper-based pregnancy journals with a secure, digital solution.<br />
Users: Patients, co-parents<br />
Core Features:
 - Patient & partner profiles
 - Pregnancy tracking (visits, labs, symphysis-fundus, medical history)
 - Role-based access for patients and providers
 - Integration tests for data validation and persistence

---

## Tech Stack
Backend: Java, Spring Boot, JPA/Hibernate, PostgreSQL<br />
Frontend: Angular (WIP), HTMX/Thymeleaf (front-end prototype)<br />
Other: Docker (WIP), JUnit/MockMvc

---

## Project Structure
<a href="https://github.com/JeffAlexB/barselplus-backend">BarselPlus-Backend</a>
 - Uses: Spring Boot + PostgreSQL (REST API, services, DTO mappers, security).

<a href="https://github.com/JeffAlexB/barselplus-frontend">BarselPlus-Frontend</a>
 - Uses: Angular, TailwindCSS. 

<a href="https://github.com/JeffAlexB/BarselPlus/Documentation/README.md">Docs & FAQs</a>
 - Documents: Architecture, database schema, API design, roadmap, QA/testing, regulatory notes.

---

## Documentation Index
 - <a href="https://github.com/JeffAlexB/BarselPlus/Documentation/README.md">Scope Statement</a>
 - <a href="https://github.com/JeffAlexB/BarselPlus/Documentation/README.md">LEAN Canvas</a>
 - <a href="https://github.com/JeffAlexB/BarselPlus/Documentation/README.md">Architecture & Tech Stack</a>
 - <a href="https://github.com/JeffAlexB/BarselPlus/Documentation/README.md">Database Schema</a>
 - <a href="https://github.com/JeffAlexB/BarselPlus/Documentation/README.md">API Docs</a>
 - <a href="https://github.com/JeffAlexB/BarselPlus/Documentation/README.md">Roadmap</a>
 - <a href="https://github.com/JeffAlexB/BarselPlus/Documentation/README.md">Testing Strategy & QA</a>
 - <a href="https://github.com/JeffAlexB/BarselPlus/Documentation/README.md">Privacy & Security Policy</a>

---

## ERD

![alt "ERD image"](https://github.com/JeffAlexB/BarselPlus/blob/main/Technical/BarselPluss_ERD.png)

---

## Roadmap
- [ ] Finalize backend DTO mappers and integration tests
- [ ] Expand role-based security (patients, midwives, doctors)
- [ ] Spin up Angular frontend to replace prototype HTMX views
- [ ] CI/CD pipelines for backend & frontend
- [ ] Polish documentation (update diagrams, wireframes)

---

## Reflections

BarselPlus started, initally, as a tightly coupled prototype. While early iterations started exposing gaps in testing and design, they also highlighted opportunities to apply best practices and learn a lot about software development procoeses:
 - Layered architecture with DTO mappers and service/repo separation
 - REST integration testing with MockMvc
 - Role-based access control for multiple user types (or the lack thereof multi-users)

This repo is going to serve as a 'live' demo project and a sandbox where I integrate concepts learned in my consultant training and on-the-job learning to test and learn new techinques, practices and tech.

--- 

## License
MIT License – <a href="https://github.com/JeffAlexB/barselplus-backend/blob/main/LICENSE">see LICENSE</a>

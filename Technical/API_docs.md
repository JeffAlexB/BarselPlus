# BarselPlus – API Documentation

This document provides a high-level overview of the REST API exposed by the BarselPlus backend.  
The API is designed as a **demo/vertical slice**: it focuses on CRUD operations for core entities only.  
Full endpoint reference is available through **Swagger/OpenAPI** at runtime.

---

## Base URL

`http://localhost:8080/api`

--- 

## Resources

### 1. Patients
- **GET /api/patients** – Retrieve all patients  
- **GET /api/patients/{id}** – Retrieve a patient by ID  
- **POST /api/patients** – Create a new patient  
- **PUT /api/patients/{id}** – Update a patient  
- **DELETE /api/patients/{id}** – Delete a patient  

**Example Request (POST)**  
```
http
POST /api/patients
Content-Type: application/json
{
  "firstName": "Anna",
  "lastName": "Olsen",
  "dob": "1995-06-12",
  "phone": "12345678"
}
```

**Example Response (201 Created)**
```
{
  "id": 1,
  "firstName": "Anna",
  "lastName": "Olsen",
  "dob": "1995-06-12",
  "phone": "12345678"
}
```

---

### 2. Partners
 - GET /api/partners – Retrieve all partners
 - GET /api/partners/{id} – Retrieve a partner by ID
 - POST /api/partners – Create a new partner

Example Request (POST)
```
POST /api/partners
Content-Type: application/json

{
  "firstName": "Lars",
  "lastName": "Hansen",
  "phone": "98765432"
}
```

---

### 3. Pregnancies
 - GET /api/pregnancies – Retrieve all pregnancies
 - GET /api/pregnancies/{id} – Retrieve a pregnancy by ID
 - POST /api/pregnancies – Create a new pregnancy linked to a patient
 - GET /api/patients/{id}/pregnancies – Retrieve pregnancies for a given patient

Example Request (POST)
```
POST /api/pregnancies
Content-Type: application/json

{
  "patientId": 1,
  "lastMens": "2025-02-01",
  "dueDate": "2025-11-08",
  "parity": "G1P0"
}
```

---

### 4. Medical History
 - GET /api/medicalhistory – Retrieve all medical history entries
 - POST /api/medicalhistory – Add history linked to a patient

Example Request (POST)
```
POST /api/medicalhistory
Content-Type: application/json

{
  "patientId": 1,
  "condition": "Asthma",
  "diagnosed": "2010-05-12"
}
```

---

### Error Handling
Validation errors return 400 Bad Request with details:
```
{
  "errors": [
    { "field": "firstName", "message": "must not be blank" }
  ]
}
```
 - Resource not found returns 404 Not Found.
 - Server errors return 500 Internal Server Error.

---

### Notes
 - Authentication/authorization is out of scope for this demo.
 - All endpoints are open for CRUD operations.
 - For full details, refer to Swagger at:
```
http://localhost:8080/swagger-ui.html
```




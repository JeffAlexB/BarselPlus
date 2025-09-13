# BarselPlus – Wireframes & UI (Prototype)

## Purpose
These wireframes illustrate the **prototype user flows** for the BarselPlus vertical slice.  
The goal is not a polished design, but to demonstrate how patient and pregnancy data can be created and displayed digitally, replacing the current paper-based journals.  

---

## Core User Flows (Demo Scope)

### 1. Home / Dashboard
- Simple landing page with links to:
  - View all patients
  - Add new patient
  - (Planned) View project information/docs

### 2. Patients
- **List View**
  - Table of patients with ID, name, DOB, phone
  - "View" and "Add Pregnancy" actions
- **Detail View**
  - Patient information (read-only)
  - Linked pregnancies displayed as a table
- **Add Patient Form**
  - Required fields: firstName, lastName, DOB
  - Optional fields: phone
  - On submit: calls `POST /api/patients`

### 3. Pregnancies
- **Add Pregnancy Form**
  - Select patient (dropdown or prefilled when accessed from Patient)
  - Required fields: lastMens, dueDate
  - Optional: parity, notes
  - On submit: calls `POST /api/pregnancies`
- **View Patient Pregnancies**
  - Table of pregnancies linked to a patient
  - Columns: ID, lastMens, dueDate, parity

### 4. Medical History (Optional Slice)
- **Add History Entry**
  - Condition, date diagnosed
  - Linked to a patient
- **View History**
  - List of history entries under a patient detail page

---

## Design Notes
- **Scope**: only CRUD for core entities (no auth, no role-based screens).  
- **Style**: simple forms and tables, prioritizing clarity over design polish.  
- **Implementation**: 
  - Prototype currently uses **HTMX + Thymeleaf** templates for server-rendered forms.  
  - Planned Angular frontend will mirror these flows with a modern SPA approach.  

---

## Visuals
- Wireframes and mockups can be found in this folder:
  - [`mockup.png`](./mockup.PNG) – early UI sketch

---

## Next Steps
- Mirror wireframes in Angular frontend (patients + pregnancies).  
- Add lightweight styling (Bootstrap/Tailwind) for clarity.  
- Expand with medical history once core flows are stable.

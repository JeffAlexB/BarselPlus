# Database Schema & Model:

<p>
Initial DB schema and ERD model, includes basic relationships and moc-setup for how to the db should relate. It includes
all related fields and data from the physical paper copy. Some tables are relatively bloated with a lot of 
initial data setup (such as the pregnancy_lab and medical_history tables), but are initially set up this way to 
enable hardcoding the data. There's probably better ways to set up the tables, but it should at least work initially and 
allow some latitude to get a functioning DB up to support the app and its critical data functions.
</p>

![alt "ERD image"]
(https://github.com/JeffAlexB/BarselPlus/blob/main/Technical/BarselPluss_ERD.png)

```
// Use DBML to define your database structure
// Docs: https://dbml.dbdiagram.io/docs
Table Patient {
  PatientID integer
  FirstName String
  LastName String
  DateOfBirth date
  NationalID integer
  Address String
  PhoneNumber String
  MaritalStatus String
  EducationLevel String
  Working boolean
  Occupation String
  WorkPercentage String
  CountryOfOrigin String
  Language String
  InterpreterNeeded Boolean
}

Table Partner {
  PartnerID integer [primary key]
  PatientID integer [ref: - Patient.PatientID]
  FirstName String
  LastName String
  DateOfBirth date
  NationalID integer
  Address String
  PhoneNumber String
  Occupation String
  CountryOfOrigin String
  Language String
}

Table PregnancyHistory {
  HistoryID integer [primary key]
  PatientID integer [ref: - Patient.PatientID]
  NumberOfPregnancies integer
  SpontAbortions integer
  LiveBorn integer
  ExUteral integer
  Stillborn integer
  Notes String
}

Table MedicalHistory{
  HistoryID integer [primary key]
  PatientID integer [ref: - Patient.PatientID]
  ChronicDiseases String
  GeneticConditions String
  SmokingUse String
  SnusUse String
  AlchoholUse String
  OtherDrugUse String
  SmokingWeek1 String
  SnusWeek1 String
  AlchoholWeek1 String
  SmokingWeek36 String
  SnusWeek36 String
  AlchoholWeek36 String
  Medications String
  MedList String
  DrugAllergy boolean
  Folate String
  Notes String
}

Table SymphysisFondus{
  SymphysisFondusID integer [primary key]
  PregnancyID integer [ref: > Pregnancy.PregnancyID]
  PatientID integer
  Week integer
  UteralSize integer
}

Table Pregnancy {
  PregnancyID integer [primary key]
  PatientID integer [ref: > Patient.PatientID]
  LastMens timestamp
  EstimatedDuedate timestamp
  ULDuedate timestamp
  CorrectedDuedate timestamp
  FetusDiagnostics boolean
  AssistedConcept boolean
  AssistDate timestamp
  MultipleFetus boolean
  PrePregnancyHeight integer
  PrePregnancyWeight integer
  PrePregnancyBMI decimal
  BreastfeedGuide boolean 
  PrenatalConsult boolean
  CoparentDeclaration boolean
  MaternityWard String
  WardTLF integer
  Healthstation String
  HSAdresse String
  HStelefon integer
  Notes String
}

Table PregnancyLab{
  PregnancyID integer [ref: > Pregnancy.PregnancyID]
  PatientID integer [ref: > Patient.PatientID]
  Hb integer
  Sferritin integer
  HepB_HBsAg boolean
  HepB_antiHBc boolean
  HIV boolean
  Syphilis boolean 
  ABO_Rh String
  BloodAntigens String

  FetusRhDWeek24 boolean
  RhDProphylacticWeek28 boolean 
  FetusRhDConsent String
  FetusRhDDate timestamp
  FetusRhDNotes String

  Chlamydia boolean
  Toxoplasmosis boolean
  RubellaAntigen boolean
  HepC boolean
  MRSAVREESBL boolean
  HbA1c decimal
  GlucoseTestFasting decimal
  GlucoseTest2Hours decimal
  GlucoseTestDate timestamp
}

Table PrenatalVisit {
  VisitID integer [primary key]
  PregnancyID integer [ref: > Pregnancy.PregnancyID]
  VisitDate datetime
  PregnancyWeek integer
  Weight integer
  BloodPressure String
  UrineProtein String
  Edema Integer
  FetalPosition String
  FetalMovement Boolean
  FetalHeartRate integer
  Presence boolean
  Medications String
  WorkPercentage decimal
  Notes String
  HealthcareProviderID integer [ref: > HealthcareProvider.ProviderID]
}

Table HealthcareProvider{
  ProviderID integer [primary key]
  FirstName String
  LastName String
  Role String
  PhoneNumber String
  Email String
  FacilityName String
}
```

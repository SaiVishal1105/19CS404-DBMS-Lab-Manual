# Experiment 1: Entity-Relationship (ER) Diagram

## 🎯 Objective:
To understand and apply the concepts of ER modeling by creating an ER diagram for a real-world application.

## 📚 Purpose:
The purpose of this workshop is to gain hands-on experience in designing ER diagrams that visually represent the structure of a database including entities, relationships, attributes, and constraints.

---

## 🧪 Choose One Scenario:

### 🔹 Scenario 1: University Database
Design a database to manage students, instructors, programs, courses, and student enrollments. Include prerequisites for courses.

**User Requirements:**
- Academic programs grouped under departments.
- Students have admission number, name, DOB, contact info.
- Instructors with staff number, contact info, etc.
- Courses have number, name, credits.
- Track course enrollments by students and enrollment date.
- Add support for prerequisites (some courses require others).

---

### 🔹 Scenario 2: Hospital Database
Design a database for patient management, appointments, medical records, and billing.

**User Requirements:**
- Patient details including contact and insurance.
- Doctors and their departments, contact info, specialization.
- Appointments with reason, time, patient-doctor link.
- Medical records with treatments, diagnosis, test results.
- Billing and payment details for each appointment.

---

## 📝 Tasks:
1. Identify entities, relationships, and attributes.
2. Draw the ER diagram using any tool (draw.io, dbdiagram.io, hand-drawn and scanned).
3. Include:
   - Cardinality & participation constraints
   - Prerequisites for University OR Billing for Hospital
4. Explain:
   - Why you chose the entities and relationships.
   - How you modeled prerequisites or billing.

# ER Diagram Submission - Student Name SAI VISHAL D 212223230180

## Scenario Chosen:
University

## ER Diagram:
![Untitled Diagram drawio (2)](https://github.com/user-attachments/assets/46828c3b-a8da-4aac-92ff-c2fdf3b17f00)

### Entities and Attributes:

- Student: Admission number (PK), Name, Date of birth, Email, Phone number  
- University: [No attributes shown in the diagram]  
- Department: Department ID (PK), Department name  
- Program: Program ID (PK), Program name  
- Course: Course code (PK), Course name, Credits, Prerequisite  
- Instructor: Instructor ID (PK), Name, Email  

---

### Relationships and Constraints:

- Stores Info (University–Student) 
  - Cardinality: One university stores many students (1:N)  
  - Participation: Total on Student (every student belongs to a university)

- Contains (University–Department) 
  - Cardinality: One university contains many departments (1:N)  
  - Participation: Total on Department

- Grouped by (Program–Department) 
  - Cardinality: Many programs grouped by one department (N:1)  
  - Participation: Total on Program

- Enroll (Student–Program) 
  - Cardinality: Many students enroll in many programs (M:N)  
  - Participation: Partial (students may or may not enroll)

- *Offers (Program–Course)*  
  - Cardinality: One program offers many courses (1:N)  
  - Participation: Partial on Course

- Teach (Instructor–Course)  
  - Cardinality: Many instructors can teach many courses (M:N)  
  - Participation: Partial on both sides

---

### Extension (Prerequisite / Billing):

- Prerequisite is modeled as an attribute of the *Course* entity.  
  - It likely refers to the course code of another course. This could be better represented as a recursive relationship on the Course entity, where a course has another course as its prerequisite.

---

### Design Choices:

- Chose *Student, **Course, **Instructor, **Program, **Department, and **University* as entities because they represent core components of a typical academic system.
- Many-to-many relationships like Enroll and Teach reflect real-world flexibility (e.g., students taking multiple programs or instructors teaching multiple courses).
- Prerequisite as an attribute was a simplification, but a recursive relationship might better support complex rules (e.g., multiple prerequisites).
- All keys and attributes were chosen based on logical identifiers (like Admission number, Program ID, etc.).



## RESULT
ER diagram for University is created successfully.

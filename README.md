# University-Timetable-Generator

A constraint-based system for automatically generating **conflict-free university timetables** using Python and MySQL, with a graphical interface for visualization.

---

## 📌 Overview
This project solves the **University Timetabling Problem** by modeling it as a  
**Constraint Satisfaction Problem (CSP)**.

The system generates realistic academic schedules while enforcing strict academic rules such as:
- Instructor role separation (Doctor vs Teaching Assistant)
- No time or room conflicts
- Separate schedules per level, semester, and group

---

## 🎯 Project Objectives
- Automatically generate valid timetables
- Prevent instructor, room, and time conflicts
- Separate schedules by:
  - **Level (1–4)**
  - **Semester (1–2)**
  - **Group (A / B / C)**
- Simulate real university scheduling rules
- Provide a clean and usable GUI

---

## 🧠 Intelligent System Concept
The problem is formulated as a **Constraint Satisfaction Problem (CSP)**:

### Variables
- Course sessions (Lecture / Section / Lab)

### Domains
- Time slots
- Rooms
- Instructors

### Hard Constraints
- No instructor teaches two sessions at the same time
- No room is double-booked
- Doctors teach **lectures only**
- Teaching Assistants teach **sections and labs only**
- Maximum **4 sessions per day**
- Sessions distributed across **4 days**
- No overlap between different levels

---

## 🏗 System Architecture

---

## 🗄 Database Design

### Main Tables
- `courses`
- `instructors`
- `instructor_courses`
- `rooms`
- `timeslots`
- `timetable`

### Relationships
| Relation | Type |
|--------|------|
Courses ↔ Instructors | Many-to-Many |
Courses ↔ Timetable | One-to-Many |
Instructors ↔ Timetable | One-to-Many |
Rooms ↔ Timetable | One-to-Many |
Levels ↔ Timetable | One-to-Many |
Groups ↔ Timetable | One-to-Many |

Relational integrity ensures conflict-free scheduling.

---

## 🛠 Technologies Used
- **Python 3**
- **MySQL**
- **Tkinter (GUI)**
- **PyMySQL**

---

## ✨ Features
- Automatic timetable generation for **Semester 1 & 2**
- Independent schedules for each level and group
- Color-coded sessions:
  - 🟦 Lecture (LEC)
  - 🟩 Section (SEC)
  - 🟧 Lab (LAB)
- Realistic academic distribution
- Conflict-free results

---

## ▶️ How to Run

### 1️⃣ Requirements
- Python 3.10+
- MySQL Server
- Install dependencies:
```bash
pip install pymysql

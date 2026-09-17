# Student Grade Tracker

A desktop Java/Swing application for recording and analyzing student grades
across a fixed subject set (Mathematics, English, Science).

## Overview
Teachers can maintain a student roster, record per-subject grades, and get
instant averages, letter grades, and class-wide analytics — all persisted
to a local CSV file so data survives between sessions.

## Features
- **Student Management** — add/remove students, duplicate-name prevention
- **Grade/Assessment Management** — set grades per subject with validation
  (0–100 range enforced at the model layer, not just the UI)
- **Reporting & Analytics** — per-subject class averages, top performer,
  at-risk student detection (average below a configurable threshold)
- **Persistence** — auto-loads on startup and saves on exit / on demand
- **Reset** — clear all data with a confirmation prompt

## Technologies / Tools Used
- Java (Swing for the GUI)
- No external dependencies — pure JDK

## Project Structure
```
StudentGradeTracker/
├── README.md
├── statement.md
├── docs/
│   └── requirements.md
└── src/
    ├── Subject.java
    ├── Student.java
    ├── StudentManager.java        (Module 1: Student Management)
    ├── GradeManager.java          (Module 2: Grade/Assessment Management)
    ├── ReportGenerator.java       (Module 3: Reporting & Analytics)
    ├── FileStorageManager.java    (CSV persistence)
    ├── GradeValidator.java        (shared validation)
    ├── InvalidGradeException.java
    ├── StudentNotFoundException.java
    └── GUI.java                   (entry point / UI layer)
```

## Steps to Install & Run
1. Make sure you have a JDK installed (Java 11+): `java -version`
2. Clone this repository
3. From the `src/` folder, compile all files:
   ```
   javac *.java
   ```
4. Run the application:
   ```
   java GUI
   ```
5. A `grades.csv` file will be created in `src/` the first time you save —
   this is where your data persists between runs.

## Instructions for Testing
- **Add a student**: type a name in the top field, click "Add Student".
  Try adding the same name twice — it should refuse the duplicate.
- **Set a grade**: pick a student and subject from the dropdowns, enter a
  number, click "Set Grade". Try a value like `150` or `-5` — it should be
  rejected with a message instead of being stored.
- **Report**: click "Full Report" to see class averages, top performer, and
  at-risk students.
- **Persistence**: close and reopen the app — your data should still be there.
- **Reset**: click "Reset All" and confirm — the roster should empty out.

## Screenshots
<img width="920" height="620" alt="{D72CA09E-4411-4DC3-A797-D29826AE590B}" src="https://github.com/user-attachments/assets/4f66aacf-1af5-4beb-8952-32262e8f6998" />
<img width="916" height="607" alt="{0A17E98E-83D4-4015-8160-BFCAE7662EDF}" src="https://github.com/user-attachments/assets/7c64baae-289c-49f8-92d2-8c1cc4791973" />
<img width="919" height="612" alt="{E2B477FD-BA29-4007-9EE5-4CC4155A3A17}" src="https://github.com/user-attachments/assets/b2a8b93c-dd9c-4cfa-9460-03ff69b39106" />

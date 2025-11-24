# StudentRecordManagementSystem_Qt
GUI-based C++ Student Record Management System using Qt.
A lightweight, modular, and extensible desktop application built with Qt (C++), designed to manage basic student information with persistent storage using a flat-file (CSV-style) backend.
This project was developed as part of an academic requirement but follows industry-aligned structure, design decisions, and coding practices.

Overview

The Student Record Management System provides a minimal yet functional interface for managing student data.
It enables users to create, update, remove, and browse records through an event-driven GUI.

The application operates on a plain-text data store to keep the implementation transparent, accessible, and easy to audit.
All records are persisted automatically and can be edited without requiring a database engine.

Key Features

Add Record
Creates a new student entry and appends it to the storage file.

Update Record
Rewrites the existing entry identified by Roll Number.

Delete Record
Removes a selected record from the file while preserving data integrity.

Sequential Navigation
Allows users to browse records line-by-line.

State-Aware UI Controls
Buttons are automatically enabled or disabled depending on the current operation.

CSV-Compatible Format
Data stored as comma-separated values for portability and ease of inspection.

Record Structure

Each record is written in the following order:

Name,RollNumber,FatherName,Caste,District,GPA


Example:

Ali Ahmed,21SW102,Ahmed Khan,Syed,Khairpur,3.65

Tech Stack
Component	Technology
Language	C++17
Framework	Qt 5/6 (Widgets)
Build System	qmake / CMake
IDE	Qt Creator
Storage	Flat file (students.txt)
Project Layout
.
├── main.cpp
├── mainwindow.h
├── mainwindow.cpp
├── mainwindow.ui
├── students.xlsx
├── resources/
│   └── icons/
├── screenshots/
│   └── *.png
└── README.md

Build & Run
Using Qt Creator

Open the project (.pro or CMakeLists.txt).

Configure an appropriate kit (MinGW/MSVC).

Build → Run.

Manual Build (qmake)
qmake StudentRecordManagementSystem.pro
make
./StudentRecordManagementSystem

Manual Build (CMake)
cmake -B build
cmake --build build
./build/StudentRecordManagementSystem

Implementation Notes

The application uses a line-based parser to load and split CSV fields.

Updates and deletions use a temporary file swap technique to prevent corruption.

All GUI interactions are driven through Qt’s signal/slot mechanism.

The design intentionally avoids unnecessary dependencies to keep the codebase minimal and easy to understand.

Planned Improvements

The following enhancements are optional but can be integrated easily:

Input validation for numeric fields (e.g., GPA).

Search by Roll Number.

Sort functionality (Name, GPA, District).

Export to CSV for Excel compatibility.

Replace file backend with SQLite.

How to Contribute

Fork the repository

Create a new feature branch

Commit changes with clear messages

Submit a pull request

Author

Muhammad Essa Arijo
Department of Software Engineering
Mehran University of Engineering & Technology (MUET), SZAB Campus
Batch: K25SW

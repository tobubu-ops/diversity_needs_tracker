# diversity_needs_tracker

Diversity Needs Tracker – GUI Application

Overview

The Diversity Needs Tracker is a Python-based GUI application developed as a Minimum Viable Product (MVP) within the Employee Management Systems (EMS) domain.
It enables authorised users to record, view, update, and export employee diversity and workplace accommodation needs in a structured and consistent manner.

The application is designed for assessment purposes and uses synthetic (fake) employee data only. It demonstrates key software engineering principles including object-oriented design, GUI-based interaction, CSV persistence, validation, exception handling, and testable logic.
 
Key Features
•	Graphical User Interface (GUI) built using Tkinter
•	Add and edit employee diversity needs records
•	Enforces unique Employee IDs
•	Employee ID is immutable during record edits
•	Mandatory fields with clear validation messages
•	Dropdown fields with a default “Select…” option to enforce deliberate input
•	Calendar date picker for request and review dates
•	Read from and write to a CSV file
•	Export records to CSV for reporting or analysis
•	Modular code structure supporting maintainability and testability
 
Employee ID Rules
•	Employee IDs must follow the format:
EMP + three digits (e.g. EMP001, EMP123)
•	Duplicate Employee IDs are not allowed
•	When editing a record, the Employee ID is locked and cannot be changed
 
Mandatory Fields

The following fields are mandatory and validated before a record can be saved:
•	Employee ID
•	Full Name
•	Department
•	Division
•	Category
•	Priority
•	Status
•	Request Date
•	Review Date

Dropdown fields must not remain at the default “Select…” value.

(Notes are optional by default but can be made mandatory if required.)
 
Project Structure
diversity_needs_tracker/
│
├── main.py
├── data/
│   └── diversity_needs.csv
│
├── models/
│   └── record.py
│
├── services/
│   ├── validator.py
│   └── csv_repository.py
│
├── ui/
│   ├── main_window.py
│   └── record_form.py
│
├── tests/
│   ├── test_validator.py
│   └── test_csv_repository.py
│
└── README.md
Separation of concerns is maintained:
•	models – data structures
•	services – validation and CSV persistence
•	ui – GUI components
 
Requirements
•	Python 3.x
•	Standard Library modules:
o	tkinter
o	csv
o	datetime
•	Optional (recommended) dependency for calendar picker:
pip install tkcalendar


If tkcalendar is not installed, the application falls back to manual date entry using the YYYY-MM-DD format.
 
How to Run the Application
1.	Ensure Python 3.x is installed.
2.	Navigate to the project root directory.
3.	(Optional) Install calendar picker support:
pip install tkcalendar
3.	
4.	Run the application:
python main.py


The GUI window will open displaying the Diversity Needs Tracker dashboard.
 
CSV File

An initial CSV file is included at:
data/diversity_needs.csv
This file:
•	Demonstrates CSV read functionality
•	Acts as a template for imports
•	Is overwritten when records are saved/exported

The CSV headers must remain unchanged:
employee_id,full_name,department,division,category,priority,status,request_date,review_date,notes
 
Testing
•	Validation logic is implemented as pure functions, enabling deterministic unit testing.
•	Example tests are included using pytest for:
o	Field validation
o	Employee ID rules
o	CSV read/write round-trip behaviour

Tests can be run from the project root using:
pytest
 
Data Ethics and Scope

This application uses synthetic employee data only and is intended solely for educational and assessment purposes.
In a real organisational environment, handling diversity and accommodation data would require additional security, access control, and governance measures, which are outside the scope of this MVP.

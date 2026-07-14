# 🎒 Student Data Organizer — Python Basics Project

A menu-driven console application for managing student records — supporting add, view, update, delete, and subject-tracking operations using Python data structures like lists, dictionaries, sets, and tuples.

---

## 📌 Project Overview

| Property | Details |
|---|---|
| **Language** | Python 3 |
| **File** | `03_project.py` |
| **Type** | Console-based, menu-driven CRUD application |
| **Key Concepts** | Functions, Lists, Dictionaries, Sets, Tuples, `while` loops, `for...else` |

---

## ⚙️ How It Works

The program runs an infinite `while True` menu loop offering six options:

| Option | Action |
|---|---|
| 1 | Add Student |
| 2 | Display All Students |
| 3 | Update Student Information |
| 4 | Delete Student |
| 5 | Display Subjects Offered |
| 6 | Exit |

Each option calls a dedicated function, keeping the program modular and easy to extend.

---

## 🧩 Core Functions

| Function | Purpose |
|---|---|
| `add_student()` | Collects name, age, DOB, student ID, grade, and subjects; stores each student as a dictionary (with a nested tuple for `student_id` + `dob`) inside `student_list`; adds each subject to a global `subjects_offered` set |
| `display_students()` | Loops through `student_list` and prints each student's ID, name, age, grade, and subjects in a readable format |
| `student_information()` | Looks up a student by ID and allows updating either their **age** or **subjects**; uses a `for...else` to report "Student ID not found" if no match is found |
| `del_student()` | Looks up a student by ID and removes them from `student_list`; uses `for...else` to handle a not-found case |
| `subject_offered()` | Displays every unique subject collected so far across all students, using the `subjects_offered` set |

---

## 🗂️ Data Structures Used

| Structure | Used For |
|---|---|
| **List** (`student_list`) | Storing all student records (each as a dictionary) |
| **Dictionary** (`student_details`) | Structuring each student's data — ID, name, age, grade, subjects, info |
| **Set** (`subjects_offered`) | Automatically de-duplicating subjects across all students |
| **Tuple** (`student_info`) | Bundling `student_id` and `dob` together as a fixed, immutable pair inside each student record |
| **List comprehension** | Cleaning up subject input, e.g. `[s.strip() for s in subjects]` |

---

## 🧪 Concepts Practiced

- Structuring a program into **reusable functions** rather than one long script
- Using a **dictionary of mixed types** (including a nested tuple) to represent a real-world entity (a student)
- Leveraging a **set** to automatically track unique subjects without manual duplicate-checking
- Using **`for...else`** to cleanly handle "not found" scenarios after searching a list
- Parsing comma-separated user input into a cleaned list with `.split(",")` and a list comprehension
- Building a persistent **menu loop** that keeps the program running until the user exits

---

## ▶️ How to Run

```bash
python 03_project.py
```

Select an option from the menu (1–6) to add, view, update, delete, or list students and their subjects. Choose option 6 to exit.

---

## 🚧 Known Limitations & Improvement Opportunities

| Issue | Explanation | Suggested Fix |
|---|---|---|
| Goodbye messages print on invalid input, not on exit | The two `"thankyouu..."` print statements are indented inside the `else` (invalid option) branch, so they only appear after an invalid entry — not when the user actually exits via option 6 | Move those two print statements to right after the `break` in the `option == "6"` branch |
| No input validation on numeric fields | `age` and `student_id` are cast directly with `int()`, so a non-numeric entry (e.g. accidentally typing a letter) would crash the program with a `ValueError` | Wrap these inputs in a `try/except` block to catch invalid entries and re-prompt the user |
| Data isn't saved between runs | All student data is stored only in memory (`student_list`), so it's lost when the program closes | Extend the project to save/load records from a file (e.g. CSV or JSON) for persistence |

---

## 💡 What I Learned

- How to break a multi-feature program into clean, single-purpose **functions**
- Practical use of **sets** for automatic de-duplication (subjects offered across students)
- Combining different data structures — **list of dictionaries**, with a **tuple** nested inside — to model a real entity
- The value of **`for...else`** for concisely handling "not found" logic after a search loop
- How small indentation choices affect *when* code runs — tracing through this script surfaced a genuine bug in the exit-message logic
- The importance of input validation and thinking about **data persistence** as natural next steps for a CRUD-style console app

---

## 📁 Repository Contents

```
student-data-organizer/
│
├── 03_project.py     # Main Python script
└── README.md          # Project documentation
```

---

## 👤 Author

**Prerita Morashiya**

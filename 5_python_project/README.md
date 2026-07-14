# 🏢 Employee Management System — Python OOP Project

A console-based Object-Oriented Programming project demonstrating class inheritance, method overriding, and polymorphism through a simple People/Employee/Developer record system.

---

## 📌 Project Overview

| Property | Details |
|---|---|
| **Language** | Python 3 |
| **File** | `05_project.py` |
| **Type** | Console-based OOP application |
| **Key Concepts** | Classes, Inheritance, `super()`, Method Overriding, Polymorphism, Lists of Objects |

---

## 🏗️ Class Structure

| Class | Inherits From | Attributes | Purpose |
|---|---|---|---|
| `Person` | — | name, age | Base class representing a general person |
| `Employee` | `Person` | + emp_id, salary | Extends Person with employment details |
| `Developer` | `Employee` | + language | Extends Employee with a programming language specialty |

This forms a clean **three-level inheritance chain**: `Person` → `Employee` → `Developer`, with each subclass building on the one before it using `super().__init__(...)`.

### Method Overriding

Each class overrides the `display()` method to show progressively more detail:

```python
Person.display()     -> "Person: Name, Age"
Employee.display()   -> "Employee: Name, Age, ID, Salary"
Developer.display()  -> "Developer: Name, Age, ID, Salary, Language"
```

This is a practical demonstration of **polymorphism** — calling `.display()` on any object in `all_people` automatically runs the correct version for its class, without needing to check the object's type first.

---

## ⚙️ How It Works

The program runs a `main_menu()` loop offering five options:

| Option | Action |
|---|---|
| 1 | Create Person |
| 2 | Create Employee |
| 3 | Create Developer |
| 4 | Show All Records |
| 5 | Exit |

All created objects — regardless of class — are stored together in a single shared list, `all_people`.

---

## 🧩 Core Functions

| Function | Purpose |
|---|---|
| `create_person()` | Collects name and age, creates a `Person` object, and appends it to `all_people` |
| `create_employee()` | Collects name, age, employee ID, and salary; creates an `Employee` object and appends it to `all_people` |
| `create_developer()` | Collects name, age, employee ID, salary, and programming language; creates a `Developer` object and appends it to `all_people` |
| `show_details()` | Loops through `all_people` and calls `.display()` on each object, automatically printing the correct level of detail thanks to polymorphism |
| `main_menu()` | Runs the main input loop, routing each menu choice to the correct function |

---

## 🧪 Concepts Practiced

- Defining classes with `__init__` constructors and instance attributes
- **Single-chain inheritance** across three classes (`Person` → `Employee` → `Developer`)
- Using **`super().__init__(...)`** to reuse parent-class initialization instead of duplicating code
- **Method overriding** — each subclass provides its own `display()` implementation
- **Polymorphism** — storing different object types in one list and calling the same method name on each, letting Python resolve the correct version at runtime
- Structuring a program around a **menu-driven loop** that delegates to dedicated functions

---

## ▶️ How to Run

```bash
python 05_project.py
```

Use the menu to create People, Employees, or Developers, then choose **Show All** to see every record printed with the appropriate level of detail for its class. Choose option 5 to exit.

---

## 🚧 Known Limitations & Improvement Opportunities

| Issue | Explanation | Suggested Fix |
|---|---|---|
| No input validation | `age` and `salary` are cast directly with `int()`/`float()`, so non-numeric input would crash the program with a `ValueError` | Wrap these inputs in a `try/except` block to catch invalid entries and re-prompt |
| No duplicate or format checking on Employee ID | `emp_id` is accepted as free-text with no uniqueness check | Add a check against existing `emp_id` values in `all_people` before creating a new Employee/Developer |
| Records aren't saved between runs | All objects live only in memory (`all_people`), so data is lost when the program closes | Extend the project to serialize records to a file (e.g. JSON) for persistence |

---

## 💡 What I Learned

- How to design a clean **inheritance hierarchy** where each class adds meaningful new attributes and behavior
- The role of **`super()`** in reusing parent-class logic instead of re-writing constructor code
- How **method overriding** lets subclasses customize behavior while keeping a consistent method name (`display()`)
- A concrete example of **polymorphism** — one list, multiple object types, one method call, correct behavior every time
- How OOP design keeps a program more organized and extensible compared to using separate dictionaries or functions for each entity type

---

## 📁 Repository Contents

```
employee-management-system/
│
├── 05_project.py     # Main Python script
└── README.md          # Project documentation
```

---

## 👤 Author

**Prerita Morashiya**

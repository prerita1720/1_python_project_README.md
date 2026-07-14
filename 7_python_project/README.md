# 🧰 Multi-Utility Toolkit — Python Modules Project

A menu-driven console application bundling several everyday utilities into one toolkit — date/time operations, math calculations, random data generation, file handling, UUID generation, and a built-in Python module explorer.

---

## 📌 Project Overview

| Property | Details |
|---|---|
| **Language** | Python 3 |
| **File** | `07_project.py` |
| **Type** | Console-based, multi-menu utility application |
| **Modules Used** | `datetime`, `time`, `math`, `random`, `uuid` |
| **Key Concepts** | Nested Menus, Modular Functions, File I/O, Exception Handling, Standard Library Usage |

---

## ⚙️ How It Works

The program opens on a **main menu** with seven options, each leading into its own dedicated sub-menu (except UUID generation and Exit, which act immediately):

| Option | Leads To |
|---|---|
| 1 | Datetime & Time Operations Menu |
| 2 | Mathematical Operations Menu |
| 3 | Random Data Generation Menu |
| 4 | Generate a UUID (`uuid.uuid4()`) |
| 5 | File Operations Menu |
| 6 | Explore Module Attributes (`dir()`) |
| 7 | Exit |

Each sub-menu runs its own loop and returns to the main menu when the user selects "Back".

---

## 🕒 Datetime & Time Menu

| Option | Feature | How It Works |
|---|---|---|
| 1 | Current Date & Time | `datetime.datetime.now()` |
| 2 | Date Difference | Parses two `YYYY-MM-DD` dates with `strptime()` and calculates the absolute day difference |
| 3 | Custom Date Formatting | Formats the current date/time with `strftime("%d-%m-%Y %I:%M %p")` |
| 4 | Stopwatch | Measures elapsed time between two key presses using `time.time()` |
| 5 | Countdown Timer | Counts down from a user-given number of seconds using `time.sleep(1)` |

---

## ➗ Math Menu

| Option | Feature | How It Works |
|---|---|---|
| 1 | Factorial | `math.factorial(n)` |
| 2 | Compound Interest | `P × (1 + R/100)^T` |
| 3 | Trigonometry | Converts degrees to radians with `math.radians()`, then computes sin/cos/tan |
| 4 | Area of Circle | Custom `circle_area(r)` function using `math.pi * r * r` |

---

## 🎲 Random Menu

| Option | Feature | How It Works |
|---|---|---|
| 1 | Random Number | `random.randint(1, 100)` |
| 2 | Random List | List comprehension generating 5 random numbers between 1–20 |
| 3 | Password Generator | Builds a random password of user-defined length from a mixed character set (letters, digits, symbols) |
| 4 | OTP Generator | 6-digit random number via `random.randint(100000, 999999)` |

---

## 📁 File Menu

| Option | Feature | How It Works |
|---|---|---|
| 1 | Create File | Opens a file in `"w"` mode to create it empty |
| 2 | Write File | Opens a file in `"w"` mode and writes user-provided text (overwrites existing content) |
| 3 | Read File | Opens a file in `"r"` mode and prints its contents, handling `FileNotFoundError` |
| 4 | Append File | Opens a file in `"a"` mode and appends user-provided text on a new line |

---

## 🔎 Module Explorer

- Prompts the user for any built-in module name (e.g. `os`, `sys`, `random`)
- Dynamically imports it with `__import__(name)` and prints all its attributes using `dir()`
- Catches invalid module names with a try/except

---

## 🧪 Concepts Practiced

- Structuring a large program into **nested, self-contained menus**, each with its own loop
- Practical use of Python's **standard library**: `datetime`, `time`, `math`, `random`, `uuid`
- **Dynamic module importing** at runtime with `__import__()` and introspection via `dir()`
- File handling across all major modes: `"w"` (write/create), `"a"` (append), `"r"` (read)
- Exception handling for invalid dates (`ValueError`) and missing files (`FileNotFoundError`)
- Building small **reusable helper functions** (`circle_area()`, `km_to_m()`) separate from menu logic
- Simple **randomized generation** use cases: numbers, lists, passwords, OTPs, and UUIDs

---

## ▶️ How to Run

```bash
python 07_project.py
```

Navigate the main menu to access datetime tools, math calculations, random generators, file operations, UUID generation, or the module explorer. Each sub-menu has its own "Back" option to return to the main menu.

---

## 🚧 Known Limitations & Improvement Opportunities

| Issue | Explanation | Suggested Fix |
|---|---|---|
| `km_to_m()` is defined but never used | The helper function for converting kilometers to meters isn't wired into any menu option | Add a "Unit Converter" option to the Math Menu that calls this function |
| Bare `except:` in `explore()` | Catching all exceptions without specifying a type can hide unexpected errors, not just invalid module names | Catch `ImportError`/`ModuleNotFoundError` specifically instead of a bare `except` |
| No input validation on numeric fields | Several options (factorial, compound interest, circle area, password length) cast input directly with `int()`/`float()`, which would crash on non-numeric input | Wrap these inputs in `try/except` blocks to catch invalid entries and re-prompt |
| Write File always overwrites | `write_file()` uses `"w"` mode, so calling it twice on the same filename replaces the previous content entirely | This may be intentional (distinct from Append), but worth documenting clearly in-app |

---

## 💡 What I Learned

- How to organize a **multi-feature CLI tool** using nested menus instead of one long flat menu
- Practical, hands-on use of several core Python standard library modules in one project
- How `__import__()` and `dir()` can be combined to build a simple **runtime module explorer**
- The differences between file modes (`"w"`, `"a"`, `"r"`) and when each is appropriate
- Building small utility functions (like `circle_area()`) that can be reused across different menu options
- The value of testing every menu path to catch unused code (like `km_to_m()`) and overly broad exception handling

---

## 📁 Repository Contents

```
multi-utility-toolkit/
│
├── 07_project.py     # Main Python script
└── README.md          # Project documentation
```

---

## 👤 Author

**Prerita Morashiya**

# 🧍 Personal Data Collector — Python Basics Project

A beginner-friendly Python script that collects a user's personal details through console input, demonstrates type casting and Python's built-in `type()`/`id()` functions, and classifies the user into an age group using conditional logic.

---

## 📌 Project Overview

| Property | Details |
|---|---|
| **Language** | Python 3 |
| **File** | `01_project.py` |
| **Type** | Console-based interactive script |
| **Key Concepts** | User Input, Type Casting, Data Types, Memory Identity (`id()`), Conditional Logic (`if / elif / else`) |

---

## ⚙️ How It Works

1. Greets the user and explains what the program does
2. Collects personal details via `input()`:
   - Full Name
   - Age
   - Height
   - Weight
   - Email Address
   - Birthdate
3. Converts raw string inputs into proper data types (**type casting**):
   - `age` → `int`
   - `height` → `float` (as `height_cm`)
   - `weight` → `int` (as `weight_kg`)
4. Displays the collected details back to the user
5. Prints the **data type** and **memory ID** of key variables using `type()` and `id()`
6. Classifies the user into an age group using `if / elif / else` logic
7. Ends with a personalized thank-you message

---

## 🧮 Age Classification Logic

| Condition | Category |
|---|---|
| age < 0 | Invalid age entered |
| age ≤ 12 | Child |
| 13 ≤ age ≤ 19 | Teenager |
| 20 ≤ age ≤ 35 | Young Adult |
| age ≥ 60 | Senior Citizen |
| Else | Age classification not found |

---

## 🧪 Concepts Practiced

- Taking multiple types of user input with `input()`
- **Type casting** string input into `int` and `float`
- Inspecting variable **data types** with `type()`
- Inspecting variable **memory addresses** with `id()`
- Writing multi-branch **conditional logic** (`if / elif / else`)
- Structuring console output with formatted headers and separators using `print()`

---

## ▶️ How to Run

```bash
python 01_project.py
```

You'll be prompted to enter your name, age, height, weight, email, and birthdate. The script will then display your details, show type/memory information, and classify your age group.

---

## 🚧 Challenges & Solutions

| Challenge | Solution |
|---|---|
| `input()` always returns a string, even for numbers | Applied explicit type casting (`int()`, `float()`) before using values in numeric comparisons |
| Age comparisons (`age < 0`, `age <= 12`, etc.) would fail on string input | Cast `age` to `int` before running it through the classification logic |
| Understanding how Python stores variables in memory | Used `id()` alongside `type()` to inspect each variable's identity, not just its value |
| Keeping console output readable | Used consistent header/separator lines (`"===...==="`) to visually organize each output section |

---

## 💡 What I Learned

- The difference between the **value** of a variable and its **type**, and why input from the console always needs casting before numeric use
- How `id()` reveals that even simple variables are objects with their own memory identity in Python
- How to structure a multi-condition **age classification** system using chained `elif` statements
- The importance of validating input ranges (e.g. handling a negative age) even in a simple script
- How thoughtful `print()` formatting can make a basic console program feel more polished and user-friendly

---

## 📁 Repository Contents

```
personal-data-collector/
│
├── 01_project.py     # Main Python script
└── README.md          # Project documentation
```

---

## 👤 Author

**Prerita Morashiya**

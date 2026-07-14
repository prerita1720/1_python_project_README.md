# 📈 Data Analyzer & Transformer — Python Basics Project

A menu-driven console application for entering a list of numbers and running summary statistics, filtering, sorting, and factorial calculations — built using core Python functions and list operations.

---

## 📌 Project Overview

| Property | Details |
|---|---|
| **Language** | Python 3 |
| **File** | `04_project.py` |
| **Type** | Console-based, menu-driven data analysis tool |
| **Key Concepts** | Functions, Lists, List Comprehensions, Global Variables, `while` loops, Aggregate Calculations |

---

## ⚙️ How It Works

The program runs an infinite `while True` menu loop offering seven options:

| Option | Action |
|---|---|
| 1 | Input Data |
| 2 | Display Data Summary |
| 3 | Calculate Factorial |
| 4 | Filter Data by Threshold |
| 5 | Sort Data |
| 6 | Display Data Statistics |
| 7 | Exit |

Each option calls a dedicated function, keeping the menu logic separate from the data-processing logic.

---

## 🧩 Core Functions

| Function | Purpose |
|---|---|
| `input_data()` | Reads space-separated numbers from the user and stores them as an integer list in the `data` global variable, using a list comprehension |
| `display_summary()` | Prints the total count, sum, minimum, and maximum of the current dataset |
| `calculate_factorial()` | Calculates the factorial of a user-provided number using an iterative loop |
| `filter_data()` | Filters the dataset to only values above a user-provided threshold, using a list comprehension |
| `sort_data()` | Sorts the dataset in ascending or descending order based on user choice |
| `display_statistics()` | Calculates and prints the minimum, maximum, and average of the dataset |

---

## 🧪 Concepts Practiced

- Structuring a program into **reusable functions**, each handling one specific task
- Using the `global` keyword to update a shared `data` list from within a function
- **List comprehensions** for parsing input (`[int(x) for x in input(...).split()]`) and filtering (`[x for x in data if x > t]`)
- Aggregate calculations using built-in functions: `sum()`, `len()`, `min()`, `max()`
- Calculating **average** manually via `sum(data) / len(data)`
- Iterative **factorial calculation** using a `for` loop and running product
- In-place list sorting with `.sort(reverse=...)`, driven by user input
- Guarding against empty data with `if data:` checks before running calculations

---

## ▶️ How to Run

```bash
python 04_project.py
```

Select an option from the menu (1–7). Start with **Input Data** to populate the dataset before using the summary, filter, sort, or statistics options. Choose option 7 to exit.

---

## 🚧 Known Limitations & Improvement Opportunities

| Issue | Explanation | Suggested Fix |
|---|---|---|
| No validation on numeric input | `input_data()` and `calculate_factorial()` cast directly with `int()`, so non-numeric input would crash the program with a `ValueError` | Wrap these inputs in a `try/except` block to catch invalid entries and re-prompt |
| Factorial doesn't guard against negative numbers | `calculate_factorial()` silently returns `1` for a negative input instead of flagging it as invalid (factorials aren't defined for negative numbers) | Add a check like `if n < 0: print("Factorial is undefined for negative numbers")` before the loop |
| Re-entering data overwrites the previous dataset | Calling `input_data()` again fully replaces `data` rather than appending to it | Could be intentional, but worth documenting — or add an "append vs. replace" prompt if accumulation is desired |

---

## 💡 What I Learned

- How to organize a multi-feature console tool into clean, single-purpose **functions**
- Using the **`global`** keyword correctly to modify a variable defined outside a function's scope
- Writing concise **list comprehensions** for both parsing input and filtering data
- The difference between calculating summary stats manually (e.g. average) versus relying on built-in functions (`min`, `max`, `sum`)
- Building an iterative algorithm (factorial) from scratch using a simple `for` loop
- The importance of guarding against edge cases — empty datasets, invalid input, and negative numbers — even in a small utility script

---

## 📁 Repository Contents

```
data-analyzer-transformer/
│
├── 04_project.py     # Main Python script
└── README.md          # Project documentation
```

---

## 👤 Author

**Prerita Morashiya**

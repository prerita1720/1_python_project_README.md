# 🔢 Pattern Generator & Number Analyzer — Python Basics Project

A menu-driven console program built in Python that lets the user generate star patterns or analyze a range of numbers for odd/even classification and summation, using loops and conditional logic.

---

## 📌 Project Overview

| Property | Details |
|---|---|
| **Language** | Python 3 |
| **File** | `02_project.py` |
| **Type** | Console-based, menu-driven interactive script |
| **Key Concepts** | `while` loops, `for` loops, `for...else`, Conditional Logic, Modulus Operator, f-strings |

---

## ⚙️ How It Works

1. Displays a welcome message describing the program's purpose
2. Enters a `while(True)` loop that repeatedly shows a menu with three options:
   - **1.** Generate Pattern
   - **2.** Analyze a Range of Numbers
   - **3.** Exit
3. Based on the user's choice:
   - **Option 2 — Number Analysis:** Takes a start and end value, then loops through the range, printing whether each number is **Odd** or **Even** (using the modulus operator `%`), and uses a `for...else` block to print the **sum of all numbers** in the range once the loop completes
   - **Option 1 — Pattern Generation:** Takes the number of rows and prints a right-angled triangle pattern using `*` characters, with one more star added per row
   - **Option 3 — Exit:** Breaks out of the loop and ends the program
4. Prints a goodbye message once the loop exits

---

## 🧮 Sample Logic

**Odd/Even check:**
```python
if num % 2:
    print(f"Number {num} is Odd")
else:
    print(f"number{num} is even")
```

**Pattern generation (for n = 4):**
```
*
* *
* * *
* * * *
```

---

## 🧪 Concepts Practiced

- Building a **menu-driven program** using an infinite `while(True)` loop with a `break` condition
- Using `for` loops combined with `range()` to iterate over a numeric range
- The `for...else` construct — printing the total sum only after the loop completes without breaking
- Using the **modulus operator** (`%`) to classify numbers as odd or even
- Building simple **pattern printing** logic using nested string repetition (`'* ' * i`)
- Formatting output dynamically with **f-strings**

---

## ▶️ How to Run

```bash
python 02_project.py
```

You'll see a menu where you can repeatedly choose to generate a pattern, analyze a number range, or exit the program.

---

## 🚧 Known Limitations & Improvement Opportunities

While reviewing this script, a couple of structural issues worth flagging (and fixing in a future revision):

| Issue | Explanation | Suggested Fix |
|---|---|---|
| Pattern-printing loop runs on every menu choice | The `for i in range(1, n + 1)` block that prints the pattern sits outside the `if user_input == 1` block, so it re-runs every loop iteration (using whichever `n` was last set) regardless of the option chosen | Indent the pattern-printing `for` loop so it's nested inside `if user_input == 1:` |
| `n` can be undefined on first run | If the user picks Option 2 before ever picking Option 1, `n` hasn't been created yet, which would raise a `NameError` when the (misplaced) pattern loop tries to run | Initialize `n = 0` before the `while` loop, or move the pattern loop inside the `if user_input == 1` block as above |
| Minor typo in output text | `"number{num} is even"` is missing a space after "number" | Change to `f"Number {num} is Even"` for consistent formatting with the "Odd" message |

These don't stop the core logic (pattern generation and number analysis) from working when run in isolation, but fixing the indentation would make the menu behave exactly as intended on every choice.

---

## 💡 What I Learned

- How to structure a **menu-driven program** that keeps running until the user chooses to exit
- The behavior of the **`for...else`** construct, and how it differs from putting code after a loop unconditionally
- How **indentation controls scope** in Python — and how a small indentation slip can cause code to run in the wrong place or at the wrong time
- Practical use of the **modulus operator** for odd/even classification
- Building simple visual output (patterns) using string multiplication instead of nested loops
- The value of tracing through code line-by-line to catch logic bugs that don't throw an error but still behave unexpectedly

---

## 📁 Repository Contents

```
pattern-generator-number-analyzer/
│
├── 02_project.py     # Main Python script
└── README.md          # Project documentation
```

---

## 👤 Author

**Prerita Morashiya**

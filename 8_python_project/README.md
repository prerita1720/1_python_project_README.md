# 💰 Smart Expense Tracker — Python Data Analysis Project

A console-based expense tracking application that combines file-backed data storage with `pandas` data cleaning, summary statistics, category-wise reporting, and multi-chart visualizations using `matplotlib` and `seaborn`.

---

## 📌 Project Overview

| Property | Details |
|---|---|
| **Language** | Python 3 (Jupyter Notebook) |
| **File** | `smart_expenses_tracker.ipynb` |
| **Type** | Console-based expense management & visualization tool |
| **Libraries Used** | `pandas`, `numpy`, `matplotlib`, `seaborn`, `os` |
| **Key Concepts** | OOP, CSV Persistence, Data Cleaning, Aggregation, Multi-Chart Visualization |

---

## 🏗️ Class Structure

| Class | Purpose |
|---|---|
| `ExpenseTracker` | Encapsulates all expense operations — loading, cleaning, adding, summarizing, reporting, and visualizing expense data backed by a CSV file (`expenses.csv`) |

---

## 🧩 Core Methods

| Method | Purpose |
|---|---|
| `__init__()` | Loads `expenses.csv`, auto-creating it with sample data if it doesn't exist yet, then cleans the loaded data |
| `create_default_file()` | Generates a starter CSV with two sample expense rows (Food, Transport) so the app works out of the box |
| `clean_data()` | Drops null rows, converts `Date` to proper `datetime`, and ensures `Amount` is stored as `float` |
| `add_expense()` | Validates that the amount is positive, appends a new expense row via `pd.concat`, and saves the updated data back to CSV |
| `get_summary()` | Prints total and average expense using `numpy.sum()` and `numpy.mean()` |
| `generate_report()` | Prints total spend grouped by `Category` using `groupby().sum()` |
| `visualize()` | Builds a 2×2 grid of charts summarizing spending patterns |

---

## 📊 Visualizations

| Chart | Type | Shows |
|---|---|---|
| Expenses by Category | Bar chart | Total amount spent per category |
| Expenses Over Time | Line chart | Spending trend across dates |
| Expense Distribution by Category | Pie chart | Percentage share of spend per category |
| Distribution of Expenses | Histogram | Frequency distribution of individual expense amounts |

All four charts are rendered together in a single `matplotlib` figure using `plt.subplot(2, 2, ...)`.

---

## ⚙️ How It Works

The program runs a `main()` loop offering five options:

| Option | Action |
|---|---|
| 1 | Add Expense |
| 2 | Summary |
| 3 | Report (by Category) |
| 4 | Visualize |
| 5 | Exit |

Every added expense is immediately persisted to `expenses.csv`, so data survives across sessions.

---

## 🧪 Concepts Practiced

- Structuring a data application around a single **class** that owns both its data and its file
- **Auto-initializing** a data file with sensible defaults if none exists, so the app works immediately for a new user
- **Data cleaning** with `pandas` — handling nulls, enforcing correct `datetime` and `float` types
- Validating input (rejecting non-positive amounts) before writing to the dataset
- Appending new rows to an existing DataFrame with `pd.concat()` instead of the deprecated `.append()`
- Aggregating data with `groupby()` for category-wise reporting
- Building a **multi-panel visualization** (bar, line, pie, histogram) in a single figure using `plt.subplot()`
- Styling plots with `seaborn.set(style="whitegrid")` for a cleaner look

---

## ▶️ How to Run

```bash
jupyter notebook smart_expenses_tracker.ipynb
```

Or convert and run as a script:

```bash
jupyter nbconvert --to script smart_expenses_tracker.ipynb
python smart_expenses_tracker.py
```

Use the menu to add expenses, view summaries, generate category reports, or open the visualization dashboard. All data is stored in `expenses.csv` in the same directory.

---

## 🚧 Known Limitations & Improvement Opportunities

| Issue | Explanation | Suggested Fix |
|---|---|---|
| Leftover shell command inside a code cell | The notebook shows a `SyntaxError` triggered by a stray line (`echo "# Smart Expense Tracker" > README.md`) accidentally left inside a Python cell instead of a terminal | Remove that line from the notebook cell, or move it to an actual terminal/shell if the intent was to generate a README file |
| No validation on date format | `add_expense()` passes the date straight to `pd.to_datetime()`; an incorrectly formatted date would raise an unhandled exception | Wrap the date parsing in a try/except and re-prompt on failure |
| No validation on numeric `Amount` input in the menu | `float(input("Amount: "))` in `main()` would crash on non-numeric input | Wrap this input in a try/except block |
| Visualization requires at least one row per chart type | Pie/bar/line charts would behave unexpectedly with very little or single-category data | Add a minimum-data check before calling `visualize()` |

---

## 💡 What I Learned

- How to design a small data application around a class that manages its own **persistent CSV storage**
- Writing a **data cleaning pipeline** with `pandas` (dropping nulls, correcting types) that runs automatically on load
- The importance of validating input (like rejecting negative amounts) before it reaches the dataset
- Using `pd.concat()` to safely add new rows to an existing DataFrame
- Aggregating and summarizing data with `groupby()` for category-level insights
- Building a **multi-chart dashboard** in a single figure using `matplotlib`'s subplot grid
- How small mistakes — like a stray shell command pasted into a code cell — can break an otherwise working notebook, and the value of testing every cell end-to-end before sharing it

---

## 📁 Repository Contents

```
smart-expense-tracker/
│
├── smart_expenses_tracker.ipynb   # Main Jupyter Notebook
├── expenses.csv                     # Expense data (auto-created on first run if missing)
└── README.md                        # Project documentation
```

---

## 👤 Author

**Prerita Morashiya**

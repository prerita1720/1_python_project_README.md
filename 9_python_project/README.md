# 📊 Sales Data Analyzer — Python Data Analysis & Visualization Project

A menu-driven console application for loading, exploring, cleaning, and visualizing sales data — combining `pandas` for data manipulation with `matplotlib` and `seaborn` for a wide range of chart types.

---

## 📌 Project Overview

| Property | Details |
|---|---|
| **Language** | Python 3 (Jupyter Notebook) |
| **File** | `9_project.ipynb` |
| **Type** | Console-based data analysis & visualization tool |
| **Libraries Used** | `pandas`, `numpy`, `matplotlib`, `seaborn` |
| **Key Concepts** | OOP, CSV Loading, Data Cleaning, Aggregation, Pivot Tables, Multi-Chart Visualization |

---

## 🏗️ Class Structure

| Class | Purpose |
|---|---|
| `SalesDataAnalyzer` | Encapsulates the full analysis workflow — loading, exploring, cleaning, transforming, aggregating, and visualizing sales data from a CSV file |

---

## 🧩 Core Methods

| Method | Purpose |
|---|---|
| `load_data()` | Reads a CSV file path from the user into a DataFrame, with error handling if loading fails |
| `explore_data()` | Prints the first/last 5 rows, column names, data types, and full dataset info (`.head()`, `.tail()`, `.columns`, `.dtypes`, `.info()`) |
| `clean_data()` | Checks for missing values and fills them with the column mean if any are found |
| `mathematical_operations()` | Calculates a `Profit_Margin` column as `Profit / Sales` |
| `search_sort_filter()` | Sorts records by `Sales` (descending) and filters rows where `Sales > 600` |
| `aggregate_functions()` | Groups by `Region` to total `Sales`, and calculates average `Profit` |
| `statistical_analysis()` | Prints `.describe()`, standard deviation, and variance for numeric columns |
| `create_pivot_table()` | Builds a pivot table of total `Sales` by `Region` and `Product` |
| `visualize_data()` | Generates a bar chart (Sales by Region), line chart (Sales over time), scatter plot (Sales vs Profit), and histogram (Sales distribution) |
| `stack_plot()` | Builds a stacked area chart of `Sales` by `Region` over time |
| `seaborn_visuals()` | Generates a Seaborn boxplot (Sales by Region) and a correlation heatmap |

---

## ⚙️ How It Works

The program runs a `main()` loop offering eight options:

| Option | Action |
|---|---|
| 1 | Load Dataset |
| 2 | Explore Data |
| 3 | Perform DataFrame Operations (Profit Margin + Search/Sort/Filter) |
| 4 | Handle Missing Data |
| 5 | Generate Descriptive Statistics (Aggregation + Statistical Analysis) |
| 6 | Data Visualization (Charts + Stack Plot + Seaborn Visuals) |
| 7 | Save Visualization |
| 8 | Exit |

---

## 🧪 Concepts Practiced

- Structuring a full analysis pipeline inside a single **class**, with each stage as its own method
- Loading external data safely with a **try/except** around `pd.read_csv()`
- **Exploratory data analysis**: head/tail preview, column and dtype inspection, `.info()` summaries
- **Missing value handling** using mean imputation (`fillna(self.data.mean(...))`)
- Deriving new columns (`Profit_Margin`) through **vectorized column arithmetic**
- Sorting and filtering DataFrames with `.sort_values()` and boolean indexing
- **Aggregation** with `groupby()` and descriptive statistics with `.describe()`, `.std()`, `.var()`
- Building a **pivot table** to cross-tabulate Sales by Region and Product
- A wide range of **visualizations**: bar, line, scatter, histogram, stacked area, boxplot, and heatmap

---

## ▶️ How to Run

```bash
jupyter notebook 9_project.ipynb
```

Or convert and run as a script:

```bash
jupyter nbconvert --to script 9_project.ipynb
python 9_project.py
```

Use the menu to load a CSV file, then explore, clean, analyze, and visualize the data.

---

## 🚧 Known Limitations & Improvement Opportunities

| Issue | Explanation | Suggested Fix |
|---|---|---|
| Constructor and destructor use single underscores (`_init_`, `_del_`) instead of double (`__init__`, `__del__`) | Because these aren't real Python dunder methods, they never run automatically — the class currently relies entirely on explicitly calling `load_data()` through the menu rather than through initialization | Rename them to `__init__` and `__del__` so the constructor logic (and optional auto-load via `file_path`) actually fires when the object is created |
| Several methods assume fixed column names (`Sales`, `Profit`, `Region`, `Product`, `Date`) | When tested with a real-world CSV that used different column names (e.g. `Total_Amount`, `Region`, `Product_Category`), the program raised a `KeyError: 'Profit'` in `mathematical_operations()` because that column didn't exist in the loaded file | Make column names configurable (e.g. passed in or auto-detected), or clearly document the expected schema so users load compatible datasets |
| Option 7 ("Save Visualization") has no matching logic in the menu | The menu prints "7. Save Visualization" but there's no `elif choice == "7":` branch to handle it | Add a branch that saves the current figure(s) via `plt.savefig(...)` |
| No validation on missing DataFrame before running operations | Methods like `explore_data()` or `mathematical_operations()` would raise an `AttributeError` if called before a dataset is loaded | Add a check (e.g. `if self.data is None: print("Please load a dataset first")`) at the start of each method |

---

## 💡 What I Learned

- How to structure a full **data analysis pipeline** — load, explore, clean, transform, aggregate, visualize — inside one well-organized class
- The importance of the exact double-underscore syntax for Python's special methods (`__init__`, `__del__`), and how a small typo can silently disable expected behavior
- How to build a **pivot table** with `pd.pivot_table()` to summarize data across two dimensions at once
- Practical experience across a wide range of chart types: bar, line, scatter, histogram, stacked area, boxplot, and correlation heatmap
- The value of testing a "generic" analysis tool against a **real, differently-structured dataset** — it surfaced a genuine column-mismatch bug that wouldn't have shown up with only the originally intended schema
- Why defensive checks (missing data, missing columns) matter for a tool meant to be reused across different CSV files

---

## 📁 Repository Contents

```
sales-data-analyzer/
│
├── 9_project.ipynb   # Main Jupyter Notebook
└── README.md          # Project documentation
```

---

## 👤 Author

**Prerita Morashiya**

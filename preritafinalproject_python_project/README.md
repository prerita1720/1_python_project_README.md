# 🛍️ Indian Retail Business Sales Analysis — Python Data Analysis Project

An end-to-end exploratory data analysis project on a large Indian retail sales dataset — covering data cleaning, business-driven aggregation, correlation analysis, multi-chart visualization, and final data-driven business recommendations.

---

## 📌 Project Overview

| Property | Details |
|---|---|
| **Language** | Python 3 (Jupyter Notebook) |
| **File** | `Prerita_10580_pythonAnalyzers.ipynb` |
| **Dataset** | `Indian_Retail_Business_Sales_Gigantic_Dataset.csv` |
| **Libraries Used** | `numpy`, `pandas`, `matplotlib`, `seaborn` |
| **Key Concepts** | Data Cleaning, EDA, GroupBy Aggregation, Correlation, Time-Based Trends, Multi-Chart Visualization, Business Insights |

---

## 📂 Dataset Fields Used

| Column | Role in Analysis |
|---|---|
| Order_Date | Converted to datetime; used to derive monthly sales trends |
| Region | Grouped to compare revenue across regions |
| Product_Category | Grouped to compare revenue across categories |
| Customer_Type | Grouped to compare revenue by customer type (e.g. New vs Returning) |
| Revenue | Core metric analyzed across nearly every task |
| Discount_Percent | Correlated against Revenue |
| Quantity | Used in distribution analysis |
| Unit_Price | Compared against Revenue in a scatter plot |

---

## ⚙️ Project Workflow

### Task 1 — Import Libraries & Load Dataset
- Imported `numpy`, `pandas`, `matplotlib`, and `seaborn`
- Loaded the CSV dataset and confirmed successful loading
- Displayed dataset shape, and first/last 5 rows for an initial look

### Task 2 — Data Cleaning & Exploratory Data Analysis
- Checked for **missing values** across all columns
- Identified and **removed duplicate rows**
- Converted `Order_Date` to proper `datetime` format (with `errors='coerce'` to safely handle invalid dates)
- Reviewed data types across all columns
- Generated **summary statistics** with `.describe()`
- Examined category distributions for `Region`, `Product_Category`, and `Customer_Type` using `.value_counts()`

### Task 3 — Business Analysis
| Analysis | Method |
|---|---|
| Region-wise Revenue | `groupby('Region')['Revenue'].sum()` |
| Category-wise Revenue | `groupby('Product_Category')['Revenue'].sum()` |
| Customer Type Revenue | `groupby('Customer_Type')['Revenue'].sum()` |
| Monthly Sales Trend | Derived a `Month` period from `Order_Date`, then grouped and summed Revenue |
| Discount vs Revenue Correlation | `.corr()` between `Discount_Percent` and `Revenue` |

### Task 4 — Data Visualization
| # | Chart | Insight Shown |
|---|---|---|
| 1 | Bar Chart | Category-wise revenue comparison |
| 2 | Line Chart | Monthly revenue trend over time |
| 3 | Histogram | Distribution of revenue values |
| 4 | Pie Chart | Revenue share by product category |
| 5 | Scatter Plot | Relationship between discount percentage and revenue |
| 6 | 2×2 Subplot Grid | Region revenue, customer revenue, quantity distribution, and price vs. revenue — combined into one summary figure |

### Task 5 — Final Insights & Business Recommendations
- Identified the **highest-revenue region**, **best-selling category**, **most valuable customer type**, and **peak sales month** using `.idxmax()`
- Noted that discount level has a **moderate impact** on revenue
- Translated findings into actionable business recommendations (see below)

---

## 💼 Business Recommendations

- Retain returning customers
- Focus on high-performing regions and categories
- Use discounts strategically
- Improve low-performing regions
- Plan inventory based on monthly sales trends

---

## 🧪 Concepts Practiced

- Structuring a real-world analysis into clear, numbered **tasks** (Import → Clean → Analyze → Visualize → Conclude)
- **Data cleaning**: detecting missing values, removing duplicates, safely parsing dates with `errors='coerce'`
- **GroupBy aggregation** across multiple business dimensions (Region, Category, Customer Type, Month)
- Deriving a **time-based grouping key** (`Month`) from a datetime column using `.dt.to_period('M')`
- Measuring relationships between variables using `.corr()`
- Producing a wide range of **visualizations** — bar, line, histogram, pie, scatter, and a combined subplot dashboard
- Turning statistical findings into **plain-language business recommendations** — connecting data analysis to real decision-making

---

## ▶️ How to Run

```bash
jupyter notebook Prerita_10580_pythonAnalyzers.ipynb
```

Or convert and run as a script:

```bash
jupyter nbconvert --to script Prerita_10580_pythonAnalyzers.ipynb
python Prerita_10580_pythonAnalyzers.py
```

> **Note:** The notebook currently loads the dataset from a hardcoded local path (`C:\Users\Admin\Downloads\...`). Update `file_path`/the `pd.read_csv(...)` call to point to wherever `Indian_Retail_Business_Sales_Gigantic_Dataset.csv` is stored on your machine, or place the CSV in the same folder as the notebook and use a relative path.

---

## 🚧 Known Limitations & Improvement Opportunities

| Issue | Explanation | Suggested Fix |
|---|---|---|
| Hardcoded absolute file path | `pd.read_csv(r"C:\Users\Admin\Downloads\...")` only works on the original machine/user account | Use a relative path (e.g. `pd.read_csv(file_path)`, which is already defined but unused) so the notebook runs on any machine with the CSV in the project folder |
| `file_path` variable is defined but not actually used | The script defines `file_path = "Indian_Retail_Business_Sales_Gigantic_Dataset.csv"` but then reads from the hardcoded Downloads path instead | Replace the `pd.read_csv(r"C:\...")` call with `pd.read_csv(file_path)` |
| No check for missing values before running `.describe()`/correlation | If missing values exist, some statistics/correlations could be skewed depending on how pandas handles NaNs by default | Decide explicitly whether to drop or impute missing values after inspecting them, rather than proceeding straight to analysis |
| `Order_Date` conversion errors are silently coerced to `NaT` | Using `errors='coerce'` is safe but any invalid dates become `NaT` without being flagged to the user | Add a check like `print(df['Order_Date'].isnull().sum())` after conversion to report how many dates failed to parse |

---

## 💡 What I Learned

- How to structure a full **business analysis project** as a sequence of clear, well-commented tasks
- Practical techniques for **cleaning real-world data** — missing values, duplicates, and inconsistent date formats
- How to derive time-based aggregations (like monthly revenue) from a raw date column
- Using `groupby()` across multiple business dimensions to answer specific, real questions (best region, best category, best customer type)
- Measuring and interpreting **correlation** between a business lever (discount) and an outcome (revenue)
- Building a **dashboard-style subplot grid** to present multiple insights in a single visual
- The importance of translating analysis results into **clear, actionable business recommendations** rather than stopping at the numbers

---

## 📁 Repository Contents

```
indian-retail-sales-analysis/
│
├── Prerita_10580_pythonAnalyzers.ipynb           # Main Jupyter Notebook
├── Indian_Retail_Business_Sales_Gigantic_Dataset.csv   # Source dataset
└── README.md                                      # Project documentation
```

---

## 👤 Author

**Prerita Morashiya**

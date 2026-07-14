# 🎓 Student Performance Analysis — Python Final Project

A data analysis project that builds a small student dataset from scratch, calculates performance metrics, and visualizes results using `pandas` and `matplotlib` — covering gender-wise, subject-wise, and distribution-based insights.

---

## 📌 Project Overview

| Property | Details |
|---|---|
| **Language** | Python 3 (Jupyter Notebook) |
| **File** | `FINAL_PROJECT.ipynb` |
| **Type** | Script-style data analysis & visualization notebook |
| **Libraries Used** | `pandas`, `matplotlib` |
| **Key Concepts** | DataFrame Creation, Aggregation, Derived Columns, Grouping, Data Visualization |

---

## 📂 Dataset

A student dataset is constructed directly in code (no external file needed) with the following fields:

| Column | Description |
|---|---|
| Student_ID | Unique identifier for each student |
| Gender | Male / Female |
| Maths | Marks scored in Maths |
| Science | Marks scored in Science |
| English | Marks scored in English |

10 student records are included, covering a mix of genders and score ranges.

---

## ⚙️ Analysis Steps

| Step | Description |
|---|---|
| 1. Create Dataset | Builds the student dataset as a dictionary and converts it into a `pandas` DataFrame |
| 2. Display Data | Prints the full dataset to inspect the raw records |
| 3. Basic Analysis | Calculates the **average marks** per subject (Maths, Science, English) using `.mean()` |
| 4. Add Total & Percentage | Derives a `Total` column (sum of all three subjects) and a `Percentage` column (`Total / 3`) |
| 5. Gender-Wise Average | Groups students by `Gender` and calculates the average `Percentage` for each group |
| 6. Visualization — Gender Performance | Bar chart comparing average percentage by gender |
| 7. Visualization — Subject Performance | Bar chart comparing average marks by subject |
| 8. Visualization — Percentage Distribution | Histogram showing how student percentages are distributed |

---

## 📊 Key Results

| Subject | Average Marks |
|---|---|
| Maths | 77.8 |
| Science | 80.0 |
| English | 79.8 |

| Gender | Average Percentage |
|---|---|
| Female | 90.0 |
| Male | 68.4 |

---

## 📈 Visualizations

| Chart | Type | Purpose |
|---|---|---|
| Gender-Wise Average Performance | Bar chart | Compares average percentage between Male and Female students |
| Subject-Wise Average Marks | Bar chart | Compares average marks across Maths, Science, and English |
| Percentage Distribution | Histogram | Shows the spread of student percentages across 5 bins |

---

## 🧪 Concepts Practiced

- Creating a **DataFrame from a Python dictionary** without needing an external CSV
- Calculating column-wise averages with `.mean()`
- Deriving new columns (`Total`, `Percentage`) through simple arithmetic on existing columns
- **Grouping** data with `groupby()` to compare performance across categories (Gender)
- Building clear, single-purpose **bar charts** and a **histogram** with `matplotlib`
- Structuring a notebook with clearly numbered, commented steps for readability

---

## ▶️ How to Run

```bash
jupyter notebook FINAL_PROJECT.ipynb
```

Or convert and run as a script:

```bash
jupyter nbconvert --to script FINAL_PROJECT.ipynb
python FINAL_PROJECT.py
```

Run all cells to build the dataset, print the analysis, and display the three charts.

---

## 🚧 Known Limitations & Improvement Opportunities

| Issue | Explanation | Suggested Fix |
|---|---|---|
| Dataset is hardcoded in the notebook | The 10 student records are defined directly in code, so the analysis can't be reused on new data without editing the script | Extend the project to load data from a CSV file (e.g. via `pd.read_csv()`) for reusability |
| Percentage assumes exactly 3 subjects | `Percentage = Total / 3` is hardcoded for three subjects; adding a fourth subject would silently produce an incorrect percentage | Calculate percentage dynamically, e.g. `Total / len(subject_columns)` |
| No handling for missing or invalid marks | The dataset is clean by construction, but a real-world version reading from a file should validate for missing or out-of-range values | Add a data validation step before running calculations |

---

## 💡 What I Learned

- How to construct a **DataFrame directly from a dictionary**, useful for quick prototyping or small, self-contained datasets
- Deriving meaningful new columns (`Total`, `Percentage`) from existing ones using simple vectorized arithmetic
- Using `groupby()` to compare a metric (percentage) across categories (gender)
- Choosing the right chart type for the message: bar charts for categorical comparison, histograms for distribution
- The importance of writing clear, numbered, commented analysis steps so a notebook is easy to follow from top to bottom

---

## 📁 Repository Contents

```
student-performance-analysis/
│
├── FINAL_PROJECT.ipynb   # Main Jupyter Notebook
└── README.md              # Project documentation
```

---

## 👤 Author

**Prerita Morashiya**

# 📊 ITI Student Commute & Performance Analytics Case Study

A comprehensive statistical analysis evaluating whether long travel times impact student performance across five Information Technology Institute (ITI) branches.

---

## 📌 Project Overview

The ITI academic board considered offering a remote attendance option for long-commute students under the assumption that long travel hours hurt academic outcomes. Using Python and statistical methods, this case study tests that hypothesis, cleans messy data, evaluates sampling biases, and delivers an evidence-backed policy recommendation.

---

## 🚀 Key Project Highlights

### 1. Data Cleaning & Wrangling
* **Deduplication:** Filtered raw data down from **271 initial rows to 260 clean student records** by removing duplicate `student_id` entries.
* **Categorical Standardization:** Corrected typos and text casing across string variables (e.g., `mansora` $\to$ `mansoura`, `f/m` $\to$ `female/male`).
* **Type Conversion & Boundary Checks:** Converted text-formatted numbers (e.g., `"45 min"`, `"18.5 hours"`) to numeric values. Handled invalid entries (negative sleep, invalid ages) while preserving genuine long-distance commute outliers (>200 mins).
* **Auditability:** Maintained a complete **Cleaning Log** detailing every rule applied and row dropped.

### 2. Exploratory Data Analysis (EDA)
* **Distribution Skewness:** Commute time proved heavily right-skewed ($CV \approx 74\%$). The **Median (46.60 min)** was selected over the Mean (**60.35 min**) to represent the typical student experience.
* **Regional Disparities:** Cairo logged the highest average commute (Mean: 60.35 min, $SD = 44.87$ min), dragging the national average upward. Regional branches like Assiut showed predictable travel times (Mean: 25.91 min, $SD = 16.13$ min).

### 3. Correlation & Performance Drivers
* **Commute vs. Performance ($r = -0.055$):** Regression models revealed virtually **no correlation** between travel time and final academic scores. Grades remained consistent (~78%–81% average) across all branches regardless of commute length.
* **Study Time Impact ($r = 0.644$):** Weekly study hours demonstrated a strong positive correlation with final grades, proving academic performance is driven by study effort rather than travel constraints.

### 4. Sampling & Policy Recommendation
* **Evaluating Bias:** Highlighted survey sampling flaws, including voluntary portal access limitations and Cairo overrepresentation.
* **Executive Proposal:** Recommended against a uniform national remote-attendance policy, proposing instead targeted regional support and clear qualification thresholds.

---

## 🛠️ Tools & Tech Stack

| Tool | Purpose |
| :--- | :--- |
| **Python** | Primary analytics language |
| **Pandas & NumPy** | Data manipulation, string cleaning, missing value handling, summary statistics |
| **Matplotlib & Seaborn** | Visualization (Branch box plots, score vs. commute/study scatter plots) |
| **Excel (openpyxl)** | Multi-sheet statistical workbook and structured calculation outputs |

---

## 📁 Repository Structure

```text
├── data/
│   ├── raw_data.xlsx                  # Original raw survey data (271 rows)
│   └── ITI_Part_C_Calculations.xlsx   # Cleaned multi-sheet workbook & log
├── notebook/
│   └── data_cleaning_and_eda.ipynb    # Python notebook containing cleaning & analysis
├── visualizations/
│   ├── commute_boxplot_branches.png   # Regional commute distributions
│   ├── scatter_score_vs_commute.png   # Score vs. Commute scatter plot
│   └── scatter_score_vs_study.png     # Score vs. Study Hours scatter plot
└── README.md                          # Project documentation

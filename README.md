## 🏥 Medical Insurance Charges — Exploratory Data Analysis

A structured EDA project on a medical insurance dataset to uncover the key drivers of healthcare charges using Python.

---

### 📌 Project Overview

This project performs end-to-end Exploratory Data Analysis (EDA) on a medical insurance dataset containing approximately 1,500 records. The goal is to understand data quality, feature distributions, and the factors that most significantly influence insurance charges.

---

## 📂 Repository Structure

```
EDA-with-Python/
│
├── Medical_Cost.csv            # Raw dataset
├── MedicalCharges_EDA.ipynb    # Jupyter Notebook with full EDA
└── README.md                   # Project documentation
```

---

## 📊 Dataset Description

| Column | Type | Description |
|---|---|---|
| `age` | Numeric | Age of the primary beneficiary |
| `sex` | Categorical | Gender of the policyholder (male / female) |
| `bmi` | Numeric | Body Mass Index |
| `children` | Numeric | Number of dependents covered |
| `smoker` | Categorical | Whether the individual is a smoker (yes / no) |
| `region` | Categorical | US residential region (northeast, northwest, southeast, southwest) |
| `charges` | Numeric | Annual medical insurance charges (USD) — **target variable** |

**Source:** Medical Cost Personal Dataset (commonly available as a learning dataset for regression and EDA practice)

---

## 🔍 EDA Workflow

### 1. Data Loading & Inspection
- Loaded dataset using pandas
- Reviewed shape, data types, and statistical summary

### 2. Data Cleaning
- **Duplicates:** Identified and removed 1 duplicate row
- **Missing Values:**
  - `age` — 30 nulls → imputed with **mean** (distribution is symmetric, skew ≈ 0.05)
  - `children` — nulls → imputed with **median** (right-skewed, median = 0)
  - `bmi` — nulls → imputed with **median** (slightly right-skewed; robust to outliers)
- **Outliers:** BMI has high-end outliers detected via IQR method — retained as clinically valid values

### 3. Univariate Analysis
- Distribution and spread examined for: `age`, `bmi`, `children`, `charges`
- Charges are heavily right-skewed, indicating a high-cost minority

### 4. Bivariate Analysis
- **Numeric features vs Charges:** scatter plots for age, BMI, children
- **Categorical features vs Charges:** box plots for sex, smoker status, region

### 5. Multivariate Analysis
- BMI vs Charges coloured by smoker status — reveals the strongest interaction in the dataset

### 6. Correlation Analysis
- Heatmap of numeric feature correlations

---

## 💡 Key Insights

1. **Smoking is the single strongest cost driver** — smokers incur 3–4× higher charges than non-smokers
2. **Age has a consistent positive relationship** with charges — older individuals cost more
3. **BMI × Smoking interaction** creates the highest-cost cluster in the dataset (obese smokers)
4. **Gender and region are weak predictors** — charge distributions are similar across both
5. **Charges are right-skewed** — a log transformation would be advisable before predictive modelling
6. **Data quality resolved cleanly** — duplicates removed, nulls imputed based on distribution shape

---

## 🛠️ Tools & Libraries

| Tool | Purpose |
|---|---|
| Python 3 | Core language |
| pandas | Data loading, cleaning, manipulation |
| NumPy | Numeric operations |
| Matplotlib | Base plotting |
| Seaborn | Statistical visualisations |
| Jupyter Notebook | Interactive analysis environment |

---

## ▶️ How to Run

1. Clone this repository:
   ```bash
   git clone https://github.com/akellapadmaja/EDA-with-Python.git
   cd Medical-Insurance-EDA
   ```

2. Install dependencies (if not already available):
   ```bash
   pip install pandas numpy matplotlib seaborn jupyter
   ```

3. Launch the notebook:
   ```bash
   jupyter notebook MedicalCharges_EDA.ipynb
   ```

> Make sure `Medical_Cost.csv` is in the **same folder** as the notebook before running.

---

## 👩‍💻 Author

**Padmaja Akella**  
Banking Professional | Aspiring Data Analyst  
[GitHub](https://github.com/akellapadmaja) 

---

## 📁 Related Projects

- [Sales Insights Dashboard](https://github.com/akellapadmaja/Sales-Insights-Dashboard) — Power BI dashboard with star schema, DAX measures, and multi-page reporting

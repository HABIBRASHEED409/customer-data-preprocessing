# 📊 Customer Data Pre-processing — Assignment Portfolio

This repository contains the complete solution to the coursework assignment for the module **"771768 - Introduction to Programming for Artificial Intelligence and Data Science"**. The task was centered around **customer data wrangling and visualization**, where flat CSV records are cleaned, restructured, and analyzed for business intelligence.

---

## 📌 Project Summary

The assignment mimics real-world data engineering scenarios. I was provided with a **flat CSV** file containing mock customer data. The goal was to transform it into a richer **nested JSON structure**, clean invalid entries, generate specific filtered outputs, and compute useful metrics. Lastly, exploratory **data visualizations** were created to support further analysis.

---

## 📁 Repository Structure

customer-data-preprocessing/
├── data/
│ └── acw_user_data.csv 
│
├── figures/
│ ├── age_distribution.png
│ ├── commute_vs_salary.png
│ ├── age_vs_salary.png
│ ├── salary_vs_dependants.png
│ └── ... other seaborn plots
│
├── outputs/
│ ├── processed.json
│ ├── employed.json
│ ├── retired.json
│ ├── remove_ccard.json
│ └── commute.json 
│
├── Portfolio_Python_Assignment.ipynb # ✅ All tasks coded here
├── README.md # 📄 You are here
└── .gitignore


---

## 🧪 Features Implemented

### 💻 Data Preprocessing (Using Python Standard Libraries)

- **CSV Parsing** with Python's `csv` module
- **Nested Structure Conversion**:
  - `Vehicle`: make, model, year, type
  - `Credit Card`: start date, end date, number, security code, IBAN
  - `Address`: street, city, postcode
- **Handling Missing Data**:
  - Replaced empty `"dependants"` fields with `0`
  - Tracked problematic rows and printed:  
    `Problematic rows for dependants: [16, 58, 80, 98]`
- **Filtered Outputs**:
  - `retired.json` for retired individuals
  - `employed.json` for employed individuals
  - `remove_ccard.json` for credit cards older than 10 years (using MM/YY diff)
- **Metric Computation**:
  - `Salary-Commute` = Salary / Commute Distance  
    *(For distances ≤ 1km, commute = salary)*
  - Sorted records stored in `commute.json` (included in this repo ✅)

### 📊 Data Visualizations (With Pandas & Seaborn)

- **Univariate Analysis**:
  - Age histogram (bin width = 5)
  - Dependants count
  - Age distribution by Marital Status
- **Multivariate Analysis**:
  - Commute Distance vs Salary
  - Age vs Salary
  - Age vs Salary (conditioned by Number of Dependants)
- **Saved Figures**:
  - All figures saved in PNG format inside `figures/`

---

## 🧾 Sample Output — commute.json

Example structure from `commute.json`:

```json
{
  "first_name": "Graeme",
  "last_name": "Jackson",
  "salary": 17046,
  "commute_distance": 5.52,
  "Salary-Commute": 3088.04,
  "vehicle": {...},
  "credit_card": {...},
  "address": {...}
}

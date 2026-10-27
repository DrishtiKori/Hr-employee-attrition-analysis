# HR Employee Attrition Analysis

An end-to-end HR analytics project that cleans a 1,470-employee dataset, analyses who leaves and why using Excel PivotTables, and presents the findings in an interactive Tableau dashboard.

> **Headline:** 16.1% of employees (237 of 1,470) have left. Attrition is concentrated among **employees working overtime**, **new joiners (0–1 year)**, **18–24 year olds**, **low-income employees**, and **Sales Representatives**.

<img width="1920" height="1080" alt="Hr-attrition" src="https://github.com/user-attachments/assets/de2ac71a-e83a-46d7-8af5-706c0d2866e5" />


---

## Business Questions

1. How many employees do we have, and what share has left?
2. Which departments and job roles lose the most people?
3. Does overtime make employees more likely to leave?
4. Which age groups, tenure groups and income bands are most at risk?
5. Are job satisfaction, work-life balance and promotion delays linked to attrition?

---

## Key Findings

| Factor | Highest-risk group | Attrition rate | Comparison |
|---|---|---|---|
| Overall | All employees | **16.1%** | 237 of 1,470 left |
| Overtime | Works overtime | **30.5%** | 10.4% for no overtime (~2.9x) |
| Job role | Sales Representative | **39.8%** | Research Director: 2.5% |
| Department | Sales | **20.6%** | R&D: 13.8% |
| Age group | 18–24 | **39.2%** | 35–44: 10.1% |
| Tenure | 0–1 years | **34.9%** | 10–20 years: 10.0% |
| Income band | Low income (< 3,000/month) | **28.6%** | Very High income: 8.9% |
| Work-life balance | Rated "Bad" (1) | **31.3%** | Rated "Good" (3): 14.2% |
| Job satisfaction | Rated 1 (lowest) | **22.8%** | Rated 4 (highest): 11.3% |

Employees working overtime are 28% of the workforce but account for **54% of all leavers**. Employees in their first year are 15% of the workforce but **32% of leavers**.

Promotion delay showed **no clear link** to attrition in this data (17.0% for 0–1 years since promotion vs 12.5% for 10+ years).

Full analysis, recommendations and limitations are in [`HR_Attrition_Report.md`](HR_Attrition_Report.md).

---

## Tools & Skills Demonstrated

| Area | Tools / techniques |
|---|---|
| Data cleaning | Excel: removing invalid rows, standardising column names, dropping constant columns, data-quality checks |
| Feature engineering | Age, income, tenure, promotion-delay and work-life-balance bands; binary `Attrition_Flag` |
| Analysis | Excel PivotTables (10 business questions, PT01–PT10) |
| Visualisation | Tableau: KPI sheet, 5 attrition breakdown charts, interactive filter actions, calculated fields |

---

## Repository Structure

```
├── README.md
├── report/
│   └── HR_Attrition_Report.pdf 
├── data/
│   └── HR-Employee-Attrition_Data_analyst_Project.xlsx
├── dashboard/
    └── HR_Attrition_Analysis_Dashboard.twbx
```

**Workbook sheets**

| Sheet | Contents |
|---|---|
| `Raw_Data` | Original data (1,482 rows incl. invalid rows) |
| `Clean_Data` | Cleaned dataset (1,470 rows, 38 columns) with engineered features |
| `Data_Quality` | Missing-value check for every column |
| `Pivot_Tables` | PT01–PT10, each tied to a business question |

---

## Data Cleaning & Preparation

- Removed **12 invalid rows** from the raw data (6 fully blank rows and 6 rows containing only stray time values), leaving **1,470 employees**.
- Renamed columns to a consistent `Snake_Case` format.
- Dropped columns with a single constant value (`EmployeeCount`, `Over18`, `StandardHours`).
- Confirmed **0 missing values** and unique employee numbers in the clean dataset.
- Created analysis fields:
  - `Attrition_Flag` (1 = left, 0 = stayed)
  - `Age_Group`: 18–24, 25–34, 35–44, 45–54, 55–60
  - `Income_Band`: Low, Medium, High, Very High
  - `Tenure_Group`: 0–1, 2–4, 5–9, 10–20, 20+ years
  - `Promotion_Delay_Band`: 0–1, 2–4, 5–9, 10+ years
  - `Work_Life_Balance_Band`: Bad, Fair, Good, Excellent

---

## Dashboard

The Tableau workbook (`dashboard/HR_Attrition_Analysis_Dashboard.twbx`) contains:

- **KPIs**: headcount, active employees, leavers, attrition rate
- **Attrition by** Department, Job Role, Age Group, Tenure Group, Overtime Status
- Interactive filter actions (Age Group, Department, Income Band)

To open it, download the `.twbx` file and open it in [Tableau Public](https://public.tableau.com/) (free) or Tableau Desktop.

---

## Recommendations

1. **Review overtime workload**, especially in Sales Representative, Laboratory Technician and Research Scientist roles where overtime attrition is highest.
2. **Strengthen onboarding and first-year support**: one in three employees with under a year of tenure has left.
3. **Investigate the Sales Representative role** (pay, targets, workload): 4 in 10 have left.
4. **Review entry-level pay and early-career growth** for low-income and 18–24 employees.
5. **Monitor work-life balance and job satisfaction** scores as early-warning signals.

---

## Limitations

- The data is a single snapshot, so the attrition figures are the share of employees in the dataset who left, **not an annual rate**.
- Findings show **association, not causation**.
- Some groups are small (e.g. HR department n=63, Sales Representatives n=83, age 18–24 n=97, work-life balance "Bad" n=80), so their rates are less stable.

---

## Dataset

HR Employee Attrition dataset (1,470 employees, 35 original fields). Source: [](https://www.kaggle.com/datasets/pavansubhasht/ibm-hr-analytics-attrition-dataset)

---

## Author

**Drishti Kori**: Aspiring Data Analyst / Data Scientist, Mumbai

[GitHub](https://github.com/DrishtiKori) · [LinkedIn](https://linkedin.com/in/drishti-kori) · [Portfolio](https://drishtikori.github.io)

# codealpha_tasks_HF
# 🏥 Hospital Financial Health Dashboard – Power BI

This Power BI dashboard analyzes and visualizes the financial performance of a hospital using real transactional data. It provides decision-makers with critical KPIs such as revenue, expenses, profit margins, and regional performance.

---

## 📊 Dataset Overview

The dataset used is `HospitalFinance.xlsx`, which includes the following fields:

| Column Name         | Description                              |
|---------------------|------------------------------------------|
| Date                | Transaction date                         |
| Department          | Medical department (e.g., Urology)       |
| Region              | Hospital's geographic region             |
| PatientsBilled      | Number of patients billed                |
| Charges             | Total charges raised                     |
| OperatingCosts      | Operating expenses                       |
| InsuranceDiscount   | Discount due to insurance                |
| SupplyCost          | Cost of medical supplies                 |
| Tax                 | Tax paid                                 |
| NetProfit           | Final net profit                         |
| GrossProfit         | Gross profit before tax & discounts      |

---

## 📈 Dashboard Features

- **Executive Overview** with KPIs:
  - Total Revenue
  - Total Expenses
  - Net Income
  - Gross Profit Margin

- **Interactive Charts**:
  - Revenue by Department & Region
  - Monthly Revenue Trends (with Forecasting)
  - Net Income by Department

- **Filters/Slicers**:
  - Year
  - Region
  - Department

---

## 🧠 DAX Measures Used

```dax
-- Total Revenue
Total Revenue = SUM(HospitalFinance[Charges])

-- Total Expenses
Total Expenses = 
    SUM(HospitalFinance[OperatingCosts]) +
    SUM(HospitalFinance[SupplyCost]) +
    SUM(HospitalFinance[InsuranceDiscount]) +
    SUM(HospitalFinance[Tax])

-- Gross Profit
Gross Profit = SUM(HospitalFinance[GrossProfit])

-- Net Income
Net Income = SUM(HospitalFinance[NetProfit])

-- Gross Profit Margin
Gross Profit Margin = DIVIDE([Gross Profit], [Total Revenue], 0)

-- Net Profit Margin
Net Profit Margin = DIVIDE([Net Income], [Total Revenue], 0)

-- Year-To-Date Revenue
Revenue YTD = CALCULATE([Total Revenue], DATESYTD(DateTable[Date]))

-- Previous Year Revenue
Revenue PY = CALCULATE([Total Revenue], SAMEPERIODLASTYEAR(DateTable[Date]))

-- Year-over-Year Growth
Revenue Growth YoY = DIVIDE([Total Revenue] - [Revenue PY], [Revenue PY], 0)


▶️ How to Run
Clone the repository

bash
Copy
Edit
git clone https://github.com/yourusername/hospital-financial-dashboard.git
Open HospitalFinance.pbix in Power BI Desktop.

If needed, replace the sample dataset with your own HospitalFinance.xlsx.

Use the slicers and visuals to explore the dashboard.

-> Dashboard Preview

You can upload screenshots in an images/ folder and link them here.

-> Contact
If you have questions or suggestions:

📧 Email: kandibhanusree@gmail.com

💼 LinkedIn: (https://www.linkedin.com/in/kandi-bhanusree-b15b29160/)

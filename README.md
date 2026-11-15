# 📞 Telco Customer Churn Analysis (Excel)

> **1 in 4 customers left. Which customers are most at risk, and what can be done to keep them?**

An end-to-end Excel analysis of 7,043 telecom customers: data cleaning, pivot tables, slicers and an interactive dashboard that shows who churns, why they leave, and where retention efforts should focus.

![Dashboard](dashboard.png)

---

## 🎯 Business questions

1. How many customers leave, and how much revenue does it cost?
2. Which contracts, tenure groups, internet types, payment methods and offers have the highest churn?
3. Why do customers say they leave?
4. Where should the business focus its retention efforts?

## 📦 Dataset

| | |
|---|---|
| Source | IBM Telco Customer Churn sample dataset ([IBM Cognos Analytics, version 11.1.3](https://community.ibm.com/community/user/businessanalytics/blogs/steven-macko/2019/07/11/telco-customer-churn-1113)) |
| Size | 7,043 customers (one row per customer), 50 columns |
| Coverage | California, one quarter (Q3) |
| Outcome | `Churn Label`: 1,869 customers churned, 5,174 stayed |

> The raw dataset is not re-uploaded here. Please download it from the source above.

## 🧹 Data preparation

Every step is recorded in the **Cleaning Log** sheet of the workbook.

| Step | What I did | Result |
|---|---|---|
| 1 | Checked the original data | 7,043 customers, one row per customer |
| 2 | Filled blanks in `Offer` with "No Offer" | 3,877 blanks. A blank here is a real group: customers who were given no offer |
| 3 | Filled blanks in `Internet Type` with "No Internet" | 1,526 blanks. These customers have no internet service |
| 4 | Filled blanks in `Churn Category` and `Churn Reason` with "Not Churned" | 5,174 blanks. These are the customers who stayed |
| 5 | Checked for duplicates using `Customer ID` | 0 duplicates |

**Added columns:** `Churned` (1 if the customer left, otherwise 0) and `Tenure Band` (0-12, 13-24, 25-48, 49-72 months).
Because `Churned` is 1 or 0, the **average of `Churned` is the churn rate**, which keeps every pivot table simple and accurate.

## 📊 Headline numbers

| Customers | Churned | Churn rate | Monthly revenue lost | Share of monthly revenue lost |
|---|---|---|---|---|
| 7,043 | 1,869 | **26.5%** | $139,131 | **30.5%** |

## 🔑 Key findings

| # | Finding | Evidence |
|---|---|---|
| 1 | **Contract type is the strongest churn signal.** | Month-to-month 45.8%, one year 10.7%, two year **2.5%** |
| 2 | **The first year is the danger zone.** | 0-12 months **47.4%**, falling to 9.5% after four years |
| 3 | **Fiber Optic customers churn the most.** | Fiber Optic 40.7%, Cable 25.7%, DSL 18.6%, no internet 7.4% |
| 4 | **One offer stands out as a problem.** | Offer E loses **52.9%** of its customers; Offer A only 6.7% |
| 5 | **Payment method matters.** | Bank withdrawal 34.0% and mailed check 36.9%, versus credit card 14.5% |
| 6 | **The customers who leave pay more.** | Churned customers paid 30.5% of monthly revenue, although they are 26.5% of customers |
| 7 | **Competitors are the main reason.** | 45% of customers who left cited a competitor, mainly better devices and better offers |

## 💡 Recommendations

- **Move month-to-month customers onto longer contracts**, for example with a loyalty discount, since two-year customers almost never leave.
- **Focus retention on the first 12 months**: onboarding, a check-in after the first bills, and early offers.
- **Review Fiber Optic pricing and service quality**, because it is also the largest internet group (3,035 customers).
- **Review Offer E**, which loses more than half of its customers.
- **Counter competitor offers** with device upgrades and better data plans, the two most common reasons for leaving.

## ⚠️ Limitations

- This analysis shows **patterns, not proven causes**. For example, a high churn rate on Fiber Optic does not prove that Fiber Optic is the reason.
- The data covers **one quarter in California**, so results may differ elsewhere.
- The Top 10 reasons chart shows **10 of 20 reasons** (81% of customers who left).
- `Satisfaction Score` was **not used** as a driver: every customer scoring 1 or 2 had already churned, so the score was probably recorded after they left.
- The KPI tiles show **all customers** and do not change with the slicers. The charts do.

## 🛠️ What's inside the workbook

| Sheet | Purpose |
|---|---|
| `Dashboard` | Interactive dashboard: 4 slicers, 5 KPI tiles, 6 charts, key insights |
| `Calc` | Formulas that power the KPI tiles |
| `Cleaning Log` | Record of every cleaning step |
| `Data` | Cleaned dataset (Excel Table `tblChurn`) |
| `Pivot_Contract`, `Pivot_Tenure`, `Pivot_Internet`, `Pivot_Payment`, `Pivot_Offer`, `Pivot_Reason` | Pivot tables and charts behind the dashboard |

**Excel skills used:** Tables, PivotTables and PivotCharts, Slicers with Report Connections, IFS, SUMIFS, COUNTA, TEXT, shapes linked to cells, Go To Special, Remove Duplicates, dashboard design.

## ▶️ How to use

1. Download `Telco_Churn_Analysis.xlsx`
2. Open the `Dashboard` sheet
3. Click the **Contract**, **Internet Type**, **Payment Method** and **Offer** slicers to filter all six charts
4. Use the funnel icon with the **X** on a slicer to clear a filter

## 👩‍💻 Author

**Imanathul Reyyan**: BSc Applied Data Analytics, University of Colombo
🔗 [LinkedIn](https://www.linkedin.com/in/imanathul-reyyan) · 🌐 [Portfolio](https://imanathulreyyan.github.io) · ✉️ imanareyyan@gmail.com

*Project 2 in my data analytics portfolio (Excel, then SQL and Power BI).*

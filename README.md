<div align="center">

# Budget vs Actual Variance Analysis & Cost Control Dashboard

**Excel | Power Query | Pivot Tables | Slicers | Advanced Formulas**

Built an Excel dashboard that identifies overspending across departments and highlights where immediate cost control is required.

This is not a reporting tool — it is a decision tool.

It answers one question clearly: **Where is money being wasted, and what needs to be fixed?**

![Excel](https://img.shields.io/badge/Excel-Dashboard-217346?logo=microsoftexcel&logoColor=white)
![Power Query](https://img.shields.io/badge/Power%20Query-Data%20Transform-217346)
![Pivot Tables](https://img.shields.io/badge/Pivot%20Tables-Analysis-217346)
![Formulas](https://img.shields.io/badge/XLOOKUP%20|%20LET%20|%20FILTER-Advanced-217346)

</div>

---

## The Short Version

Total budget: **$45.32M**. Total actual spend: **$46.04M**. Total overspend: **$0.72M**.

The overall 1.58% variance looks small. But inside that number, Marketing alone is overspending by 15.69% — roughly **$1.08M above its allocation** — while IT is leaving 11.58% of its budget unspent. The money exists. It is just going to the wrong places.

This dashboard makes that visible in real time, with one-click filtering by department, region, and year.

---

## The Core Problem

Most companies track budget vs actual in Excel. But data sits in spreadsheets, nobody monitors it monthly, and overspending is noticed too late. By the time finance teams react, the damage is already done.

A $0.72M total variance sounds manageable. But it hides a $1.08M Marketing overspend being partially masked by IT's underspend. Without a clear view of where the variance is concentrated, both problems go unaddressed — Marketing keeps overspending and IT's unused budget sits idle instead of being reallocated.

---

## Full Dashboard View

![Dashboard Overview](images/dashboard_overview.png)

---

## Key Findings

### Marketing is the biggest overspender

15.69% over budget across 24 months — approximately **$1.08M above plan**. This is not a one-time spike. It is consistent every single month across the entire dataset.

![Department Variance](images/department_variance.png)

| Department | Variance % | Status |
|---|---|---|
| Marketing | +15.69% | 🔴 Overspend |
| Operations | +3.56% | 🟡 Watch |
| HR | +0.82% | 🟢 On Budget |
| Finance | +0.60% | 🟢 On Budget |
| IT | -11.58% | 🔴 Underspend |

---

### IT is consistently leaving money on the table

-11.58% under budget. Either IT is overplanning or delaying projects. Either way, that unspent budget could be reallocated to Marketing or Operations where the pressure is highest.

---

### Travel spikes every Q3 — without fail

July, August, and September show 30–40% overspend in Travel across all departments — not just one. At 9.40% over budget overall, Travel is the single most overspent cost category.

This is a seasonal pattern that should be planned for, not surprised by every year.

![Category Variance](images/category_variance.png)

| Category | Variance % |
|---|---|
| Travel | +9.40% |
| Training | +1.44% |
| Salaries | +1.01% |
| Supplies | +0.55% |
| Software | -0.34% |

---

### Q3 is where the budget breaks

The monthly trend shows spending tracking close to budget from January through June — then a sharp spike in July through September — then a return to normal in October.

This is not random variation. It is a structural pattern that repeats across both years in the dataset.

![Monthly Trend](images/monthly_trend.png)

---

### HR is the benchmark for good planning

0.82% variance. Almost exactly on budget every single month. Whatever HR is doing for planning and cost control is working — and it should be the reference model for other departments.

---

### Operations needs investigation

3.56% overspend overall, but the month-to-month numbers swing unpredictably. Some months under, some months well over. Unlike Marketing which is consistently over, Operations is volatile — which points to a different kind of problem.

---

## What Should Be Done

| Problem | Action | Expected Impact |
|---|---|---|
| Marketing overspending by ~$1.08M | Monthly spend review against budget with hard approval required above threshold | Catches overruns before month-end instead of after |
| IT leaving 11.58% unspent | Mid-year budget reallocation from IT to high-pressure departments | Puts idle budget to work where it is actually needed |
| Travel spiking every Q3 | Build Q3 travel spike into the annual budget as a planned line item | Eliminates surprise overspend — it is predictable, plan for it |
| Operations volatile month to month | Root cause investigation — identify which cost centers are driving the swings | Determines whether this is a planning problem or an execution problem |

---

## Variance Rules Used

| Status | Condition | Action |
|---|---|---|
| **Overspend** | Variance % > +5% | Investigate and control |
| **On Budget** | Between -5% and +5% | No action needed |
| **Underspend** | Variance % < -5% | Review allocation |

The 5% threshold matches how finance teams actually operate. Most companies flag spending issues at 5%, not 10%.

---

## What the Dashboard Contains

### KPI Cards
Five numbers at the top — Total Budget, Total Actual, Total Variance ($), Variance %, and Worst Department. Full picture in one glance.

### Department Variance Chart
Horizontal bar chart showing which departments are over and under budget. Colour coded — green for overspend, red for underspend.

### Monthly Variance Trend
Line chart showing how variance moves across all 12 months. The Q3 spike is immediately visible.

### Category Variance Chart
Bar chart breaking overspend by cost category. Travel stands out instantly.

### Interactive Slicers
Three slicers — Department, Region, Year — connected to all pivots and charts simultaneously. Click Marketing, everything filters. Click 2024, everything updates.

---

## Pivot Analysis

Three pivot tables power the analysis — each answering a different business question.

| Pivot | Question It Answers |
|---|---|
| Department Variance | Which departments are most over or under budget? |
| Category Variance | Which cost types are driving the overspend? |
| Monthly Variance by Year | When does overspending happen — is it seasonal? |

All three pivots connect to the same slicers so filtering one filters all.

![Pivot Analysis](images/pivot_analysis.png)

---

## Excel Skills Used

| Feature | Where It Is Used |
|---|---|
| **Power Query** | Loaded and transformed raw CSV — fixed data types, created Month_Year column |
| **Named Tables** | tbl_Budget, tbl_Department, tbl_Threshold — clean formula references |
| **Pivot Tables** | 3 pivots with calculated fields (Variance_Pct) |
| **Pivot Charts** | Charts built on pivot tables, fully connected to slicers |
| **Slicers** | 3 slicers connected to all pivots simultaneously |
| **SUMIFS** | KPI calculations, department and category totals |
| **XLOOKUP** | Cost centre lookups, department references |
| **LET** | Readable variance formulas |
| **FILTER / SORT / UNIQUE** | Dynamic Top 3 Worst Departments — auto-updates |
| **INDEX + SORT + SEQUENCE** | Top 3 ranking using dynamic arrays |
| **IF (nested)** | Status classification: Overspend / On Budget / Underspend |
| **Conditional Formatting** | Colour scales on variance, red for negatives |
| **Custom Number Formats** | Currency formatting, red negatives |
| **Data Validation** | Lookup tables for department-cost centre mapping |

---

## Workbook Structure

| Sheet | What Is Inside |
|---|---|
| **Raw Data** | 2,400 rows loaded via Power Query. Named table with Variance, Variance_%, and Status columns. |
| **Lookup Tables** | Department to Cost Centre mapping. Variance threshold definitions (±5%). |
| **Calculations** | All advanced formulas — KPIs, department summaries, Top 3 ranking, monthly trend, category breakdowns. |
| **Pivot Analysis** | 3 pivot tables with calculated fields, connected to slicers. |
| **Dashboard** | KPI cards, 3 pivot charts, 3 slicers. The main deliverable. |
| **Insights** | 5 decision-focused bullets — no explanations, just actions. |

---

## Dataset

Synthetic dataset built to simulate realistic budget behaviour over 24 months.

| Detail | Info |
|---|---|
| **Rows** | 2,400 |
| **Timeframe** | Jan 2023 – Dec 2024 |
| **Departments** | Marketing, IT, HR, Operations, Finance |
| **Categories** | Salaries, Software, Travel, Supplies, Training |
| **Regions** | North, South, East, West |
| **Total Budget** | $45.32M |
| **Total Actual** | $46.04M |

The data has realistic patterns built in — some departments consistently overspend, some underspend, Travel spikes every Q3, and Operations is volatile month to month.

---

## Project Structure

```
budget-variance-dashboard/
│
├── budget_variance_dashboard.xlsx  ← The deliverable (full dashboard)
├── budget_data.csv                 ← Synthetic dataset (2,400 rows)
├── README.md                       ← You are reading this
│
└── images/
    ├── dashboard_overview.png
    ├── department_variance.png
    ├── monthly_trend.png
    ├── category_variance.png
    └── pivot_analysis.png
```

---

## How to Use This Dashboard

1. Download the repo
   ```bash
   git clone https://github.com/analytics-ak/budget-variance-dashboard.git
   ```
2. Open `budget_variance_dashboard.xlsx` in Excel
3. If prompted, click **Enable Content** for data connections
4. Use the slicers on the Dashboard sheet to filter by Department, Region, or Year
5. All charts and pivots update together when you change a filter
6. Check the Insights sheet for key decisions

---

## Conclusion

The overall 1.58% variance looks fine on the surface. It is not.

Marketing is $1.08M over plan. IT has significant unspent budget sitting idle. Travel overspends every Q3 without fail. These are not surprises — they are predictable, recurring patterns that a monthly monitoring process would catch before they compound.

This dashboard makes those patterns visible at a glance, so decisions happen before the damage is done — not after.

---

## Author

**Ashish Kumar Dongre**

🔗 [LinkedIn](https://www.linkedin.com/in/analytics-ashish/) &nbsp;|&nbsp; 💻 [GitHub](https://github.com/analytics-ak/budget-variance-dashboard)

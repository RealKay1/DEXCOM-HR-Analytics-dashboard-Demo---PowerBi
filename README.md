# 👥 Dexcom HR Analytics Dashboard | Power BI

An interactive Power BI dashboard that gives HR and people leadership a single view of headcount, compensation, workforce demographics, and attrition - down to individual employee records - to support faster, evidence-based workforce decisions.

**Tools:** Power BI Desktop · Power Query · DAX · Data Modeling
**File:** `Dexcom_HR_dashboard.pbix`

> **Disclaimer:** This is a demo/practice project built for portfolio purposes using a publicly available HR analytics dataset, styled with Dexcom branding to demonstrate real-world dashboard design. It does not use or represent Dexcom's actual employee data.

---

## 📸 Dashboard Preview

**Overview Page** - headcount, salary, attrition KPIs, and workforce demographics

![Dexcom HR Analytics Dashboard - Overview](https://raw.githubusercontent.com/RealKay1/DEXCOM-HR-Analytics-dashboard-Demo---PowerBi/main/Capture1.JPG)

**Attrition Page** - termination trends and reasons behind employee turnover

![Dexcom HR Analytics Dashboard - Attrition](https://raw.githubusercontent.com/RealKay1/DEXCOM-HR-Analytics-dashboard-Demo---PowerBi/main/Capture2.JPG)

---

## 📌 Project Overview

HR teams are often asked to answer workforce questions - headcount, pay, diversity mix, and especially attrition - quickly and accurately, but the underlying data usually lives in disconnected HRIS exports and spreadsheets. This makes it hard to spot turnover trends early or explain *why* people are leaving in a way leadership can act on.

This dashboard consolidates employee records into one interactive Power BI report covering three areas: an organization-wide **Overview** of headcount, salary, and demographics; a dedicated **Attrition** page analyzing turnover trends and termination reasons; and an **Employee Details** page providing a searchable, filterable record-level table. A year filter and functional page navigation let users move between views and slice every page by time period.

The project demonstrates the core workflow of an HR/People Analyst or BI Analyst: data modeling, DAX measure development (including rate-based workforce metrics), and dashboard design that turns raw HR records into decisions leadership can act on.

## 🎯 Business Objectives

The dashboard was designed to answer the following workforce questions:

- What is our current total headcount, and how has it trended over time?
- What is our average salary, and how does it trend year over year?
- What is our attrition rate, and how has it evolved historically?
- How is our workforce distributed by sex, citizenship, marital status, department, race, and age band?
- How many employees are active versus terminated at any point in time?
- What are the top reasons employees leave the organization?
- Can HR quickly look up and filter individual employee records by year, department, or position?

## 🗂️ Dataset Overview

*Note: dataset details below are based only on the tables, fields, and values visible in the Power BI data model and report visuals.*

The model consists of:

| Table | Purpose | Key Fields Used in the Report |
|---|---|---|
| **HR_Dataset** | Employee-level record table | `EmpID`, `Employee_Name`, `DOB`, `DateofHire`, `DateofTermination`, `Department`, `Position`, `EmploymentStatus`, `Sex`, `Marital Status`, `Race`, `Citizenship`, `Employee Age Band` |
| **Date Table** | Calendar/time intelligence table | `Year`, `Month Name` |
| **Measures** | Dedicated measures table housing the report's DAX calculations | `Total Employees`, `Active Employees`, `Terminated Employees`, `Avg Salary`, `Attrition Rate` |

**Headcount composition (all-time, from the Overview page):** 311 total employees across 6 departments (Production, IT/IS, Sales, Software Engineering, Admin Offices, Executive Office), 6 race categories, and 5 employee age bands.

**Core measures (DAX):**

| Measure | What It Calculates |
|---|---|
| `Total Employees` | Count of all employee records in the filtered context |
| `Active Employees` | Count of employees with an active employment status |
| `Terminated Employees` | Count of employees who have left the organization |
| `Avg Salary` | Average salary across the filtered employee population |
| `Attrition Rate` | Turnover rate for the filtered period |

The report is filtered by a Year slicer on every page, plus Department and Position slicers on the Employee Details page, so all KPIs and visuals recalculate dynamically based on the selected filters.

## 📊 Dashboard Features

The report consists of three pages, connected by a functional in-report navigation menu (Overview, Attrition, Employee Details).

### Page 1 - Overview

| Visual | Type | What It Measures / Shows |
|---|---|---|
| Year slicer | Slicer | Filters the entire page by year |
| Total Employees | KPI card + sparkline | Total headcount, with a trend sparkline |
| Avg Salary | KPI card + sparkline | Average salary, with a trend sparkline |
| Attrition Rate | KPI card + sparkline | Attrition rate, with a trend sparkline |
| Total Employees by Sex | Donut chart | Gender split of the workforce |
| Total Employees by Citizenship | Donut chart | Breakdown by US Citizen, Eligible Non-Citizen, and Non-Citizen status |
| Total Employees by Marital Status | Donut chart | Breakdown by Single, Married, Divorced, Separated, and Widowed |
| Total Employees by Department | Bar chart | Headcount by department, showing where the workforce is concentrated |
| Total Employees by Race | Bar chart | Workforce breakdown by race/ethnicity |
| Total Employees by Employee Age Band | Bar chart | Workforce distribution across age bands |

### Page 2 - Attrition

| Visual | Type | What It Measures / Shows |
|---|---|---|
| Year slicer | Slicer | Filters the page by year |
| Terminated Employees | KPI card | Total count of employees who have left |
| Active Employees | KPI card | Total count of currently active employees |
| Attrition Rate | KPI card | Turnover rate for the selected period |
| Terminated Employees by Sex | Donut chart | Gender split among terminated employees |
| Attrition Rate by Year | Line chart | Historical attrition trend across years |
| Terminated Employees by Termination Reason | Bar chart | Ranks the reasons employees left (e.g., another position, unhappy, more money, career change, hours, attendance, relocation, return to school, military, no-call/no-show, performance) |

### Page 3 - Employee Details

| Visual | Type | What It Measures / Shows |
|---|---|---|
| Year / Department / Position slicers | Slicers | Filter the employee table by year, department, and position |
| Employee record table | Table | Row-level detail per employee, including EmpID, Employee Name, DOB, Date of Hire, Date of Termination, Department, Position, Employment Status, Marital Status, Race, Sex, Citizenship, Employee Age Band, and Avg Salary |

## 🔑 Key Performance Indicators (KPIs)

| KPI | Definition | Why It Matters |
|---|---|---|
| **Total Employees** | Count of employees in the filtered period | Baseline headcount metric for workforce planning |
| **Avg Salary** | Average salary across the filtered population | Tracks compensation trends and supports budget/pay-equity analysis |
| **Attrition Rate** | Turnover rate for the filtered period | A core HR health indicator; sustained high attrition signals retention risk and drives up hiring cost |
| **Active vs. Terminated Employees** | Split of current workforce vs. departed employees | Gives a clear, immediate picture of workforce stability |
| **Termination Reason** | Ranked reasons employees leave | Identifies whether attrition is driven by controllable factors (pay, culture, hours) or less controllable ones (relocation, school, military), directly informing retention strategy |

## 💡 Key Insights

*Analysis based strictly on the values visible in the dashboard for the selected reporting periods.*

- **Overall attrition is very high at 50.24%.** With 104 terminated employees against 207 active employees (311 total), roughly half of the historical workforce has turned over - a figure worth flagging to leadership as a retention priority. It's also worth noting the terminated-to-active ratio (104/207) matches the displayed rate almost exactly, so it may be worth double-checking whether the intended denominator is active headcount or total headcount, since each tells a different story to stakeholders.
- **Attrition has historically spiked in specific years.** The Attrition Rate by Year trend shows a sharp peak (well above 100%) around 2011, before declining and stabilizing at a lower level toward 2013-2014. A rate exceeding 100% in a single year suggests those early years had a very small employee base, where a handful of departures produced an outsized percentage - useful context before comparing early years directly to later, larger-headcount years.
- **Voluntary, controllable reasons dominate turnover.** The top termination reasons are "another position" (20) and "unhappy" (14), followed by "more money" (11) and "career change" (9) - together these controllable/competitive factors outweigh less controllable reasons like relocation, school, or military service. This points to a compensation and engagement review as a high-leverage retention lever.
- **Workforce is concentrated in Production.** 209 of 311 employees (about 67%) sit in the Production department, with IT/IS (50) a distant second. Any attrition or engagement issue in Production will have an outsized impact on total headcount stability.
- **Gender split is fairly balanced but skews male.** The overall workforce is 56.59% male / 43.41% female, and this skew is slightly more pronounced among terminated employees (57.69% male / 42.31% female) - close enough to the overall mix that gender does not appear to be a standout driver of attrition on its own.
- **The workforce is US-citizen dominant (94.86%)** and skews toward the 40-49 age band (129 employees, the largest single group), followed by 50-59 (78) - together these two bands represent about two-thirds of the workforce, which may be worth factoring into succession and retirement planning.
- **Marital status leans single/married.** Single (44.05%) and Married (39.87%) together account for the large majority of employees, with Divorced (9.65%), Separated (2.57%), and Widowed making up the remainder.

**Recommendation for leadership:** prioritize a compensation and engagement benchmarking exercise given that "another position" and "more money" are leading termination drivers, and investigate Production-specific retention programs given its outsized share of headcount.

## 🛠️ Tools & Technologies Used

- **Power BI Desktop** - report development and data visualization
- **Power Query** - data shaping and preparation
- **DAX (Data Analysis Expressions)** - custom measures (Total Employees, Active Employees, Terminated Employees, Avg Salary, Attrition Rate)
- **Data Modeling** - relationships between the HR_Dataset, a dedicated Date table, and a Measures table
- **Time Intelligence** - year-based filtering and trend analysis via a dedicated Date Table
- **Custom navigation & theming** - branded multi-page report with functional in-canvas page navigation

## 🧠 Skills Demonstrated

- Data modeling with a dedicated date/time intelligence table and a separate measures table (modeling best practice)
- DAX measure development for headcount, compensation, and rate-based (attrition) metrics
- Multi-page dashboard design with functional navigation, sparklines, and KPI cards
- Workforce/people analytics: demographics, compensation, and turnover analysis
- Record-level reporting design (searchable/filterable employee table) alongside summary-level dashboards
- Translating raw HR data into leadership-ready insights and retention recommendations
- Business storytelling - framing dashboard output as decisions, not just numbers

## ▶️ How to Use the Dashboard

1. **Navigate between pages:** use the left-hand menu (Overview, Attrition, Employee Details) to move between workforce summary, turnover analysis, and record-level detail.
2. **Set the time period:** use the Year slicer at the top of each page to filter KPIs and charts to a specific year, or leave on "All" for the full historical view.
3. **Review workforce composition:** on the Overview page, use the donut and bar charts to explore headcount by sex, citizenship, marital status, department, race, and age band.
4. **Investigate turnover:** on the Attrition page, review the Attrition Rate by Year trend and the Termination Reason bar chart to understand when and why employees are leaving.
5. **Look up individual employees:** on the Employee Details page, use the Year, Department, and Position slicers to narrow the table to a specific group, then scroll the table for employee-level detail.

## 📈 Project Outcomes

This dashboard replaces manual HR reporting with a single interactive source of truth for people analytics. It enables HR and leadership to:

- Monitor headcount, compensation, and attrition trends without waiting on manual reports
- Identify which departments and demographic groups carry the greatest retention risk
- Understand the actual drivers behind employee turnover to prioritize the right interventions
- Access individual employee records quickly for day-to-day HR operations
- Make faster, data-backed decisions on compensation strategy, retention programs, and workforce planning

## 🚀 Future Enhancements

- Add pay-equity analysis (average salary by department, race, and sex) to complement the existing demographic breakdowns
- Build a tenure/retention curve to show how long employees typically stay before leaving
- Add manager/supervisor-level rollups for department-level accountability
- Introduce predictive attrition scoring to flag at-risk employees before they leave
- Add row-level security so department heads only see their own team's data
- Automate data refresh via a scheduled gateway connection if/when connected to a live HRIS data source

---

*This project is part of a Business Intelligence / Data Analytics portfolio. Feedback and suggestions are welcome.*

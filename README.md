# 📊 Business Process Optimization & Efficiency Dashboard

> **An end-to-end data analytics project simulating how operations teams identify bottlenecks, reduce costs, and drive process excellence — built with Python, Excel, and Power BI.**

---

## 🎯 Project Objective

Design a comprehensive Business Process Optimization dashboard that enables management teams, business analysts, and process improvement professionals to:

- **Identify bottlenecks** in operational workflows
- **Benchmark performance** against SLA targets and standard cycle times
- **Quantify inefficiencies** through KPIs like Error Rate, Rework Rate, and Cycle Time Variance
- **Prioritize improvement initiatives** using data-backed evidence
- **Monitor cost efficiency** across departments and process types

---

## 🏢 Business Problem

Organizations operating across multiple departments — Finance, Operations, HR, IT, CX, Sales, Legal — frequently struggle to maintain visibility into their process health. Common pain points include:

- **Process delays** that inflate costs and miss delivery timelines
- **SLA violations** that damage client relationships and compliance scores
- **Undocumented rework** that consumes 15–30% of operational capacity unnoticed
- **Siloed reporting** that prevents cross-functional root cause analysis

This project addresses these challenges by centralizing process metrics in a single analytical framework.

---

## 📁 Dataset Description

**File:** `data/process_data.csv` | `data/BPO_Process_Dataset.xlsx`  
**Records:** 120 process-level observations across 15 unique processes and 7 departments  
**Period:** January 2024 – December 2024

| Column | Description |
|---|---|
| Process ID | Unique identifier (PRC-0001 to PRC-0120) |
| Process Name | E.g., Order Fulfillment, Invoice Processing |
| Department | Operations, Finance, HR, IT, CX, Sales, Legal |
| Process Owner | Responsible individual |
| Start Date / End Date | Process execution window |
| Cycle Time (Hours) | Actual time taken |
| Standard Cycle Time | Benchmark / expected time |
| Employee Assigned | Headcount for the process |
| Task Volume | Total tasks assigned |
| Tasks Completed | Tasks successfully finished |
| Productivity % | Completion rate |
| Error Count | Defects/mistakes found |
| Rework Count | Tasks requiring redo |
| Process Cost ($) | Operational cost |
| Customer Complaints | Complaints raised |
| SLA Target (%) | Agreed service level threshold |
| SLA Achieved (%) | Actual SLA performance |
| Process Status | Completed / In Progress / Delayed / On Hold |
| Improvement Opportunity | Recommended action |

**Derived Columns:**
- `Process Efficiency %` = (Standard Cycle Time / Actual Cycle Time) × 100
- `Error Rate %` = (Errors / Task Volume) × 100
- `Rework Rate %` = (Rework / Task Volume) × 100
- `Task Completion Rate %` = (Tasks Completed / Task Volume) × 100
- `Cost per Task ($)` = Process Cost / Task Volume
- `SLA Breach` = SLA Achieved < SLA Target (boolean)

---

## 📐 KPI Framework

| KPI | Formula | Benchmark |
|---|---|---|
| Process Efficiency % | (Std Time / Actual Time) × 100 | > 80% |
| Productivity % | (Tasks Completed / Task Volume) × 100 | > 85% |
| SLA Achievement Rate | Processes meeting SLA / Total Processes | > 90% |
| Avg Cycle Time | Mean of Cycle Time (Hours) | ≤ Standard |
| Error Rate % | (Errors / Volume) × 100 | < 5% |
| Rework Rate % | (Rework / Volume) × 100 | < 3% |
| Task Completion Rate % | (Completed / Volume) × 100 | > 90% |
| Cost per Task ($) | Total Cost / Total Volume | Minimize |

---

## 🔍 Analysis Performed

### 1. Process Efficiency Analysis
- Calculated efficiency % for each process run
- Identified processes with actual time > 1.5× standard (flagged as bottlenecks)
- Cycle time variance heatmap by department and process type

### 2. Bottleneck Identification
- Ranked top 20 processes by cycle time variance (actual minus standard)
- Cross-referenced with error rates to distinguish skill vs. process issues
- Improvement opportunity tagging for each flagged process

### 3. SLA Compliance Analysis
- Compared achieved vs. target SLA at process and department level
- Identified departments with highest breach rates
- Trend analysis across months to detect seasonal patterns

### 4. Cost Analysis
- Total and per-task cost by department and process
- Cost vs. efficiency scatter to identify high-spend / low-return processes
- Cost distribution (donut chart) for portfolio view

### 5. Error & Rework Analysis
- Grouped error and rework counts by department and process
- Flagged processes exceeding 5% error rate threshold
- Correlation analysis: error rate vs. SLA breach likelihood

### 6. Root Cause Categorization
- Improvement opportunities mapped to each process
- Frequency distribution of improvement types (RPA, SOPs, Automation, Training, etc.)

---

## 📊 Dashboard Features

### Excel Dashboard (`BPO_Process_Dataset.xlsx`)
| Sheet | Contents |
|---|---|
| Process Data | Full 120-row dataset with derived columns, color-coded status |
| KPI Summary | Executive-level KPI cards: Efficiency %, Productivity %, SLA Rate, Cost, Error Rate |
| Department Analysis | Dept KPI table + Bar charts (Efficiency and Cost) |
| Process Analysis | Process-level table with variance flagging + Actual vs Std Line Chart |
| SLA Dashboard | Full SLA breach table + Dept SLA summary |
| Cost Analysis | Cost ranking table + Pie chart by dept |
| Bottleneck Analysis | Top 20 bottleneck processes + Improvement opportunity chart |
| Error & Rework | Error/rework table + Clustered bar chart by dept |
| Recommendations | 8 data-backed improvement recommendations with priority and timeline |

### Power BI Template (`BPO_Efficiency_Dashboard.pbit`)
| Page | Visuals |
|---|---|
| 📊 Executive Summary | 6 KPI cards, Dept efficiency bar, Cost donut, SLA pie, Process status bar, Error trend, Cycle time comparison, Cost-efficiency scatter |
| 🏢 Department Analysis | Productivity bar, Cost bar, Error bar, KPI matrix table, SLA gauge, Cost treemap |
| 🚧 Bottleneck Analysis | Cycle time variance chart, Improvement opportunities bar, Error vs Cycle scatter, Top-20 bottleneck table |
| ✅ SLA & Compliance | SLA cards, Breach rate by dept, Achievement by process, SLA detail table, Monthly SLA trend line |
| 💰 Cost Analysis | Cost KPI cards, Cost waterfall by dept, Top-10 cost processes, Cost vs efficiency scatter, Full cost table |

---

## 💡 Key Insights

1. **Invoice Processing and Vendor Payment** show the highest cycle time variance (+4–6 hrs over standard), indicating Finance department is the primary bottleneck.
2. **SLA breach rate** is highest in the IT Support Ticket and Customer Complaint Handling processes — indicating resource constraints in high-volume intake processes.
3. **Operations department** accounts for the largest share of total process cost, driven by Order Fulfillment and Quality Inspection.
4. **Rework rates above 5%** were observed in 3 Finance processes — suggesting a need for upstream data quality controls.
5. **20+ processes** are tagged with automation-eligible improvement opportunities (RPA, workflow automation), representing significant labor savings potential.
6. **HR processes** exhibit lower error rates but higher cycle time variability — suggesting process design issues rather than skill gaps.

---

## 🛠️ Recommendations

| Priority | Finding | Action | Benefit |
|---|---|---|---|
| 🔴 HIGH | High error rate in Finance | Automated validation + poka-yoke | -30–40% errors |
| 🔴 HIGH | SLA breaches in IT/CX | Real-time SLA monitoring alerts | 90%+ SLA compliance |
| 🔴 HIGH | 20+ automation-eligible processes | RPA roadmap for top 5 processes | -30% labor cost |
| 🟡 MEDIUM | Low efficiency in Operations | Lean process redesign workshop | +15–20% efficiency |
| 🟡 MEDIUM | High cycle time variance | SOP standardization + training | -25% variance |
| 🟡 MEDIUM | High rework in Finance | Quality gates at checkpoints | -35% rework |
| 🟢 LOW | Productivity dips across HR | Capacity planning review | +10–15% productivity |

---

## 🚀 How to Use This Project

### Excel Dashboard
1. Open `data/BPO_Process_Dataset.xlsx`
2. Navigate using sheet tabs: start with **KPI Summary**, then drill into departmental sheets
3. Use Excel's built-in filter on the **Process Data** sheet to slice by Department, Status, or Process Name

### Power BI Dashboard
1. Install [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (free)
2. Open `BPO_Efficiency_Dashboard.pbit`
3. When prompted, point the data source to `data/process_data.csv`
4. Click **Refresh** — all 5 pages and 13 DAX measures will auto-populate
5. Use slicers to filter by Department, Date Range, Process Status, or Process Name

---

## 🗂️ Folder Structure

```
Business-Process-Optimization-Dashboard/
│
├── data/
│   ├── process_data.csv                  ← Raw dataset (120 rows)
│   └── BPO_Process_Dataset.xlsx          ← Excel multi-sheet dashboard
│
├── BPO_Efficiency_Dashboard.pbit         ← Power BI Template (5 pages, 13 measures)
│
├── reports/
│   └── BPO_Recommendations_Report.pdf   ← Business recommendations summary
│
├── screenshots/
│   ├── dashboard_overview.png
│   ├── kpi_summary.png
│   ├── bottleneck_analysis.png
│   └── sla_dashboard.png
│
├── build_dashboard.py                    ← Python script for Excel generation
├── build_pbit.py                         ← Python script for .pbit generation
└── README.md
```

---

## 🧰 Tech Stack

| Tool | Purpose |
|---|---|
| Python (pandas, openpyxl, numpy) | Data generation, Excel workbook construction |
| Microsoft Excel | Multi-sheet dashboard, charts, KPI cards |
| Power BI Desktop | Interactive 5-page BI dashboard |
| DAX (Power BI) | Custom measures and KPI calculations |
| Power Query (M Language) | Data transformation and Date dimension |
| GitHub | Version control and portfolio showcase |

---

## 📝 Resume-Ready Project Descriptions

**One-line:**  
Developed a Business Process Optimization dashboard in Excel and Power BI analyzing 120 process records across 7 departments, identifying bottlenecks, SLA breaches, and cost inefficiencies using DAX measures and KPI frameworks.

**Two-line (ATS-friendly):**  
Built an end-to-end Business Process Optimization & Efficiency Dashboard using Python, Excel, and Power BI to analyze 120 operational records across Finance, Operations, HR, IT, and CX departments. Delivered 5-page interactive Power BI report with 13 DAX measures tracking KPIs including Process Efficiency %, SLA Achievement Rate, Error Rate %, and Cost per Task — identifying 8 high-priority improvement opportunities with projected 20–30% cost reduction.

---

## 🎓 Interview Q&A Highlights

**Q: What KPIs did you measure?**  
A: Process Efficiency %, Productivity %, SLA Achievement Rate, Avg Cycle Time, Error Rate %, Rework Rate %, Task Completion Rate, Cost per Task, and Cycle Time Variance.

**Q: How did you identify bottlenecks?**  
A: By calculating cycle time variance (actual minus standard) and ranking processes by this metric. Cross-referenced with error rates and SLA breach data to distinguish capacity issues from quality issues.

**Q: What business value does this deliver?**  
A: The dashboard enables management to prioritize 8 improvement initiatives estimated to reduce process costs by 20–30%, improve SLA compliance to 90%+, and cut error rates by 30–40% through targeted interventions.

---

## 📬 Connect

*Project by Debarati | Business Analyst Portfolio*

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=flat&logo=linkedin)](https://linkedin.com)
[![GitHub](https://img.shields.io/badge/GitHub-Portfolio-181717?style=flat&logo=github)](https://github.com)

---

*Built for portfolio demonstration. Dataset is synthetically generated for analytical purposes.*

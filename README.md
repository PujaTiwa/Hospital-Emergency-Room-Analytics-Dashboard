# Hospital Emergency Room Analytics Dashboard

**An interactive, two-page Microsoft Excel dashboard for monitoring emergency room patient activity, operational performance, and year-over-year trends.**

Built with **Excel, Power Pivot, DAX, PivotTables, PivotCharts, and slicers**, the project turns patient-level records into a dashboard designed to help stakeholders explore admission patterns, waiting times, referral departments, and patient satisfaction.

## Dashboard previews

### 1. Patient Overview


[![Patient Overview](screenshots/Dashboard_1_Patient_Overview.png)](screenshots/Dashboard_1_Patient_Overview.png)

The **Patient Overview** page focuses on patient volume and demographics, along with core experience and attendance metrics:

- Total patients, average waiting time, and average patient experience score
- Delay rate and delayed versus on-time attendance
- Admitted versus not-admitted patients
- Patients by age group, gender, and referral department
- Monthly patient trend, with year-based filtering
- Interactive month and year slicers

### 2. Operations & Performance

![Operations and Performance dashboard](screenshots/operations_performance.png)

The **Operations & Performance** page explores patterns that may help guide staffing and service improvement:

- Patient arrivals by hour and dynamically calculated peak admission hour
- Average waiting time by referral department
- Average satisfaction score by referral department, **including rating counts (`n`)**
- Full-year comparisons between 2023 and 2024 for patient visits, waiting time, satisfaction, and admission rate
- Dynamic year-over-year KPI indicators
- Month slicer and navigation between dashboard pages

## Project objectives

1. Monitor emergency room patient demand across months and hours of the day.
2. Compare patient experience and waiting times across referral departments.
3. Understand patient demographics and admission outcomes.
4. Compare 2023 and 2024 performance using consistent KPIs.
5. Provide an accessible, interactive reporting experience within Excel.

## Key findings

The following **full-year** metrics come from the project's year-over-year comparison:

| Metric | 2023 | 2024 | Change |
|---|---:|---:|---:|
| Total patient visits | 4,338 | 4,878 | **+540 (+12.45%)** |
| Average waiting time | 35.03 min | 35.47 min | **+0.44 min** (approximately +1.24% based on underlying values) |
| Average satisfaction score | 5.03 | 4.96 | **Decrease** (approximately −1.25% based on underlying values) |
| Admission rate | 49.72% | 50.33% | **Approximately +0.60 percentage points** |

**Interpretation:** Patient visits increased in 2024, while average waiting time increased slightly and satisfaction declined slightly. These patterns are worth investigating; the dashboard does not establish a causal relationship.

> **Data context:** Monthly selections affect the relevant operational and patient-overview visuals. The year-over-year KPIs are labeled **Full-Year Comparison** and are not intended to represent the selected month. Displayed values may vary slightly from calculations using unrounded source measures.

## Tools and techniques

| Tool / skill | How it was used |
|---|---|
| Microsoft Excel | Workbook-based dashboard and formatting |
| Power Pivot / Data Model | Structured patient and calendar data |
| DAX measures | Dynamic totals, admission rate, delay rate, and related KPIs |
| PivotTables & PivotCharts | Grouped operational and demographic analyses |
| Slicers | Interactive month and year filtering |
| Excel formulas | Dynamic KPI text, peak-hour identification, and YoY calculations |
| Conditional formatting | Status indicators and data bars |
| Linked text boxes and shapes | KPI cards and dashboard navigation |

## Core metrics

- **Total Patients:** Count of recorded patient IDs.
- **Average Wait (Min):** Average of the patient waiting-time field.
- **Average Experience Score:** Average of available patient satisfaction scores.
- **Admission Rate:** Admitted patients ÷ total patients.
- **Delay Rate:** Patients marked `Delay` ÷ total patients.
- **Peak Admission Hour:** Hour(s) with the highest recorded arrival count under the selected filters.
- **Referral Department Analysis:** Counts and averages grouped by the recorded referral department; `None` represents no recorded department referral.
- **YoY Growth:** (2024 total − 2023 total) ÷ 2023 total.

**Satisfaction interpretation:** The satisfaction chart displays both the average score and the number of nonblank ratings, such as `5.14 (n=7)`. Results with very small samples should be interpreted cautiously; a high or low score from a few respondents may not represent the broader department experience.

## Repository structure

```text
Hospital-Emergency-Room-Analytics-Excel/
├── README.md
├── screenshots/
│   ├── patient_overview.png
│   └── operations_performance.png
└── Hospital_Emergency_Room_Dashboard.xlsx   # Add your completed workbook
```

## How to explore the dashboard

1. Download or clone this repository.
2. Open `Hospital_Emergency_Room_Dashboard.xlsx` in a desktop version of Microsoft Excel that supports the workbook's Data Model and Power Pivot features.
3. Open the **Patient Overview** dashboard and use the month/year slicers to explore patient metrics.
4. Navigate to **Operations & Performance** to review hourly admissions, departmental analysis, and the 2023–2024 comparison.
5. If needed, use **Data → Refresh All** to update connected PivotTables and measures.

> The Excel workbook is **not included in this README package**; add your completed `.xlsx` file to the repository before publishing the project. The dashboard images included here are supplied screenshots.

## Limitations and considerations

- Small departmental satisfaction samples can produce unstable averages.
- Referral department does not necessarily identify the department where a patient physically waited or received treatment.
- The dataset records attendance status and waiting times; operational conclusions depend on how these fields were defined.
- Historical trends are descriptive and do not, by themselves, explain why changes occurred.
- Review any patient-level workbook before publishing to ensure it contains no confidential or identifying patient information. If necessary, share only anonymized or aggregated data.

## Potential future improvements

- Target-versus-actual waiting-time KPIs
- Same-month year-over-year comparisons
- Additional data quality checks and a metric-definition sheet
- More detailed peak-hour staffing analysis, where staffing data is available

---

**Project category:** Healthcare Analytics · Excel Dashboard · Data Analysis · Business Intelligence

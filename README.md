# hospital-performance-dashboard

# Hospital Performance Dashboard (Power BI)

Power BI dashboard built to monitor hospital activity and operational performance.  
Focus: demand trends, throughput, and service KPIs using a clean star schema, Power Query transformations, and DAX measures.

## Dashboard Preview
![Overview](screenshots/01-overview.png)
![Trends](screenshots/02-trends.png)
![Breakdowns](screenshots/03-breakdowns.png)

## Problem
Hospital operational data is often fragmented and hard to interpret quickly.  
This dashboard turns raw activity data into actionable KPIs for leaders and operational teams.

## Key Questions Answered
- How is activity trending over time (daily/weekly/monthly)?
- Which days of the week drive demand peaks?
- Which departments / service lines contribute most to volume?
- Are there early signals of operational pressure (spikes, anomalies)?

## Data
Source: (replace with: synthetic dataset / open dataset / de-identified example)  
Grain: (e.g. encounter/day, presentation-level, activity-level)

## Model (Star Schema)
- Fact table(s): (e.g. FactActivity, FactAdmissions)
- Dimensions: Date, Department, Facility, PatientType (example)

See: `powerbi/model_diagram.png`

## Transformations (Power Query)
- Standardised dates and time buckets
- Cleaned categorical fields
- Created helper columns (e.g. DayOfWeekName, DayOfWeekNum)

## Measures (DAX)
Includes core measures like:
- Total Activity
- Rolling 7/28 day averages
- MoM / WoW change
- Contribution % by department

Full list: `docs/measures_dax.md`

## How to Reproduce
1. Review `docs/refresh_instructions.md`
2. Use SQL in `/sql` or sample data in `/data`
3. Rebuild visuals following screenshots

## Improvements / Next Iteration
- Add forecasting / anomaly detection
- Add drill-through pages
- Add data quality checks and refresh monitoring

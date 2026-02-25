# Hospital Capacity and Throughput Analytics Dashboard

## Project Overview

This project simulates a hospital performance monitoring system designed for executive and operational leadership.

The dashboard analyses:

- Inpatient admission volume  
- Bed occupancy against safety thresholds  
- Average Length of Stay (ALOS)  
- Ward-level throughput efficiency  
- Capacity risk stratification  

Built in Power BI using a structured star schema data model and DAX-based performance measures.

---

## Objective

To model hospital capacity utilisation and identify operational risk patterns using:

- Time-based admission trends  
- Occupancy threshold logic  
- Throughput performance indicators  
- Ward-level efficiency profiling  

This project demonstrates healthcare performance analytics modelling rather than generic business intelligence visualisation.

---

## Data Model (Star Schema)

The model follows a clean star schema architecture.

### Fact Table

**encounters**
- EncounterID  
- AdmissionDate  
- DischargeDate  
- BedID  
- LengthOfStayDays  
- Patient attributes  

### Dimension Tables

**calendar**
- Date  
- Year  
- MonthYear  
- DayOfWeekName  
- DayOfWeekNum (Monday-start)  
- IsWeekend  

**beds**
- BedID  
- Ward  

### Relationships

- encounters[AdmissionDate] → calendar[Date] (Active)  
- encounters[DischargeDate] → calendar[Date] (Inactive)  
- encounters[BedID] → beds[BedID]  

Single-direction filtering is maintained to preserve model integrity and avoid ambiguity.

![Data Model](images/data-model.png)

---

## Key Metrics and Logic

### Total Admissions

Count of inpatient encounters within the selected time context.

### Average Length of Stay (ALOS)

Average length of stay in days across encounters.

### Bed Occupancy %

Calculated as:

Total Patient Days ÷ (Total Beds × Days in Period)

Occupancy may exceed 100% to reflect surge capacity activation during peak demand.

### Capacity Risk Stratification

Threshold-based logic implemented in DAX:

- Greater than 95% → High Risk  
- Between 85% and 95% → Watch  
- Below 85% → Stable  

Risk scoring is visualised using conditional formatting and icon indicators.

---

## Dashboard Structure

### Executive Overview

Designed for hospital leadership.

Includes:

- Total Admissions (YTD)  
- Bed Occupancy percentage versus 85% safety threshold  
- Average Length of Stay  
- Monthly occupancy trend  
- Capacity risk classification  

Focus: Strategic capacity pressure monitoring and surge detection.

![Executive Overview](images/executive-overview.png)

---

### Operational Performance

Designed for operational managers.

Includes:

- Ward-level ALOS comparison  
- Ward occupancy profiling  
- Admissions by day of week  
- Interactive filtering by month and ward  

Focus: Throughput efficiency and demand pattern analysis.

![Operational Performance](images/operational-performance.png)

---

### Capacity Forecast and Risk

Designed for performance and planning teams.

Includes:

- Daily admissions trend  
- Admission growth percentage  
- Monthly capacity risk flags  
- Ward efficiency profile (ALOS vs Occupancy)  

Focus: Early detection of capacity strain and bottleneck identification.

![Capacity Forecast](images/capacity-forecast.png)

---

## Analytical Insights

- Occupancy exceeded 100% during winter months, indicating surge bed activation.  
- ICU demonstrates the highest ALOS (5.4 days), impacting turnover efficiency.  
- Mid-week admission peaks suggest elective scheduling concentration.  
- Sustained occupancy above 95% correlates with elevated throughput pressure.  

---

## Tools and Techniques

- Power BI  
- DAX (time intelligence, threshold logic, calculated measures)  
- Star schema modelling  
- Conditional formatting and KPI design  
- Interactive filtering and slicers  

---

## Professional Context

This project was developed to demonstrate healthcare performance analytics capability, with emphasis on:

- Operational metric modelling  
- Capacity planning logic  
- Health systems data storytelling  
- Executive-level dashboard communication

---

## Key Insights

- Occupancy exceeded 100% during winter months, indicating surge capacity activation.
- ICU demonstrates the highest Average Length of Stay (5.4 days), impacting bed turnover.
- Mid-week admissions peak (Wed–Thu), suggesting elective clustering.
- Several months classified as High Risk based on occupancy thresholds.

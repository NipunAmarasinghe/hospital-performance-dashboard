# Architecture

## Flow
Data Source (CSV/SQL)  
→ Power Query (cleaning + shaping)  
→ Star Schema (Fact + Dimensions)  
→ DAX Measures  
→ Report Pages (KPIs, Trends, Breakdowns)

## Notes
- Designed to keep measures in DAX (not calculated columns where avoidable)
- Date table drives time intelligence
- DayOfWeekNum used for correct sorting of DayOfWeekName

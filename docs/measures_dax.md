# DAX Measures

## Total Activity
```DAX
Total Activity = COUNTROWS(FactActivity)

Rolling 7D Activity =
CALCULATE(
    [Total Activity],
    DATESINPERIOD('Date'[Date], MAX('Date'[Date]), -7, DAY)
)


Even if your measures differ, the format is what matters.

---

## 8) Commit message rhythm (looks professional)
When you push changes, use commits like:
- `Add dashboard screenshots and README`
- `Document data model and DAX measures`
- `Add SQL extraction scripts`
- `Add refresh instructions and data dictionary`

Recruiters do look at this. Clean commits = you’re employable.

---

## 9) Quick “refresh instructions” (makes it real)
Create `docs/refresh_instructions.md`:

- Data source location (or sample file)
- Tables used
- Steps to refresh in Power BI Desktop
- Any parameters (date range, facility filter, etc.)

This is a small thing that makes your repo feel production-ready.

---

## 10) The finishing touch: Data Dictionary
Create `docs/data_dictionary.md`:
- Table name
- Column name
- Meaning
- Example values

This is how analysts communicate.

---

## If you tell me one thing, I’ll tailor it perfectly
You don’t need a back-and-forth, but if you drop **just the page names + the main KPIs** you used (even rough), I’ll generate:
- a tighter README (more “health exec” language),
- a polished architecture diagram description,
- a clean DAX documentation layout that matches your measures.

If you want my opinion: **this GitHub version of your hospital dashboard is more valuable for getting hired than building a second dashboard.** It’s proof you can deliver, explain, and hand over work like a real analyst.

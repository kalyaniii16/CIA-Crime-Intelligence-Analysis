# CIA — Crime Intelligence Analysis

An academic Data Warehousing & Data Mining project exploring historical district-level Indian IPC crime statistics.

## Dashboard sections
- **Overview:** dataset summary, India state heatmap, historical trend, leading crime categories, and regional comparisons.
- **Crime Analytics:** filter historical records by year, state/UT, district, and crime category; inspect trends and export category analysis.
- **District Records:** search district-year totals and export matching records to CSV.
- **Data Warehouse:** inspect SQLite warehouse tables and explore OLAP-style roll-up, slice, and drill-down operations.
- **Data Mining:** use K-Means to group district profiles with similar historical crime-category patterns; PCA visualizes the clusters in two dimensions.

## Interpretation note
This is an educational analysis of historical reported counts, not a live crime-monitoring system or an official law-enforcement tool. Counts are not population-adjusted crime rates, and cluster assignments describe statistical similarity only; they do not predict individual criminality or personal risk.

## Requirements
Python 3.10+ recommended.

```bash
python -m pip install streamlit pandas numpy plotly scikit-learn
```

## Run the dashboard
Open a terminal in the folder containing `app.py` and run:

```bash
python -m streamlit run app.py
```

Open the local URL printed by Streamlit (normally `http://localhost:8501`).

## Files
- `app.py` — Streamlit dashboard
- `dstrIPC_1.csv` — source dataset
- `cia_real_warehouse.db` — SQLite database used by the dashboard
- `etl.py` — extract, transform, load pipeline
- `warehouse.py` — database schema and connection helpers
- `cia_warehouse.db` — alternate/legacy database file

The dashboard reads `cia_real_warehouse.db`; keep it beside `app.py`.

## UI design notes
The interface uses a restrained dark navy, teal, and light-blue palette. Teal is the primary analytical accent, blue supports comparison series, and coral is reserved for limited emphasis. Chart hover labels, axis spacing, sidebar selection, keyboard focus, and reduced-motion preferences have been refined for clarity and accessibility.

The radar/briefing visuals are decorative design elements; the app analyzes stored historical records and does not provide live monitoring.

## Visualization styling
The dashboard uses a consistent dark-navy chart surface with teal primary series, ice-blue comparisons, restrained coral highlights, formatted hover values, and subtle gridlines. The chart redesign changes presentation only; it does not change the SQL queries, dataset, or analysis methods.

K-Means cluster-profile styling: the higher-profile chart uses a blue gradient and the lower-profile chart uses a muted red gradient, matching the preferred earlier design. Other chart styling follows the redesigned teal/ice-blue theme.

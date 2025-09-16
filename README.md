# Automated Data Collection: FixMyStreet & Police UK

This repository demonstrates an **automated data pipeline** built with [GitHub Actions](https://docs.github.com/en/actions).  
It periodically fetches local civic and crime data for Hainault, London, and stores it in version-controlled datasets.

---

## 📊 Data Sources
- **[FixMyStreet](https://www.fixmystreet.com/)**: Reports of street and environmental issues.
- **[UK Police Data API](https://data.police.uk/docs/)**: Open data on street-level crimes.

---

## ⚙️ How it works
- **GitHub Actions** run on a schedule:
  - `fetch-fixmystreet-rss.yml`: downloads the RSS feed every hour.
  - `fetch_police_crime_data.yml`: downloads the latest published monthly crime data.
- Fetched data is stored in the `data/` folder:
  - `fixmystreet.xml` → latest reports near Hainault.
  - `police-crime-YYYY-MM.json` → archived monthly crime datasets.

---

## 🚀 Features
- Automated hourly & monthly fetch jobs.
- Change detection: commits only when data has changed.
- Historical archive of JSON files for time-series analysis.
- Reproducible setup: workflows can be reused in other repos.

---

## 🏗️ Future Improvements
- Add ETL step: parse and transform raw XML/JSON into clean CSV/Parquet tables.
- Load into a database or warehouse (e.g., PostgreSQL, BigQuery).
- Build a dashboard (e.g., Streamlit, Power BI) for civic/crime trends.
- Add automated summaries (top crime categories, FixMyStreet report counts).

---

## 📂 Repo Structure

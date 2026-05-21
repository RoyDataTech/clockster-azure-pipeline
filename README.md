# Azure Clockster Pipeline

## 📖 Overview

This project demonstrates an end-to-end data analytics pipeline using Microsoft Azure services, with a local equivalent built in VS Code, PostgreSQL, and Power BI.  
It showcases my ability to design, automate, and visualize data workflows both in the cloud and locally.

---

## 🏗️ Architecture

**Azure Workflow:**

- Storage Account (ADLS Gen2) → Raw, Clean, Curated containers
- Data Factory → ingestion pipelines (CSV, APIs, databases, services)
- Databricks → transformation notebooks (PySpark/Python)
- Synapse Analytics → external tables, SQL queries
- Power BI → dashboards connected to Synapse

**Local Workflow:**

- Local folders → `/raw`, `/clean`, `/curated`
- Python scripts → ingestion (CSV, APIs, DBs) + transformation (Pandas/Polars)
- PostgreSQL → data warehouse tables
- Task Scheduler → automation
- Power BI → dashboards connected to PostgreSQL

---

## ⚙️ Azure Workflow Steps

1. **Storage Account**
   - Containers: raw, clean, curated
   - Raw data uploaded to `raw`

2. **Data Factory**
   - Linked services: LS_ADLS_raw, LS_ADLS_clean, LS_ADLS_curated
   - Datasets: raw CSV, clean CSV
   - Pipelines: Copy Data (raw → clean)
   - Debug, publish, trigger

3. **Databricks**
   - Create cluster
   - Notebook with PySpark/Python
   - Transform data → save to curated container

4. **Synapse Analytics**
   - Link ADLS Gen2
   - Create external tables from curated data
   - Run SQL queries

5. **Power BI**
   - Connect to Synapse
   - Build dashboards

---

## 💻 Local Workflow Steps

1. **Storage Layer**
   - Folders: `/raw`, `/clean`, `/curated`

2. **Python Scripts**
   - Ingestion: CSV, API (requests), DB (psycopg2/sqlalchemy)
   - Transformation: Pandas/Polars
   - Save curated outputs

3. **PostgreSQL**
   - Load curated data via `COPY` or `pandas.to_sql`
   - Tables mirror curated datasets

4. **Automation**
   - Windows Task Scheduler runs `pipeline.py` daily

5. **Power BI**
   - Connect to PostgreSQL
   - Build dashboards
   - Scheduled refresh in Power BI Service

---

## 🔄 Azure vs Local Comparison

| Stage            | Azure Workflow                                   | Local Workflow                                   |
|------------------|--------------------------------------------------|--------------------------------------------------|
| Storage Layer    | ADLS Gen2 containers                             | Local folders                                    |
| Ingestion        | Data Factory pipelines                           | Python scripts + Task Scheduler                  |
| Transformation   | Databricks notebooks                             | Pandas/Polars scripts                            |
| Data Warehouse   | Synapse Analytics external tables                | PostgreSQL tables                                |
| Automation       | ADF triggers + CI/CD                             | Task Scheduler / cron jobs                       |
| Visualization    | Power BI connected to Synapse                    | Power BI connected to PostgreSQL                 |

---

## 📂 Repository Contents

- `raw_data/` → sample CSVs
- `scripts/` → Python ingestion/transformation scripts
- `docs/` → architecture diagram, walkthrough notes, screenshots
- `notebooks/` → exported Databricks notebooks (optional)
- `clockster.pbix` → Power BI report file (optional)
- `requirements.txt` → Python dependencies
- `.gitignore` → excludes venv, cache, temp files
- `README.md` → this documentation

---

## 🎯 Key Skills Demonstrated

- Azure Storage, Data Factory, Databricks, Synapse Analytics
- Local equivalents with VS Code, Python, PostgreSQL
- Automation with ADF triggers and Task Scheduler
- End-to-end data pipeline design
- Power BI dashboarding
- GitHub version control and portfolio presentation

---

## 📹 Walkthrough Video

A full narrated video walkthrough is available, showcasing both the Azure pipeline and the local equivalent.

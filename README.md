# Azure Lakehouse Project

**Owner:** Ruth Kumar (ruthkmr27)
**Project:** Azure Lakehouse — end-to-end example using Azure Synapse (Lakehouse pattern)
**Status:** In progress — Day 1–5 notebooks added.

---

## Project Summary
This repository demonstrates a small Azure Lakehouse pipeline implemented on Azure Synapse Analytics.
It contains sample notebooks used to ingest raw CSV data (Bronze), perform cleaning/transformations (Silver), and produce curated outputs (Gold) and a simple dimensional model. The notebooks are designed for learning and to showcase cloud-data engineering skills.

---

## Repository structure

/

├─ notebooks/                 # Synapse notebooks (PySpark .ipynb)

│  ├─ NB_BronzeToSilver.ipynb

│  ├─ NB_SilverToGold.ipynb

│  └─ NB_Gold_DimModel.ipynb

├─ architecture/              # Architecture diagrams and images

│  └─ diagram.png

├─ screenshots/               # Optional screenshots from Synapse UI

├─ README.md                  # This file

├─ LICENSE                    # MIT license

└─ .gitignore


---

## What’s included
- Notebooks that show:
- **Bronze**: ingest CSVs into the lake (raw).
- **Silver**: cleaning, dedupe, rename columns, basic transformations.
- **Gold**: write curated datasets (Delta / Parquet) and build a small dimensional model.
- Architecture diagram illustrating the Synapse workspace, ADLS Gen2, Spark pools, and data flow.
- Basic instructions to run the notebooks in an Azure Synapse environment.

---

## Prerequisites
- Azure subscription (free trial or paid) with enough quota to create a Synapse workspace and Spark pool.
- ADLS Gen2 storage account accessible by your Synapse workspace.
- A Synapse workspace with a Spark pool configured (or permissions to create one).
- Python / PySpark knowledge for running notebooks.

**Note:** Free-tier or trial subscriptions can still incur charges when compute (Spark pools, SQL pools) runs. Always stop or delete compute resources when not in use (see **Cost & Cleanup** below).

---

## How to run (high level)
1. Create an Azure Resource Group and an ADLS Gen2 storage account.
2. Create an Azure Synapse workspace and attach the storage account.
3. Create a Spark pool or ensure one exists.
4. Upload the sample CSV to the `bronze/` path in the ADLS container (or update `bronze_path` variable in the notebooks).
5. Open Synapse Studio → Develop → Notebooks. Upload or create the notebooks, attach them to the Spark pool, and run cells in order:
- `NB_BronzeToSilver.ipynb` (ingest raw CSV → silver)
- `NB_SilverToGold.ipynb` (transform silver → gold)
- `NB_Gold_DimModel.ipynb` (build dimension model)
6. Verify outputs in the lakehouse container (silver/ and gold/ paths).

---

## Notebooks summary
- **NB_BronzeToSilver.ipynb** — reads CSV from `abfss://.../bronze/`, does cleaning, renames columns, writes Delta/Parquet to silver.
- **NB_SilverToGold.ipynb** — aggregates/cleans silver data and writes final gold tables.
- **NB_Gold_DimModel.ipynb** — illustrative dimensional model SQL queries and example reads.

Each notebook contains the paths as variables at the top. Update `bronze_path`, `silver_path`, `gold_path` to match your ADLS container.

---

## Cost control & cleanup (important)
To avoid unexpected charges:
1. **Stop or delete Spark pools** when not in use:
- Synapse Studio → Manage → Apache Spark pools → select pool → Delete.
2. **Pause or delete dedicated SQL pools** (if created).
3. **Delete the Synapse workspace** if you’re finished.
4. **Delete the resource group** to remove all resources in one go (effective but irreversible).
5. Set resource tags and budgets in Azure Cost Management and create cost alerts.

I recommend deleting compute (Spark pools and SQL pools) at the end of every day if you are on a trial subscription.

---

## Files to add (recommended)
- `architecture/diagram.png` — diagram of the lakehouse.
- `notebooks/` — notebook files (already present).
- `screenshots/` — example Synapse screens (small & compressed).
- `.gitignore` — ignore unnecessary files (`.ipynb_checkpoints`, `__pycache__`, etc).
- `CLEANUP.md` (optional) — step-by-step cleanup commands.

---

## License
This repository is licensed under the MIT License — see `LICENSE` for details.

---

## Contact
Author: Ruth Kumar — `annie.data.engineer@outlook.com` (repo owner)
If you want: add LinkedIn/github/email contact information here.

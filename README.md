# 🎧 Music Listener Behavior Analytics using Orange Preprocessing, OLAP, and Data Mining

## 📘 Overview

This project proposes a hybrid analytical pipeline that integrates **data preprocessing with Orange**, **OLAP-based schema modeling using SQL Server**, and **data mining** for in-depth behavioral analysis of music listeners. The objective is to classify listener types, understand genre/language preferences, and discover usage patterns using a combination of **multidimensional analysis** and **machine learning models**.

The workflow begins with preprocessing the raw dataset in **Orange**, followed by **data warehouse cube construction** using **SQL Server Management Studio (SSMS)** and **SQL Server Analysis Services (SSAS)**. The mining models are built using **Orange workflows** with the preprocessed data.

All data is synthetically generated and fully anonymized to comply with ethical research practices.

This repository supports full **reproducibility** of our experiments and findings as presented in the research paper, and is meant for academic, learning, and experimentation purposes.

---

## 🛠 Project Workflow Summary

1. **Preprocessing** – Orange (missing value handling, encoding, normalization)
2. **Data Warehouse Modeling** – Star/Snowflake schema using SSMS
3. **Cube Construction** – SSAS (OLAP cube creation and processing)
4. **OLAP Analysis** – MDX queries for Slice, Dice, Drill-down, Roll-up
5. **Data Mining** – Orange workflows for listener type classification and feature selection

---


---

## 💾 Requirements

| Tool                  | Version | Notes                                 |
|-----------------------|---------|----------------------------------------|
| Orange Data Mining    | 3.35+   | For preprocessing and ML workflows     |
| SQL Server Management Studio (SSMS) | 18+     | For schema creation and data insertion |
| SQL Server Analysis Services (SSAS) | 2019+   | For OLAP cube design and processing     |
| Visual Studio (SSDT)  | 2019+   | For SSAS integration with cubes        |

---

## ⚙️ Setup and Execution Instructions

### 🟠 1. Preprocessing with Orange

1. Open **Orange**.
2. Load the file `preprocessing_orange/preprocessing_workflow.ows`.
3. Import the `synthetic_listener_data.csv`.
4. Perform:
   - **Missing value imputation** (5% numerical, 2% text)
   - **Discretization or normalization** (if needed)
   - **Categorical encoding**
5. Export the cleaned dataset to `.tab` or `.csv` format (already included: `preprocessed_data.tab`).

### 🛢 2. Schema and Data Warehouse Setup

1. Open **SQL Server Management Studio (SSMS)**.
2. Create a new database (e.g., `MusicDW`).
3. Run `create_star_schema.sql` to create tables.
4. Use the preprocessed `.tab` file to prepare insert statements or use `insert_dimension_tables.sql`.

### 🧊 3. OLAP Cube Construction (SSAS)

1. Open **Visual Studio** and create a **Multidimensional SSAS Project**.
2. Use `MusicDW` as your data source.
3. Define **dimensions** and **measures** based on your schema.
4. Deploy and process the cube.
5. Run MDX queries in the cube browser using scripts from `mdx_queries.md`.

### 🤖 4. Data Mining (Orange)

1. Load `listener_prediction.ows` in Orange.
2. Use `preprocessed_data.tab` as input.
3. Apply classifiers: **kNN**, **Naïve Bayes**, **Random Forest**, etc.
4. Use `feature_selection.ows` to visualize attribute importance.

---

## ✅ Reproducibility

To reproduce the results:
1. Use Orange to preprocess the dataset.
2. Load the cleaned data into SQL Server for schema and cube setup.
3. Use SSAS to run OLAP operations and visualize results.
4. Run Orange workflows for mining listener types and key attributes.

---

## 🛡️ Ethical Considerations

- **Data Collection**: The dataset used in this project is based on real-world data collected as part of a listener behavior study. Data collection was carried out responsibly, with appropriate care for participant privacy.
- **Informed Consent & Privacy**: Any personal identifiers (names, emails, DOB) were anonymized or obfuscated before analysis. No sensitive information is disclosed in this repository.
- **Anonymization**: All personally identifiable information (PII) has been removed or anonymized before preprocessing and storage.
- **Reproducibility**: The complete dataset, preprocessing workflow, OLAP schema, and mining pipelines are included in the GitHub repository for academic reproducibility.
- **Fair Use**: This project and dataset are intended strictly for academic and educational use under ethical research practices.

---

## 📬 Contact

For queries, please send an email to `keerthi.guttikonda@gmail.com`.

---







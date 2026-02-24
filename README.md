# 🎬 Netflix Shows Data Engineering Project (Python → SQL Server)

## 📌 Overview

This project implements an **end-to-end data engineering pipeline** using the Netflix Shows dataset.
The workflow covers **data ingestion, schema validation, SQL-based cleaning, and exploratory data analysis (EDA)**.

The dataset is sourced from Kaggle and stored in **Microsoft SQL Server** for structured analysis and future analytics use cases.

---

## 🧱 Architecture

```
CSV (Netflix Dataset)
        ↓
Python (Pandas)
        ↓
SQLAlchemy + ODBC
        ↓
SQL Server (netflix_raw)
        ↓
Cleaned Tables / Views
        ↓
SQL EDA & Analytics
```

---

## 📂 Repository Structure

```
Netflix_EDA_Analysis
│
├── notebooks/
│   └── data.ipynb
│
├── sql/
│   ├── Create Table.sql
│   └── Cleaning EDA.sql
│
├── data/
│   └── netflix_titles.csv
│
├── docs/
│   └── schema_diagram.png   (optional)
│
└── README.md

```

---

## 📊 Dataset Description

The dataset contains metadata for Netflix movies and TV shows.

**Key Columns**

* `show_id` – Unique content identifier
* `type` – Movie or TV Show
* `title` – Content title
* `director` – Director name(s)
* `cast` – Main cast
* `country` – Country of production
* `date_added` – Date added to Netflix
* `release_year` – Year of release
* `rating` – Content rating
* `duration` – Runtime or number of seasons
* `listed_in` – Genres
* `description` – Content summary

---

## 🔄 Data Pipeline Workflow

### 1️⃣ Data Ingestion (Python)

* Loaded CSV data using Pandas
* Validated maximum text lengths to prevent SQL truncation
* Ensured Unicode compatibility for international titles
* Inserted data into SQL Server using SQLAlchemy

Target table: **`netflix_raw`**

---

### 2️⃣ Table Creation (`Create Table.sql`)

* Explicit schema definition using NVARCHAR
* Unicode-safe columns for global content
* Raw layer preserved for data lineage and auditing

---

### 3️⃣ Data Cleaning & EDA (`Cleaning EDA.sql`)

* Handled missing values (director, cast, country)
* Standardized ratings, content types, and country names
* Converted date fields to proper formats
* Identified duplicates
* Performed exploratory SQL queries

---

### 4️⃣ Exploratory Analysis (SQL)

Key insights explored:

* Movies vs TV Shows distribution
* Content growth by release year
* Country-wise production trends
* Rating distribution
* Genre frequency analysis

---

## 🧩 Database Schema

### Raw Table: `netflix_raw`

```
show_id        NVARCHAR(10)
type           NVARCHAR(20)
title          NVARCHAR(200)
director       NVARCHAR(250)
cast           NVARCHAR(1000)
country        NVARCHAR(150)
date_added     NVARCHAR(50)
release_year   INT
rating         NVARCHAR(20)
duration       NVARCHAR(50)
listed_in      NVARCHAR(250)
description    NVARCHAR(MAX)
```

---

## 🛠 Tech Stack

* **Python** (Pandas, SQLAlchemy)
* **Microsoft SQL Server**
* **ODBC Driver 17**
* **Jupyter Notebook**

---

## 📈 Business Value

* Reliable ingestion of text-heavy datasets
* SQL-optimized structure for analytics
* Clean data ready for dashboards or ML models
* Scalable foundation for BI and reporting

---

## 🚀 Future Enhancements

* Create cleaned & normalized tables
* Build SQL views and stored procedures
* Develop Power BI / Tableau dashboards
* Integrate machine learning workflows

---

## 📜 License

Dataset is publicly available on Kaggle and used for educational and analytical purposes.

---

## 🙌 Credits

* Netflix Shows Dataset – Kaggle
* Python → SQL Server data pipeline implementation

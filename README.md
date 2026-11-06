# E-Commerce Automated Data Engineering ETL Pipeline

An end-to-end Data Engineering ETL pipeline designed to ingest raw e-commerce transaction data, perform rigorous data cleaning, validation, and outlier handling using Python & Pandas, and load the processed dataset into a Microsoft SQL Server database.

## 📌 Project Overview
- Extract: Ingests raw multi-year transaction logs from CSV.
- Transform: 
  - Standardizes column naming conventions to snake_case.
  - Enforces explicit Datetime conversion and filters invalid future dates.
  - Normalizes text attributes and removes duplicates by order_id.
  - Implements Interquartile Range (IQR) capping on Sales and Profit to handle extreme outliers safely.
  - Enforces programmatic data quality checks using explicit Python assert statements.
- Load: Bulk loads the cleaned, production-ready dataset into SQL Server with strict constraint validation.

## 🛠 Tech Stack
- Language: Python 3.x
- Data Manipulation: Pandas, NumPy
- Database & Querying: Microsoft SQL Server (T-SQL), SSMS

## 📂 Repository Structure
```text
ecommerce-etl-pipeline/
│
├── data/
│   ├── raw/                  # Contains raw, uncleaned e-commerce dataset
│   └── processed/            # Contains cleaned & transformed dataset ready for loading
│
├── sql/
│   └── schema_and_load.sql   # Database creation, staging table schema, and BULK INSERT script
│
├── etl_pipeline.py           # Main Python ETL script for cleaning and transformation
└── README.md                 # Project documentation
```
## 🚀 How to Run
1. Clone the repository:
   git clone https://github.com/Hager-Abdelnasser/Ecommerce-Sales-ETL-Pipeline
   cd Ecommerce-Sales-ETL-Pipeline
2. Install dependencies:
   pip install pandas numpy

3. Run the ETL pipeline script to process the raw data:
   python etl_pipeline.py

4. Execute the SQL script sql/schema_and_load.sql in SQL Server Management Studio (SSMS) to create the staging table and bulk insert the processed data.

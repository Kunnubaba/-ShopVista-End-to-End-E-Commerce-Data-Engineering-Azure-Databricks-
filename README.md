# -ShopVista-End-to-End-E-Commerce-Data-Engineering-Azure-Databricks-

📌 Project Overview
ShopVista is a rapidly growing e-commerce platform that faced major challenges due to data being scattered across multiple source systems and flat files. Business teams relied on manual data consolidation and static reports, resulting in delayed insights and limited visibility into sales, customers, and operations.

This project delivers a centralized, scalable, and fully automated data platform on Microsoft Azure, transforming raw operational data into analytics-ready datasets using Azure Databricks, Azure Data Lake Storage Gen2, Unity Catalog and the Medallion (Bronze → Silver → Gold) architecture. The final data model powers an interactive Power BI analytics dashboard for business decision-making.

🎯 Business Challenges
Fragmented data across multiple raw files and systems
Manual reconciliation and inconsistent reporting
No single source of truth for analytics
Slow reporting cycles and limited analytical flexibility
🛠️ Solution Approach
A centralized Azure-based data platform was designed to ingest, process, and serve data in a fully automated manner:

Azure Data Lake Storage Gen2 (ADLS) as the centralized data lake
Azure Databricks and Unity Catalog for scalable ETL/ELT processing
Delta Lake tables for reliability, performance and schema enforcement
Medallion Architecture (Bronze, Silver, Gold) for progressive data refinement
Automated Databricks Jobs for daily and monthly orchestration
Power BI for interactive analytics and reporting
🧱 Pipeline Architecture (Azure)
Pipeline Architecture

Architecture Highlights:

Source CSV files land in ADLS (Raw zone)
Databricks ingests raw data into Bronze tables
Data is cleaned, standardized and validated in Silver tables
Business-ready fact and dimension tables are created in Gold
Power BI consumes Gold tables for analytics and dashboards
📂 Azure Data Lake – Raw Zone
Raw datasets stored in ADLS include:

ADLS Raw Data

This structure enables centralized storage and traceability of source data.

🥉🥈🥇 Medallion Architecture – Data Layers
Schema Layers

🥉 Bronze Layer
Raw ingestion from ADLS
Minimal transformation
Schema enforcement
Historical and audit-friendly storage
🥈 Silver Layer
Data cleansing and standardization
Handling nulls, duplicates and invalid records
Referential integrity enforcement
Business-consistent datasets
🥇 Gold Layer
Star schema modeling
Optimized for analytics and BI consumption
Aggregated and enriched datasets
⚙️ Job Orchestration & Automation
🔁 Daily Refresh Pipeline
Daily Refresh Job

A fully automated daily Databricks job was created to process:
Dimension tables (Customers, Products, Categories, Brands, Date)
Fact Order Items
Ensures fresh, analytics-ready data every day
Dependencies enforced between dimension and fact processing, guaranteeing data consistency
📅 Monthly Processing Pipeline
Monthly Job

A separate monthly job processes:
Fact Order Returns
Fact Order Shipments
This design optimizes compute usage while supporting accurate historical trend analysis.

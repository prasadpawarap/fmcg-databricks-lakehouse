# fmcg-databricks-lakehouse
FMCG Data Lakehouse: M&A Integration Pipeline
Built with Databricks, PySpark, AWS S3, and Power BI

📌 Project Overview
This project simulates a high-stakes Data Engineering scenario following a corporate Merger and Acquisition (M&A). As the lead Data Engineer, I built an end-to-end Data Lakehouse to integrate daily sales and supply chain data from a newly acquired subsidiary ("Grand") into the parent company's ("AtliQ") analytical ecosystem.

To maintain system stability, I designed a Y-shaped Medallion Architecture that processes the subsidiary's data in parallel before merging it into a unified Gold-layer Star Schema.

🏗️ Architecture & Design
The pipeline follows the industry-standard Medallion pattern:

Landing Zone (AWS S3): Raw daily CSV files are ingested from disparate sources into a central cloud storage bucket.

Bronze Layer (Raw): Immutable copies of the source data are stored as Delta tables for auditability.

Silver Layer (Cleansed): PySpark workflows handle deduplication, data type casting, and standardization across both company datasets.

Gold Layer (Curated): The two data streams are merged into a final Star Schema (Fact_Orders and Dimensions).

Serving Layer: Databricks SQL creates flattened (denormalized) views to optimize performance for BI reporting.

🚀 Key Engineering Features
Incremental Loading: Developed logic to handle both massive full historical loads and efficient daily incremental (Delta) updates.

Parallel Processing: Engineered separate tracks for the subsidiary and parent company to prevent data contamination.

Automated Workflows: The pipeline is designed to move files from landing to processed folders in S3 to ensure no data is re-processed.

🛠️ Tech Stack
Compute: Databricks Community Edition

Languages: PySpark (Python/Spark), SQL

Storage: AWS S3 (Data Lake)

Data Modeling: Star Schema, Medallion Architecture

Visualization: Power BI

📊 Business Insights
The final Gold layer powers a Consolidated FMCG Dashboard that provides:

Unified revenue and quantity metrics across all business units.

Market share and product performance analysis.

Post-acquisition supply chain visibility.

<img width="2816" height="1536" alt="DEProjectAtliqonSportsBar" src="https://github.com/user-attachments/assets/9abbd31e-9891-4727-8918-edef94427998" />
Merger & Acquisition Scenario in simple steps.

The parent company's data is already at Gold Layer (pipeline is already established separately)
After acquisition of SportsBar company, its data will be appended in the Gold Layer of parent company Atliqon. The sports bar company's data will pass Bronze-Silver-Gold layer before appending it to parent's (Atliqon) Gold table.

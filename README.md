# fmcg-databricks-lakehouse
Built an end-to-end Data Lakehouse on Databricks to consolidate sales and daily order data after a parent FMCG company acquired a smaller subsidiary.
•	Cloud Ingestion: Configured Amazon S3 as the raw data landing zone to collect daily transactional CSVs from both companies.
•	Medallion Architecture: Built PySpark pipelines to process data through Bronze, Silver, and Gold layers, standardizing customer, product, and pricing dimensions.
•	Complex Data Loading: Implemented Databricks workflows to handle both Full Historical Loads and Daily Incremental (Delta) Loads for high-volume order data.
•	Data Modeling: Designed an optimized Star Schema and created flattened, denormalized views using Databricks SQL.
•	Analytics & BI: Connected the Gold layer directly to a BI Dashboard to provide stakeholders with unified post-acquisition business insights.
Skills: Databricks · PySpark · Amazon S3 · Data Lakehouse Architecture · Extract, Transform, Load (ETL) · Star Schema · Merger & Acquisition Data Integration.

<img width="2816" height="1536" alt="DEProjectAtliqonSportsBar" src="https://github.com/user-attachments/assets/9abbd31e-9891-4727-8918-edef94427998" />
Merger & Acquisition Scenario

The parent company's data is already at Gold Layer (pipeline is already established separately)
After acquisition of SportsBar company, its data will be appended in the Gold Layer of parent company Atliqon. The sports bar company's data will pass Bronze-Silver-Gold layer before appending it to parent's (Atliqon) Gold table.

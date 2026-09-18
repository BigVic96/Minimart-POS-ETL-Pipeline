# Minimart-POS-ETL-Pipeline
Minimart-POS-ETL-Pipeline is a fully automated, An end-to-end data engineering project: a messy, real-world-style Nigerian minimart POS dataset, taken from raw CSV through cleaning,
a star schema, an interactive Power BI dashboard, and a fully automated incremental-load pipeline.

The pipeline features event-driven automation by continually monitoring for incoming POS data files,
processing them using DuckDB, and serving refreshed analytics seamlessly.


The system utilizes a structured, multi-schema warehouse approach inside DuckDB paired with file-system orchestration:
Event Trigger: The pipeline constantly monitors a dedicated ingestion folder. 
The moment a new raw POS transaction file is dropped into the folder, the ETL process is automatically triggered.
staging Schema: The raw files are ingested directly into a landing zone without modifications to preserve data lineage.
main Schema (Star Schema): Data is cleaned, deduplicated, and transformed into optimized Fact and Dimension tables (main.fact_* and main.dim_*).
Power BI Ingestion: The finalized star schema seamlessly updates the Power BI dashboard, ensuring data changes reflect automatically for end-user reporting.

# 🛠️ Key FeaturesFile-Watch Automation
Implements automatic triggers that detect new incoming files to kick off the pipeline immediately upon arrival.
Scheduled Orchestration: Backed by Windows Task Scheduler configured on a weekly cadence to ensure routine synchronization and system maintenance.
High-Performance Analytics: Leverages DuckDB's columnar execution engine to transform millions of transactional rows efficiently on local infrastructure.
Automated End-to-End Reporting: Bridges the entire gap between a raw checkout file drop and an updated executive Power BI dashboard with zero manual intervention required.

# 🧰 Tech stack
DuckDB — data cleaning, star schema, SQL
Python — pipeline automation (duckdb package)
Power BI — dashboard and DAX measures
Windows Task Scheduler — scheduled, hands-off pipeline runs











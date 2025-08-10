# wealth-management-streaming-pipeline
End-to-end Databricks PySpark streaming ETL pipeline for real-time wealth management portfolio tracking using Delta Lake.

# Wealth Management Streaming Pipeline

## Project Overview

This project demonstrates an end-to-end real-time data engineering pipeline for the wealth management domain using Databricks, PySpark, and Delta Lake.
It simulates live stock transactions, enriches them with customer profiles, and produces analytics dashboards for portfolio tracking.

---

## Goals

* Simulate real-time stock transactions.
* Process data in a Bronze → Silver → Gold architecture.
* Enrich transactions with customer risk profiles.
* Build aggregated analytics for portfolio monitoring.
* Demonstrate streaming ETL skills for data engineering roles.

---

## Architecture

Producer Simulator → Bronze Layer (Raw Data) → Silver Layer (Enriched Data) → Gold Layer (Aggregations) → Analytics Dashboard

---

## Tech Stack

* Databricks (Community Edition)
* PySpark Structured Streaming
* Delta Lake
* Parquet and JSON
* GitHub for version control

---

## Project Structure

```
wealth-management-streaming-pipeline/
│
├── notebooks/
│   ├── 1_producer_simulator.ipynb     # Generates mock stock transactions
│   ├── 2_ingest_bronze.ipynb           # Ingests raw JSON into Bronze
│   ├── 3_silver_transform.ipynb        # Joins with customer profiles
│   ├── 4_gold_aggregation.ipynb        # Aggregates portfolio values
│   └── 5_analytics_report.ipynb        # Visual dashboards
│
├── data/
│   └── customers.csv                   # Static customer master data
│
├── images/
│   ├── dashboard.png                   # Sample analytics dashboard
│   └── pipeline_diagram.png            # Architecture diagram
│
├── README.md
└── .gitignore
```

---

## Data Flow

### Bronze Layer

* Stores raw JSON transactions.
* Schema includes:

  * customer\_id, stock\_symbol, transaction\_type, quantity, price, transaction\_time.

### Silver Layer

* Enriched with customer static data (name, risk\_category).
* Cleans and standardizes data types.

### Gold Layer

* Aggregates:

  * Total investment value per customer.
  * Portfolio value by risk category.
  * Top stocks by quantity.

---

## How to Run

1. Clone the repository:

   ```bash
   git clone https://github.com/<your-username>/wealth-management-streaming-pipeline.git
   ```

2. Upload notebooks to Databricks:

   * Import all `.ipynb` files into the Databricks workspace.

3. Run notebooks in order:

   * 1\_producer\_simulator → Generates streaming data.
   * 2\_ingest\_bronze → Reads into Bronze.
   * 3\_silver\_transform → Enriches with customer profiles.
   * 4\_gold\_aggregation → Creates final Gold dataset.
   * 5\_analytics\_report → Creates dashboards.

4. View results:

   * Bronze: `dbfs:/.../bronze`
   * Silver: `dbfs:/.../silver`
   * Gold:   `dbfs:/.../gold`

---

## Example Output

See `images/dashboard.png` for a sample portfolio dashboard.

---

## Key Learnings

* Implementing streaming ETL pipelines with PySpark.
* Using Delta Lake for ACID transactions in streaming.
* Designing Bronze → Silver → Gold architecture.
* Creating real-time analytics dashboards in Databricks.

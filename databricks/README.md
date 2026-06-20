# Databricks Section

This section organizes the Databricks material from the course into a GitHub-ready structure without changing the original exports in [../raw_databricks_exports/](../raw_databricks_exports/).

## Why multiple notebook versions are intentionally kept

The course task required the same analytics work to be demonstrated in multiple execution modes:

- BigQuery
- Spark SQL
- Spark DataFrame / Spark operators

For that reason, the Spark SQL notebooks and the Spark DataFrame/operator notebooks are intentionally both included in the final Databricks section. They are not accidental duplicates in the portfolio context; they document separate required execution styles for the exam.

## Structure

- [notebooks/spark_sql](./notebooks/spark_sql/)
- [notebooks/spark_dataframe](./notebooks/spark_dataframe/)
- [notebooks/data_enrichment](./notebooks/data_enrichment/)

## Notebook groups

### Spark SQL

- Query 1
- Query 2
- Query 3

These notebooks show the SQL-style Databricks execution mode.

### Spark DataFrame / Spark operators

- Query 1
- Query 2
- Query 3

These notebooks show the equivalent logic using Spark table loading, filtering, aggregation, and expression APIs.

### Data Enrichment

- `membership_spend_regression_enrichment.ipynb`

This notebook is kept separately because it is not one of the three required query implementations. It is an additional analytical extension on the same dataset.

## Dataset and environment assumption

The notebooks assume that the customer dataset has already been loaded in Databricks as:

- `default.ecommerce_customers`

This means the Databricks section is related to the same coursework dataset used in the Google Cloud part, but it does not currently prove a direct automated pipeline from BigQuery into Databricks.

## Important honesty note

The current data enrichment notebook does not use Spark MLlib. It uses:

- Spark DataFrame filtering and selection
- pandas conversion
- NumPy linear regression
- matplotlib plotting

If you later want to present it as an MLlib example, it would need a real refactor to `pyspark.ml`.

## Query mapping

The notebook-to-query comparison is documented in:

- [docs/query_mapping.md](../docs/query_mapping.md)

## Known mismatch to resolve later

Query numbering is preserved from the available Databricks exports. However, the current Google Cloud portfolio section defines Query 3 as:

- top 5 customers by yearly spending

while the Databricks Query 3 notebooks currently implement:

- average yearly spending where `Avg. Session Length > 34`

This mismatch is documented rather than hidden. The original university `Cloud Computing\\spark` subfolder was checked, and no additional Databricks notebook was found for a Spark version of `top 5 customers by yearly spending`.

So, at the current state of the evidence:

- Query 1 and Query 2 align across GCP and Databricks
- Query 3 does not align across the two sections
- the portfolio should present this as a real limitation of the archived material, not as a failure to organize files

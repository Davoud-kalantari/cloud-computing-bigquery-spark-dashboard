# Google Cloud Workflow

This document explains the Google Cloud workflow evidenced by the files preserved in this cleaned project.

Note:

- the original Looker Studio datasource linked to the coursework is no longer reproducible
- the repository now includes an executable replacement dashboard at [../dashboard/databricks_dashboard.ipynb](../dashboard/databricks_dashboard.ipynb)
- that notebook preserves the visualization objective using the same dataset without requiring the broken Looker Studio source

## 1. Source dataset

- Dataset file: [Ecommerce Customers.csv](<../data/Ecommerce Customers.csv>)
- Role: source data for the Google Cloud Storage and BigQuery workflow

## 2. Cloud Storage

The project used the Cloud Storage bucket:

- `ccbm-exam-dk-2025`

Evidence:

- [../evidence/screenshots/01_gcs_bucket_objects.png](../evidence/screenshots/01_gcs_bucket_objects.png)
- [../evidence/gsutil_bucket_list_command.txt](../evidence/gsutil_bucket_list_command.txt)

What this proves:

- the bucket exists
- the bucket contains the source dataset
- the bucket contains exported query result CSV files

What remains limited:

- the repository contains the bucket listing command text, not the terminal output

## 3. BigQuery dataset and table

The BigQuery resources shown by the available evidence are:

- project: `ccbm-exam-dk-2025`
- dataset: `ecommerce_data`
- table: `customers`

Evidence:

- [../evidence/screenshots/02_bigquery_workspace_dataset_queries.png](../evidence/screenshots/02_bigquery_workspace_dataset_queries.png)
- [../evidence/screenshots/03_bigquery_customers_schema.png](../evidence/screenshots/03_bigquery_customers_schema.png)

What this proves:

- the `ecommerce_data` dataset exists
- the `customers` table exists
- the schema is visible in BigQuery
- saved queries named `bigquery1`, `bigquery2`, and `bigquery3` exist in the workspace

## 4. Notebook execution

The notebook used for the BigQuery workflow is:

- [../notebooks/bigquery/Cloudcomputing_jupyter.ipynb](../notebooks/bigquery/Cloudcomputing_jupyter.ipynb)

The notebook shows:

- connection to BigQuery
- execution of three SQL queries
- conversion of query results into pandas dataframes
- export of query results to CSV
- upload logic for sending the CSV files back to Cloud Storage

Security note:

- the original workflow referenced a local credential file named `bigquery_key.json`
- the copied notebook in this cleaned project has been adjusted to use `GOOGLE_APPLICATION_CREDENTIALS`
- the credential file itself is intentionally excluded from this cleaned project

## 5. Extracted SQL

The three SQL statements were extracted from the notebook into standalone files:

- [../sql/query1.sql](../sql/query1.sql)
- [../sql/query2.sql](../sql/query2.sql)
- [../sql/query3.sql](../sql/query3.sql)

This makes the project easier to review and more recruiter-friendly than a notebook-only presentation.

## 6. Exported results

Canonical CSV outputs preserved in this cleaned project:

- [../results/bigquery_csv/query1_avg_yearly_spending.csv](../results/bigquery_csv/query1_avg_yearly_spending.csv)
- [../results/bigquery_csv/query2_avg_app_vs_web_time.csv](../results/bigquery_csv/query2_avg_app_vs_web_time.csv)
- [../results/bigquery_csv/query3_top_5_customers.csv](../results/bigquery_csv/query3_top_5_customers.csv)

These files correspond to:

- Query 1: average yearly amount spent
- Query 2: average app time and average website time
- Query 3: top 5 customers by yearly amount spent

## 7. Evidence quality summary

Covered with real files or screenshots:

- Cloud Storage bucket contents
- BigQuery dataset
- BigQuery table
- BigQuery schema
- saved query presence
- notebook-based BigQuery execution
- CSV result exports

Only partially documented:

- Cloud Shell verification output
- the exact original import procedure from Cloud Storage into BigQuery

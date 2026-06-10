# Cloud Computing Portfolio Project

This repository organizes the cleaned portfolio version of a university Cloud Computing project. The material currently has two documented layers built on the same customer dataset:

- a Google Cloud Platform layer centered on Cloud Storage and BigQuery
- a Databricks layer centered on Spark SQL and Spark DataFrame/operator execution
- an executable dashboard layer that replaces the broken Looker Studio datasource

The objective is to preserve real exam evidence, separate it into clear sections, and keep the portfolio technically honest.

## Project objective

The project uses `Ecommerce Customers.csv` as the source dataset and demonstrates how it was organized into a Google Cloud workflow:

- Google Cloud Storage bucket: `ccbm-exam-dk-2025`
- BigQuery dataset: `ecommerce_data`
- BigQuery table: `customers`
- three BigQuery queries
- CSV exports of the query results
- screenshot evidence from the GCP console

The Google Cloud documentation is preserved in this root section. The Databricks and Spark material is documented separately under:

- [databricks/README.md](./databricks/README.md)

The original Looker Studio dashboard is no longer reproducible because its datasource is broken. Instead of keeping only a static specification, this repository now includes an executable replacement dashboard:

- [dashboard/databricks_dashboard.ipynb](./dashboard/databricks_dashboard.ipynb)
- [dashboard/README.md](./dashboard/README.md)
- [dashboard/requirements.txt](./dashboard/requirements.txt)

## Dataset used

- Source dataset: [Ecommerce Customers.csv](<./data/Ecommerce Customers.csv>)
- Dataset role: input data used for the BigQuery import and subsequent SQL analysis

## BigQuery queries

The project includes three extracted SQL files:

- [sql/query1.sql](./sql/query1.sql): average yearly amount spent
- [sql/query2.sql](./sql/query2.sql): average time on app vs average time on website
- [sql/query3.sql](./sql/query3.sql): top 5 customers by yearly amount spent

The notebook evidence is preserved here as a cleaned copy of the original workflow notebook:

- [notebooks/bigquery/Cloudcomputing_jupyter.ipynb](./notebooks/bigquery/Cloudcomputing_jupyter.ipynb)

## Databricks and Spark section

The Spark material from the same course project is organized separately because the exam required the queries to be demonstrated in multiple execution modes:

- BigQuery
- Spark SQL
- Spark DataFrame / Spark operators

That section is documented here:

- [databricks/README.md](./databricks/README.md)
- [docs/query_mapping.md](./docs/query_mapping.md)

Important note:

- Query 1 and Query 2 align across GCP and Databricks
- the currently available Databricks Query 3 notebooks do not match the current BigQuery Query 3 artifact
- this mismatch is documented explicitly rather than hidden or rewritten

## Executable dashboard section

The repository also includes a recruiter-ready executable dashboard notebook that replaces the original broken Looker Studio dashboard while preserving the same visualization objective on the same dataset.

Main artifacts:

- [dashboard/databricks_dashboard.ipynb](./dashboard/databricks_dashboard.ipynb)
- [dashboard/README.md](./dashboard/README.md)

The dashboard includes:

- KPI cards
- Top 10 customers by yearly spending
- Membership length vs yearly spending
- Spending distribution
- Average yearly spending by membership range
- Average app time vs average website time
- Optional spending range distribution

To install the base local dependencies before running the dashboard notebook:

```bash
python -m pip install -r dashboard/requirements.txt
```

The `dashboard/` folder is self-contained and includes its own dataset copy under `dashboard/data/`.

## CSV result exports

Canonical exported results kept for the GitHub-ready version:

- [results/bigquery_csv/query1_avg_yearly_spending.csv](./results/bigquery_csv/query1_avg_yearly_spending.csv)
- [results/bigquery_csv/query2_avg_app_vs_web_time.csv](./results/bigquery_csv/query2_avg_app_vs_web_time.csv)
- [results/bigquery_csv/query3_top_5_customers.csv](./results/bigquery_csv/query3_top_5_customers.csv)

Duplicate CSV variants from the original course folder were not copied into this cleaned structure.

## Evidence screenshots

Real screenshots available in this cleaned project:

- [01_gcs_bucket_objects.png](./evidence/screenshots/01_gcs_bucket_objects.png)
- [02_bigquery_workspace_dataset_queries.png](./evidence/screenshots/02_bigquery_workspace_dataset_queries.png)
- [03_bigquery_customers_schema.png](./evidence/screenshots/03_bigquery_customers_schema.png)

These screenshots show:

- the Cloud Storage bucket `ccbm-exam-dk-2025` with source and exported files
- the BigQuery workspace with project `ccbm-exam-dk-2025`, dataset `ecommerce_data`, table `customers`, and saved queries
- the `customers` table schema

Additional command evidence:

- [evidence/gsutil_bucket_list_command.txt](./evidence/gsutil_bucket_list_command.txt)

## Security

Credentials are excluded for security reasons.

- `bigquery_key.json` is not included in this cleaned project
- `.gitignore` explicitly excludes `bigquery_key.json`
- the notebook copy in this repository has been adjusted to read credentials from `GOOGLE_APPLICATION_CREDENTIALS` instead of a committed local key file

## Limitations and reproducibility notes

- This cleaned project documents real available evidence only
- It does not invent missing screenshots, commands, or outputs
- The current evidence proves the BigQuery table, saved queries, schema, notebook workflow, and exported CSV results
- The Databricks material was recovered from the original course `spark` subfolder and reorganized in a cleaned portfolio section, but it is still limited to the notebooks that were actually available
- The original Looker Studio datasource is no longer available, so the executable Python/Databricks dashboard serves as the reproducible replacement
- The Cloud Shell step is only partially documented because the repository contains the `gsutil` command text, not the command output
- The exact original table-load operation into BigQuery is evidenced by the resulting table and schema screenshots, but not by a separate import script or CLI transcript
- No additional Databricks notebook was found that reproduces the current BigQuery Query 3 `top 5 customers by yearly spending` result
- Reproducing the workflow today would require a valid Google Cloud project, BigQuery access, a storage bucket, and a local credential file configured outside Git

## Repository layout

- [docs/google_cloud_workflow.md](./docs/google_cloud_workflow.md)
- [docs/query_mapping.md](./docs/query_mapping.md)
- [sql/](./sql/)
- [notebooks/bigquery/](./notebooks/bigquery/)
- [databricks/](./databricks/)
- [dashboard/](./dashboard/)
- [results/bigquery_csv/](./results/bigquery_csv/)
- [evidence/screenshots/](./evidence/screenshots/)
- [data/README.md](./data/README.md)

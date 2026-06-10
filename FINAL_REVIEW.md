# Final Review

## Repository readiness score

- `8.5/10`

Reasoning:

- the repository is well structured
- the dashboard is executable and self-contained
- credentials are excluded
- documentation is strong across GCP, Databricks, and dashboard sections
- remaining risk is mostly around notebook execution consistency and intentional duplicate dataset storage

## Remaining risks

- Notebook environments can still vary across users.
  - The dashboard notebook now includes bootstrap installation logic and `dashboard/requirements.txt`, but some users may still need to restart the kernel after installation.

- The dashboard dataset is intentionally duplicated.
  - `data/Ecommerce Customers.csv`
  - `dashboard/data/Ecommerce Customers.csv`
  - This is acceptable because the root `data/` copy supports the broader repository, while the `dashboard/` copy makes the dashboard folder standalone.

- The GCP section still references a credential-driven workflow conceptually.
  - No credential file is committed, but users reading the BigQuery notebook should understand that they must provide their own local credential file outside Git if they want to rerun that part.

- Query 3 mismatch remains documented.
  - Google Cloud Query 3 and Databricks Query 3 do not represent the same analytical question in the surviving course materials.
  - This is a documentation risk only, not a secret or security risk.

## Files safe to commit

- `.gitignore`
- `README.md`
- `PROJECT_AUDIT.md`
- `GOOGLE_CLOUD_AUDIT.md`
- `DATABRICKS_AUDIT.md`
- `FINAL_REVIEW.md`
- `requirements.txt`
- `data/README.md`
- `data/Ecommerce Customers.csv`
- `docs/CloudComputing_Project_Instructions.pdf`
- `docs/google_cloud_workflow.md`
- `docs/query_mapping.md`
- `evidence/gsutil_bucket_list_command.txt`
- `evidence/screenshots/01_gcs_bucket_objects.png`
- `evidence/screenshots/02_bigquery_workspace_dataset_queries.png`
- `evidence/screenshots/03_bigquery_customers_schema.png`
- `sql/query1.sql`
- `sql/query2.sql`
- `sql/query3.sql`
- `notebooks/bigquery/Cloudcomputing_jupyter.ipynb`
- `results/bigquery_csv/query1_avg_yearly_spending.csv`
- `results/bigquery_csv/query2_avg_app_vs_web_time.csv`
- `results/bigquery_csv/query3_top_5_customers.csv`
- `databricks/README.md`
- `databricks/notebooks/spark_sql/query1_spark_sql_avg_yearly_spending.ipynb`
- `databricks/notebooks/spark_sql/query2_spark_sql_avg_app_vs_website.ipynb`
- `databricks/notebooks/spark_sql/query3_spark_sql_avg_spending_long_sessions.ipynb`
- `databricks/notebooks/spark_dataframe/query1_spark_dataframe_avg_yearly_spending.ipynb`
- `databricks/notebooks/spark_dataframe/query2_spark_dataframe_avg_app_vs_website.ipynb`
- `databricks/notebooks/spark_dataframe/query3_spark_dataframe_avg_spending_long_sessions.ipynb`
- `databricks/notebooks/data_enrichment/membership_spend_regression_enrichment.ipynb`
- `dashboard/README.md`
- `dashboard/requirements.txt`
- `dashboard/databricks_dashboard.ipynb`
- `dashboard/data/Ecommerce Customers.csv`
- `raw_databricks_exports/ML_Linear_Model.ipynb`
- `raw_databricks_exports/query 1 through spark.ipynb`
- `raw_databricks_exports/query 2 through spark.ipynb`
- `raw_databricks_exports/query 2.ipynb`
- `raw_databricks_exports/query 3 through spark.ipynb`
- `raw_databricks_exports/query 3.ipynb`
- `raw_databricks_exports/query1.ipynb`

## Files not to commit

- `bigquery_key.json`
- any future `*.key` files
- any future `.env` file
- `.ipynb_checkpoints/`
- `__pycache__/`
- `.venv/`
- `venv/`
- `*.pyc`
- `.DS_Store`

## Credentials and secrets check

- No committed credential file was found in the cleaned repository workspace.
- Searches found documentation references to `bigquery_key.json`, but not the file itself.
- The references are acceptable because they explain what must remain excluded from Git.

## Dashboard path check

- `dashboard/databricks_dashboard.ipynb` does not rely on a single fragile absolute path.
- It first searches for `dashboard/data/Ecommerce Customers.csv`.
- It then falls back to the root `data/` copy.
- If running in Databricks with Spark access, it can also use `default.ecommerce_customers`.

## README link check

- Main documentation links were checked.
- Broken local links caused by URL-encoded spaces were corrected.
- Current README links now point to existing files in the workspace.

## Duplicate dataset check

- `data/Ecommerce Customers.csv` and `dashboard/data/Ecommerce Customers.csv` are intentionally duplicated.
- Recommended rationale for keeping both:
  - root `data/` serves the overall project structure
  - `dashboard/data/` makes the dashboard folder directly runnable on its own

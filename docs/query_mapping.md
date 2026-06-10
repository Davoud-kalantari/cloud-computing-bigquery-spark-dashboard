# Query Mapping

This document maps the currently available Google Cloud query evidence to the Databricks Spark SQL and Spark DataFrame/operator notebooks.

The mapping is evidence-based, not reconstructed from memory. Where the available Databricks notebooks do not match the current BigQuery query set exactly, the mismatch is documented explicitly.

## Mapping table

| Query label | BigQuery query | Spark SQL equivalent | Spark DataFrame/operator equivalent | Output/result | Notes |
|---|---|---|---|---|---|
| Query 1 | Average `Yearly Amount Spent` from `ccbm-exam-dk-2025.ecommerce_data.customers` | [query1_spark_sql_avg_yearly_spending.ipynb](C:/Users/David/OneDrive/Documenti/github-sistemazione/databricks/notebooks/spark_sql/query1_spark_sql_avg_yearly_spending.ipynb) | [query1_spark_dataframe_avg_yearly_spending.ipynb](C:/Users/David/OneDrive/Documenti/github-sistemazione/databricks/notebooks/spark_dataframe/query1_spark_dataframe_avg_yearly_spending.ipynb) | `499.91985771641924` in Databricks raw outputs; [BigQuery CSV](C:/Users/David/OneDrive/Documenti/github-sistemazione/results/bigquery_csv/query1_avg_yearly_spending.csv) contains `499.9198577164192` | Same analytical question across GCP and Spark. Small decimal formatting difference only. |
| Query 2 | Average `Time on App` and average `Time on Website` from `ccbm-exam-dk-2025.ecommerce_data.customers` | [query2_spark_sql_avg_app_vs_website.ipynb](C:/Users/David/OneDrive/Documenti/github-sistemazione/databricks/notebooks/spark_sql/query2_spark_sql_avg_app_vs_website.ipynb) | [query2_spark_dataframe_avg_app_vs_website.ipynb](C:/Users/David/OneDrive/Documenti/github-sistemazione/databricks/notebooks/spark_dataframe/query2_spark_dataframe_avg_app_vs_website.ipynb) | `avg_time_on_app = 14.350284262734618`, `avg_time_on_website = 33.95692625943925`; [BigQuery CSV](C:/Users/David/OneDrive/Documenti/github-sistemazione/results/bigquery_csv/query2_avg_app_vs_web_time.csv) contains the same values with formatting differences | Same analytical question across GCP and Spark. |
| Query 3 | Current Google Cloud portfolio Query 3: top 5 customers by yearly spending | [query3_spark_sql_avg_spending_long_sessions.ipynb](C:/Users/David/OneDrive/Documenti/github-sistemazione/databricks/notebooks/spark_sql/query3_spark_sql_avg_spending_long_sessions.ipynb) | [query3_spark_dataframe_avg_spending_long_sessions.ipynb](C:/Users/David/OneDrive/Documenti/github-sistemazione/databricks/notebooks/spark_dataframe/query3_spark_dataframe_avg_spending_long_sessions.ipynb) | Databricks raw outputs show `avg_spending_long_sessions = 545.0664955527343` | Query numbering is preserved from the Databricks exports, but the available Spark Query 3 logic does not match the current BigQuery Query 3 artifact. This should be documented, not hidden. |

## Interpretation

The Spark SQL and Spark DataFrame/operator notebooks are intentionally both kept because the exam required multiple execution modes.

What the current evidence proves:

- Query 1 has a BigQuery version, a Spark SQL version, and a Spark DataFrame/operator version
- Query 2 has a BigQuery version, a Spark SQL version, and a Spark DataFrame/operator version
- Query 3 has a Spark SQL version and a Spark DataFrame/operator version

What remains mismatched:

- the currently documented Google Cloud Query 3 is a different business question from the Databricks Query 3 notebooks

What was verified:

- the original university `Cloud Computing\\spark` subfolder was checked
- no additional Databricks notebook was found for a Spark version of `top 5 customers by yearly spending`
- therefore the current mismatch is a real limitation of the surviving materials, not a documentation mistake in this cleaned portfolio

## Data Enrichment mapping

The additional enrichment notebook is:

- [membership_spend_regression_enrichment.ipynb](C:/Users/David/OneDrive/Documenti/github-sistemazione/databricks/notebooks/data_enrichment/membership_spend_regression_enrichment.ipynb)

This notebook is not part of the three required query implementations. It is a separate exploratory extension and currently uses Spark plus pandas/NumPy rather than Spark MLlib.

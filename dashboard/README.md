# Dashboard

This folder contains the executable replacement for the original university Looker Studio dashboard.

This folder is intentionally self-contained: you can enter `dashboard/`, install the local requirements, open the notebook, and run the dashboard from there.

## Why this replacement exists

The original Looker Studio dashboard is no longer reproducible because its datasource is broken or unavailable. To preserve the visualization objective of the course project, this repository now includes a real executable notebook built from the same [Ecommerce Customers.csv](<./data/Ecommerce Customers.csv>) dataset.

## Main artifact

- [databricks_dashboard.ipynb](./databricks_dashboard.ipynb)

## What the notebook does

The notebook:

- loads the dataset from the local project `data/` folder when available
- supports loading from Databricks table `default.ecommerce_customers` when running in Databricks
- performs data quality checks
- computes KPI cards
- renders charts for customer value, membership behavior, and platform usage
- ends with business insights and reproducibility notes

## How to run

### Local/Jupyter execution

1. Enter the `dashboard/` folder.
2. Install the local dependencies:

   ```bash
   python -m pip install -r requirements.txt
   ```

3. Open [databricks_dashboard.ipynb](./databricks_dashboard.ipynb).
4. Run all cells from top to bottom.
5. The notebook will first look for `dashboard/data/Ecommerce Customers.csv`.
6. If PySpark is available locally, it may use Spark; otherwise it falls back to pandas for loading.

### Databricks execution

1. Import or open the notebook in Databricks.
2. Ensure `default.ecommerce_customers` exists, or upload the CSV file preserved in `dashboard/data/`.
3. Run all cells.

## Included visuals

- KPI cards
- Top 10 customers by yearly spending
- Membership length vs yearly spending
- Spending distribution
- Average spending by membership range
- Average time on app vs average time on website
- Optional spending range distribution

## Notes

- No credentials are required.
- No Looker Studio datasource is required.
- No fake values are hardcoded.
- The notebook includes a bootstrap cell that attempts to install missing base visualization dependencies automatically.
- PySpark is optional for local execution because the notebook can run from the CSV dataset with pandas and matplotlib.
- The dataset is also copied locally into `dashboard/data/` so the folder remains standalone.

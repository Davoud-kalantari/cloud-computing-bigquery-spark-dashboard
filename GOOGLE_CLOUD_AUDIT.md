# Google Cloud Audit

Project folder inspected:
- original local `Cloud Computing` coursework folder

Scope of this audit:
- Google Cloud Platform part only
- No Spark analysis
- No Databricks analysis
- No Looker Studio analysis

## 1. Project interpretation

Based on the project instruction PDF name, the course materials present in the folder, and the notebook contents, this project appears to be the Google Cloud section of a cloud computing exam assignment centered on:

- setting up a Google Cloud project
- using Google Cloud Storage as staging/output storage
- loading an e-commerce customer dataset into BigQuery
- running at least three SQL queries on the BigQuery table
- exporting query results as CSV files
- uploading those query outputs back to a Google Cloud Storage bucket

What the existing files prove with reasonable confidence:

- the dataset used for the GCP part is `Ecommerce Customers.csv`
- the working Google Cloud project ID was likely `ccbm-exam-dk-2025`
- the BigQuery dataset/table queried in the notebook was `ccbm-exam-dk-2025.ecommerce_data.customers`
- at least three BigQuery queries were executed in a Jupyter notebook
- query outputs were saved locally as CSV files
- the notebook contains Python code intended to upload exported results to a Cloud Storage bucket named `ccbm-exam-dk-2025`

What is not fully proven by the current files:

- the exact GCP console steps used to create the project
- the exact bucket creation step
- the exact dataset upload command to Cloud Storage
- the exact BigQuery import/load command or GUI action from Cloud Storage to BigQuery
- screenshot-level evidence from the GCP console
- confirmed output from Cloud Shell bucket verification

Overall interpretation:

This is a real university cloud assignment with genuine GCP work in progress, but the evidence is mixed together with lecture material, duplicate outputs, credentials, temporary files, and a partially started repo-like folder. For GitHub, the Google Cloud portion can become a solid small portfolio project, but only after it is cleaned, documented, and stripped of secrets.

## 2. File-by-file analysis

| Current file/folder name | Detected role | Related GCP step | Keep / rename / move / exclude | Reason |
|---|---|---|---|---|
| `.ipynb_checkpoints/` | Jupyter auto-generated checkpoint folder | Notebook work artifact | Exclude | Not project evidence; notebook metadata clutter only. |
| `.ipynb_checkpoints/Cloudcomputing_jupyter-checkpoint.ipynb` | Auto-saved notebook checkpoint | Notebook work artifact | Exclude | Duplicate of working notebook, not useful for GitHub. |
| `.ipynb_checkpoints/Untitled-checkpoint.ipynb` | Auto-saved checkpoint of scratch notebook | Notebook work artifact | Exclude | Temporary and incomplete. |
| `cloud-computing-bigquery-spark-looker/` | Partially started cleaned project folder | Proposed repo organization attempt | Keep, but only as reference for later | It suggests you had already started separating this work, but it currently does not contain usable evidence. |
| `cloud-computing-bigquery-spark-looker/notebooks/` | Empty placeholder folder | None yet | Exclude from evidence, possibly reuse later | Good future structure idea, but currently empty. |
| `cloud-computing-bigquery-spark-looker/sql/` | Empty placeholder folder | None yet | Exclude from evidence, possibly reuse later | Good future structure idea, but currently empty. |
| `$ gsutil ls gsccbm-exam-dk-2025.txt` | Text note containing a Cloud Shell / PowerShell `gsutil ls` command | Cloud Shell verification | Keep, rename, document | This is direct evidence of the intended bucket verification command, but it contains only the command text, not its output. |
| `1-GcpFirstSteps.pptx` | Course slide deck about GCP onboarding | GCP project setup reference | Exclude from GitHub deliverable; mention in docs only if needed | Teaching material, not project-specific evidence. |
| `2-BigQuery.pptx` | Course slide deck about BigQuery usage | BigQuery background/reference | Exclude from GitHub deliverable; mention in docs only if needed | Reference material, not your project artifact. |
| `2.4-BigQuery+LookerStudio.pptx` | Course slide deck for BigQuery plus Looker Studio | Mostly outside current scope | Exclude | It is lecture material and partly outside the current GCP-only scope. |
| `3-Unix-Shell-w-examples.pptx` | General Unix shell lecture deck | Indirect Cloud Shell background | Exclude | Background lecture deck, not project evidence. |
| `avg_time_app_web.csv` | CSV export of query result comparing average app vs website time | Query results export | Keep, rename, move | Useful evidence of a completed query result export. Current naming is understandable but can be made more consistent later. |
| `avg_yearly_spending.csv` | CSV export of query result for average yearly spending | Query results export | Keep, rename, move | Useful evidence of query output generated from BigQuery workflow. |
| `Bigquert1.json.json` | Likely saved JSON result for Query 1, probably from BigQuery Web Console or manual export | Query 1, possibly Web Console execution | Keep, rename, move, but mark as uncertain | Real result data exists, but the filename is misspelled and the origin is not fully documented. |
| `Bigquery2.json.json` | Likely saved JSON result for Query 2 | Query 2, possibly Web Console execution | Keep, rename, move, but mark as uncertain | Appears to be query output, but the generation path is not documented. |
| `Bigquery3.json.json` | Likely saved JSON result for Query 3 | Query 3, possibly Web Console execution | Keep, rename, move, but mark as uncertain | Strong evidence of a query result set, but provenance is not explicit. |
| `BigQuery_1.csv` | CSV export of Query 1 result | Query results export | Keep, rename, move | Useful as evidence; currently duplicates `avg_yearly_spending.csv`. |
| `BigQuery_2.csv` | CSV export of Query 2 result | Query results export | Keep, rename, move | Useful as evidence; currently duplicates `avg_time_app_web.csv`. |
| `BigQuery_3.csv` | CSV export of Query 3 result | Query results export | Keep, rename, move | Useful as evidence; currently duplicates `top_5_customers.csv`. |
| `bigquery_key.json` | Google service account credential file | Notebook authentication to GCP | Exclude immediately from any GitHub version | This is sensitive credential material and must never be published. |
| `Cloudcomputing_jupyter.ipynb` | Main working notebook querying BigQuery and uploading results to GCS | BigQuery queries, notebook execution, results export | Keep, rename, document | This is the strongest piece of workflow evidence in the folder. It proves real notebook-based BigQuery usage. |
| `CloudComputing_Project_Instructions.pdf` | Assignment/instructions document | Project requirements reference | Keep, move to `docs/` later | Important contextual documentation for understanding the assignment. |
| `Ecommerce Customers.csv` | Source dataset for the BigQuery work | Dataset source, potential upload input | Keep, but document source/license | This is the apparent raw dataset used for import/querying and is relevant if redistribution is allowed. |
| `EcommerceCustomers_copy.xlsx` | Spreadsheet copy of the dataset | Ancillary data copy | Exclude from GCP-focused GitHub section unless needed | Not essential to prove the GCP workflow; probably a convenience copy. |
| `EcommerceCustomers_Looker.xlsx` | Spreadsheet likely prepared for Looker Studio work | Mostly outside current scope | Exclude from GCP-only section | Relevant to later BI work, not necessary for the GCP section. |
| `media_spesa_annua.csv` | CSV export of average yearly spending result | Query results export | Keep or merge with duplicate later | It appears to duplicate `avg_yearly_spending.csv` with an Italian naming variant. |
| `top_5_customers.csv` | CSV export of top 5 customers by yearly spending | Query results export | Keep, rename, move | Useful direct evidence of Query 3 output. |
| `Untitled.ipynb` | Scratch/incomplete notebook | None or failed start | Exclude | Contains only incomplete code and adds noise. |
| `~$2-BigQuery.pptx` | Temporary Office lock file | None | Exclude | System temporary file, not a project artifact. |

## 3. Mapping to the exam requirements

- [ ] GCP project setup: `partially covered`
  - Evidence: notebook references project ID `ccbm-exam-dk-2025`; screenshot `02_bigquery_workspace_dataset_queries.png` shows the active project context.
  - Gap: no explicit project creation screenshots or setup transcript.

- [ ] Cloud Storage bucket: `covered`
  - Evidence: screenshot `01_gcs_bucket_objects.png` shows bucket `ccbm-exam-dk-2025`; notebook upload code also targets the same bucket.

- [ ] Dataset upload: `covered`
  - Evidence: screenshot `01_gcs_bucket_objects.png` shows the source dataset in the bucket; the source CSV is preserved in the cleaned project.

- [ ] Cloud Shell verification: `partially covered`
  - Evidence: `$ gsutil ls gsccbm-exam-dk-2025.txt` contains a bucket listing command.
  - Gap: the file contains the command text only, not the resulting output.

- [ ] BigQuery import: `covered`
  - Evidence: screenshot `02_bigquery_workspace_dataset_queries.png` shows dataset `ecommerce_data` and table `customers`; screenshot `03_bigquery_customers_schema.png` shows the loaded schema; notebook queries the same table.

- [x] Query 1: `covered`
  - Evidence: notebook contains Query 1 SQL and CSV/JSON result files exist.

- [x] Query 2: `covered`
  - Evidence: notebook contains Query 2 SQL and CSV/JSON result files exist.

- [x] Query 3: `covered`
  - Evidence: notebook contains Query 3 SQL and CSV/JSON result files exist.

- [ ] Query results export: `covered`
  - Evidence: multiple CSV result files exist, and notebook code writes them to disk and includes GCS upload code.

- [ ] Notebook/JupyterLab BigQuery execution: `covered`
  - Evidence: `Cloudcomputing_jupyter.ipynb` contains authentication, query execution, DataFrame conversion, CSV export, and GCS upload code.

Status summary:

- clearly covered: bucket contents, dataset upload evidence, BigQuery import outcome, Query 1, Query 2, Query 3, query result export, notebook execution
- partly evidenced: project setup, Cloud Shell check
- remaining weak point: Cloud Shell verification is still not backed by terminal output

## 4. Recommended GitHub structure for GCP only

Proposed structure for the Google Cloud section only:

- `README.md`
- `docs/`
- `docs/assignment-reference/`
- `notebooks/`
- `notebooks/bigquery/`
- `sql/`
- `results/`
- `results/bigquery_csv/`
- `results/bigquery_json/`
- `evidence/`
- `evidence/cloud-shell/`
- `data/`
- `data/README.md`

How the current files would conceptually map:

- `README.md`
  - explain the GCP workflow end to end
  - describe project ID, bucket role, BigQuery table, and the three queries
  - explicitly note that credentials are excluded

- `docs/assignment-reference/`
  - `CloudComputing_Project_Instructions.pdf`
  - optionally only if redistribution is acceptable

- `notebooks/bigquery/`
  - cleaned version of `Cloudcomputing_jupyter.ipynb`

- `sql/`
  - separate `.sql` files extracted later from the notebook for Query 1, Query 2, Query 3

- `results/bigquery_csv/`
  - final kept CSV outputs only
  - one canonical file per query, not duplicates

- `results/bigquery_json/`
  - JSON exports only if you want to show Web Console style outputs
  - filenames should be corrected and standardized

- `evidence/cloud-shell/`
  - renamed version of `$ gsutil ls gsccbm-exam-dk-2025.txt`
  - ideally replaced later with a file containing both the command and the real output

- `data/`
  - only the source dataset if it is safe and permitted to redistribute
  - otherwise `data/README.md` should describe the source and how to obtain it

Files that should not enter the GitHub-ready GCP section:

- `bigquery_key.json`
- `.ipynb_checkpoints/`
- `Untitled.ipynb`
- `~$2-BigQuery.pptx`
- lecture `.pptx` files
- Looker-specific Excel copy unless needed later for the BI section

## 5. Missing evidence

The current evidence is now much stronger thanks to the screenshots, but the following items are still missing or weak if you want the most complete GitHub-ready story:

- Cloud Shell output for `gsutil ls` or equivalent verification command
- separate SQL files for the three queries
- explicit note about the source of `Ecommerce Customers.csv`
- a safe credentials setup explanation using environment variables instead of committed keys

Now addressed in the cleaned structure:

- real screenshot of the Cloud Storage bucket
- real screenshot of the BigQuery workspace with dataset, table, and saved queries
- real screenshot of the `customers` schema
- separate SQL files for Query 1, Query 2, and Query 3
- canonical CSV outputs with duplicate variants excluded from the cleaned layout

Potentially useful to recover later if available:

- BigQuery Web Console screenshots for query execution
- job history screenshots or export screenshots
- Cloud Shell command history used during upload/check steps

## 6. Next actions

Safe step-by-step plan for turning only the Google Cloud part into a GitHub-ready section later:

1. Decide the canonical evidence set.
   - Keep the main notebook, one canonical CSV output per query, the assignment PDF, and one Cloud Shell evidence file.

2. Remove secrets from the future GitHub version.
   - Exclude `bigquery_key.json` completely.
   - Replace notebook credential usage with documented environment-variable instructions.

3. Standardize the query artifacts.
   - Choose one naming convention for Query 1, Query 2, Query 3 outputs.
   - Keep either the descriptive CSV names or the `BigQuery_*.csv` series, not both.

4. Separate code from evidence.
   - Notebook goes under `notebooks/bigquery/`.
   - Query outputs go under `results/`.
   - Cloud Shell proof goes under `evidence/cloud-shell/`.

5. Extract the SQL from the notebook.
   - Create one `.sql` file per query.
   - This makes the project more recruiter-friendly and easier to scan.

6. Document the missing steps honestly.
   - If you do not have screenshots for setup/import/upload, say so clearly in the README.
   - Do not claim those parts are complete unless you recover real evidence.

7. Decide how to handle the dataset.
   - If the dataset can be redistributed, include it in a small `data/` area.
   - If not, replace it with a `data/README.md` containing the source link and schema summary.

8. Add a concise README focused on workflow.
   - Describe: dataset -> Cloud Storage -> BigQuery -> three queries -> CSV export -> optional upload of results back to Cloud Storage.

9. Add any missing evidence you can still recover.
   - Cloud Shell output, BigQuery screenshots, bucket screenshots, and table-import proof would significantly strengthen the portfolio value.

10. The clean GitHub-ready folder can now be built around the current canonical set.
   - At this stage, the project becomes much easier to present without mixing in Spark, Databricks, or Looker work.

## Real evidence of the Google Cloud workflow

Strongest evidence currently present:

- `Cloudcomputing_jupyter.ipynb`
- `avg_yearly_spending.csv`
- `avg_time_app_web.csv`
- `top_5_customers.csv`
- `BigQuery_1.csv`
- `BigQuery_2.csv`
- `BigQuery_3.csv`
- `Bigquert1.json.json`
- `Bigquery2.json.json`
- `Bigquery3.json.json`
- `$ gsutil ls gsccbm-exam-dk-2025.txt`
- `Ecommerce Customers.csv`

Highest-risk file that must never be published:

- `bigquery_key.json`

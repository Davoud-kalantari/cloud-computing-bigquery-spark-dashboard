# Project Audit

Source archive checked:
- `C:\Users\David\Desktop\DATA SCIENCE MAGISTRALE`
- Inspected subfolders only:
  - `C:\Users\David\Desktop\DATA SCIENCE MAGISTRALE\Cloud Computing`
  - `C:\Users\David\Desktop\DATA SCIENCE MAGISTRALE\BIG DATA`

## 1) Cloud Computing

- Detected project topic: Google Cloud / BigQuery analysis of an e-commerce customer dataset, with CSV exports and upload-to-GCS steps.
- Detected technologies: Python, Jupyter Notebook, `google-cloud-bigquery`, `google-cloud-storage`, `pandas`, CSV, Google Cloud Storage, service account JSON authentication.
- Current state: messy
- Files found:
  - `Cloudcomputing_jupyter.ipynb`
  - `Untitled.ipynb`
  - `CloudComputing_Project_Instructions.pdf`
  - `bigquery_key.json`
  - `Ecommerce Customers.csv`
  - `EcommerceCustomers_copy.xlsx`
  - `EcommerceCustomers_Looker.xlsx`
  - `Bigquery2.json.json`, `Bigquery3.json.json`
  - `Bigquert1.json.json`
  - `BigQuery_1.csv`, `BigQuery_2.csv`, `BigQuery_3.csv`
  - `avg_yearly_spending.csv`
  - `avg_time_app_web.csv`
  - `top_5_customers.csv`
  - `1-GcpFirstSteps.pptx`, `2-BigQuery.pptx`, `2.4-BigQuery+LookerStudio.pptx`, `3-Unix-Shell-w-examples.pptx`
  - `.ipynb_checkpoints/` artifacts
- Files missing:
  - `README.md`
  - `requirements.txt` or environment file
  - `.gitignore`
  - A cleaned notebook without install/output clutter
  - A safe authentication approach that does not commit credentials
- Whether it is publishable on GitHub: Yes, but not as-is. It needs secret removal and cleanup first.
- Recruiter value: 6/10
- Risks:
  - `bigquery_key.json` is a service-account credential and should not be published
  - Hardcoded project/bucket names are present in the notebook
  - Derived CSV outputs are mixed with source material
  - `Untitled.ipynb` and checkpoint files add noise
  - `Ecommerce Customers.csv` should be checked for reuse rights before publishing
- Recommended clean repository folder name: `cloud-computing-bigquery-ecommerce`
- Recommended next action: fix

## 2) BIG DATA

- Detected project topic: Airbnb / Sicily housing analytics with Tableau Prep ETL, Tableau dashboards, and written project reports.
- Detected technologies: Tableau Prep (`.tfl`), Excel, CSV, Word documents, PDF, PNG exports, video recordings, Windows installer artifacts.
- Current state: messy
- Files found:
  - Tableau Prep flows:
    - `AirbnbDataPipeline.tfl`
    - `Flow1 finale.tfl`
    - `cartelle di lavoro PREP\Flow1.tfl`
    - `cartelle di lavoro PREP\Flow1 finale.tfl`
    - backup copies in `cartelle di lavoro PREP\`
    - recovered flows in `Repository personale di Tableau Prep\`
  - Data files:
    - `AirbnbPrice.xlsx`
    - `HouseInfo.xlsx`
    - `CitiesInSicily.xlsx`
    - `CitiesInSicily_BUY_RENT.xlsx`
    - `OccupancyRateByCity.xlsx`
    - `listings.csv`
    - `calendar.csv`
  - Reports and documentation:
    - `FIRST ASSIGNMENT.docx`
    - `First Assignment  Big data - Davoud Kalantari.docx`
    - `First Assignment  Big data - Davoud Kalantari.pdf`
    - `Project.docx`
    - `Project.pdf`
    - `REPORT BIG DATA ANALYTICS.docx`
    - `REPORT BIG DATA ANALYTICS.pdf`
    - `REPORT BIG DATA ANALYTICS_240618_194744_240618_200441.pdf`
    - `BOZZA BIG DATA.docx`
    - `SupportSlide_AirBNBUseCase_Part1.pdf`
  - Visual / export assets:
    - multiple `.png` dashboard images
    - `.mp4` recordings in `VIDEO LEZ BIG DATA\`
  - Extra noise / tooling:
    - `TableauPrep-2024-1-0.exe`
    - `DeepLSetup.exe`
    - `xampp-windows-x64-8.2.12-0-VS16-installer (1).exe`
    - Tableau Prep log files in `Repository personale di Tableau Prep\Log\`
- Files missing:
  - `README.md`
  - A single clean top-level project entry point
  - A short repo explanation of which `.tfl` file is canonical
  - A concise exported preview set for the final dashboard/report
  - `.gitignore`
- Whether it is publishable on GitHub: Not as-is. It needs curation, deduplication, and removal of heavy/non-repo assets.
- Recruiter value: 5/10
- Risks:
  - Raw Airbnb data may include personally identifying or sensitive information
  - Many duplicate flow copies make the project hard to follow
  - Installers, videos, and logs add unnecessary weight
  - Several documents contain student identity details
  - The structure is hard to understand without a README
- Recommended clean repository folder name: `airbnb-tableau-prep-etl-sicily`
- Recommended next action: fix

## Notes

- I did not modify the source archive.
- I did not create repositories, push anything, or delete anything.
- The most urgent cleanup item is the Cloud Computing credential file before any GitHub publication.

# CMPS360 Assignment 1 — Hotel Booking Data Pipeline

## Modular execution order

## Dataset

**Dataset name:** Hotel Booking Demand

**Dataset source (provided by the instructor):**
https://pmc.ncbi.nlm.nih.gov/articles/PMC6297060/?#s0020

**Access date:** October 14, 2026 (verify this is the date you accessed the link).

The dataset contains two CSV files:

- `H1.csv` — 40,060 rows
- `H2.csv` — 79,330 rows

Each file contains 31 source columns, giving a total of 119,390 records.

The dataset files are not uploaded to GitHub, following the instructor's instructions.

**To reproduce the project:** Obtain `H1.csv` and `H2.csv` using the instructor-provided dataset source and place both files inside `assign1/data/raw/` before running the notebooks.

Open the `assign1` directory in VS Code and run the following notebooks **in order**, from top to bottom, saving the outputs of each before proceeding:

1. `01_dataset_and_strategy.ipynb` — inspect source data, document questions and ingestion design.
2. `02_bronze.ipynb` — connect to DuckDB/DuckLake and ingest raw data with provenance.
3. `03_silver.ipynb` — validate, quarantine, clean, and report data quality.
4. `04_gold.ipynb` — create dimensions and fact table, show the star schema, validate keys.
5. `05_analytics_and_reflection.ipynb` — four Gold-only SQL analyses, saved result tables, optional charts, and reflection.

Each notebook has its own kernel; the Bronze, Silver, and Gold tables persist in the DuckLake catalog between notebooks. **Do not run notebooks simultaneously** against the same local database. The file `star_schema.png` is used by the Gold notebook.

## Setup

Install Python, Jupyter support, and packages with `python -m pip install pandas duckdb matplotlib numpy ipykernel jupyter`. Run notebooks with the working directory set to `assign1` so relative paths resolve. The first DuckLake installation may require internet access. Database and DuckLake data files are generated locally.

## Expected quality reconciliation (from saved original run)

Bronze 119,390 rows; Silver 119,209 rows; quarantine 181 rows. Re-run to verify these counts. The data contains no guaranteed source booking ID; lineage uses file, load ID, and source row number.

## Limitations

Historical observations from only two hotels; not representative of every hotel or present-day demand. Incremental batch updates are proposed but not implemented as a live scheduled ingestion service. All five modular notebooks have been executed in sequence, and their outputs have been saved.

## Acknowledgements

Dataset source is linked above. AI assistance was used to review rubric coverage and prepare documentation, a schema diagram, a reflection draft, and a modular reorganization of the existing notebook. Review the acknowledgement for accuracy and comply with course policy.

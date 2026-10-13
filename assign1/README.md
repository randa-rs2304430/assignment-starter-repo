# Assignment 1 — Hotel Booking Data Pipeline

CMPS 360: Hands-on Data Engineering

## Dataset
Hotel Booking Demand dataset, accompanying the research article:
https://pmc.ncbi.nlm.nih.gov/articles/PMC6297060/

Two original CSV files are used: `H1.csv` (Resort Hotel, 40,060 records) and `H2.csv` (City Hotel, 79,330 records). Each source file contains 31 original columns. The notebook combines these records for a total of 119,390 input rows.

## Project structure
```
assign1/
  assign1.ipynb
  README.md
  data/
    raw/
      H1.csv
      H2.csv
```

## Setup and execution
1. Install Python and the packages `pandas`, `duckdb`, `matplotlib`, `numpy`, `ipykernel`, and `jupyter`.
2. Open the `assign1` directory in VS Code, and select a Python notebook kernel.
3. Ensure both CSV files are in `data/raw/` relative to the notebook.
4. Run **Restart Kernel and Run All Cells**, from top to bottom.
5. Check Bronze/Silver/Gold counts, quarantine report, integrity tests, four query result tables, and four charts.
6. Save the executed notebook before committing to GitHub.

The notebook uses DuckDB and DuckLake; the first run may need internet access to install the DuckLake extension. DuckDB database files and DuckLake storage are generated locally.

## Analytical questions
1. How do cancellation rates compare between Resort and City Hotels?
2. How do average daily rates vary across arrival months by hotel type?
3. Which market segments have the most bookings?
4. How does lead time differ between canceled and non-canceled bookings across hotel types?

## Known limitations
The historical dataset covers two hotels and is not representative of every hotel or current demand. Source files do not include a guaranteed unique booking ID; the pipeline retains file and row identifiers for lineage. The proposed recurring ingestion approach is a design, not a live scheduled service.

## AI and external sources
Dataset: Hotel Booking Demand research article linked above. AI assistance was used to review rubric coverage and draft portions of documentation, the diagram description, and reflection. Review this statement for accuracy and comply with the course's academic-integrity policy.

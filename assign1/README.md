# Assignment 1 — Hotel Booking Data Pipeline

## Project Overview

This project implements an end-to-end data engineering pipeline using Python, DuckDB, and DuckLake. It processes hotel booking data using the Medallion Architecture (Bronze, Silver, and Gold layers).

The objective is to transform raw hotel booking records into clean, structured datasets suitable for business analysis.

## Dataset

**Dataset Name:** Hotel Booking Demand Dataset

**Source:** [Hotel Booking Demand Research Article](https://pmc.ncbi.nlm.nih.gov/articles/PMC6297060/)

**Files:**

- H1.csv — Resort Hotel bookings (40,060 records)
- H2.csv — City Hotel bookings (79,330 records)

**Total Records:** 119,390

The dataset contains hotel reservation information, including booking cancellations, lead time, arrival dates, room rates, and market segments.

## Technologies Used

- Python 3.12
- Pandas
- DuckDB
- DuckLake
- Matplotlib
- NumPy
- Jupyter Notebook
- Visual Studio Code

## Pipeline Architecture

### Bronze Layer — Raw Data Ingestion

The Bronze layer stores raw hotel booking records from both CSV files.

- Total ingested records: 119,390
- Preserves original source information
- Tracks source file names, row numbers, and ingestion metadata

### Silver Layer — Data Cleaning

The Silver layer performs data validation and cleaning.

- Clean records: 119,209
- Quarantined records: 181
- Validates booking information and numerical values
- Separates invalid records from clean data

### Gold Layer — Dimensional Modeling

The Gold layer organizes clean records into a dimensional model for analytical queries.

- Fact table: `fact_bookings`
- Hotel dimension: `dim_hotel`
- Date dimension: `dim_date`
- Market segment dimension: `dim_market_segment`
- Total fact records: 119,209

## Analytical Queries

### Query 1: Hotel Cancellation Rates

City Hotels have a cancellation rate of 41.79%, while Resort Hotels have a cancellation rate of 27.77%.

### Query 2: Average Daily Rate by Month

Monthly average daily rates vary between hotel types. Resort Hotels show particularly high average daily rates during July and August.

### Query 3: Market Segment Analysis

Online travel agencies represent the largest booking segment, accounting for 47.32% of all bookings.

### Query 4: Booking Lead Time Analysis

Canceled bookings have longer average lead times than non-canceled bookings for both hotel types.

## Data Quality and Validation

The pipeline validates record counts and data integrity.

| Layer       | Records |
| ----------- | ------: |
| Bronze      | 119,390 |
| Silver      | 119,209 |
| Quarantined |     181 |
| Gold        | 119,209 |

All final record-count reconciliation checks passed.

## Project Structure

```text
assign1/
├── data/
│   └── raw/
│       ├── H1.csv
│       └── H2.csv
├── assign1.ipynb
└── README.md
```

The pipeline also creates local DuckDB database files and DuckLake storage.

## How to Run

1. Install Python and the required packages.
2. Open `assign1.ipynb` in VS Code.
3. Select a Python kernel with the required dependencies installed.
4. Ensure `H1.csv` and `H2.csv` are available in `data/raw/`.
5. Run all notebook cells in order.
6. Review the validation results and analytical visualizations.

## Conclusion

This project demonstrates how a Medallion Architecture pipeline can transform raw hotel booking data into structured analytical information. DuckDB and DuckLake support data ingestion, cleaning, dimensional modeling, and business analysis.

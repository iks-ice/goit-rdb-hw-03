# Homework 3: NYC Yellow Taxi Data Analysis

## Project Overview

This project demonstrates a reproducible ETL pipeline and exploratory data analysis using the NYC Yellow Taxi dataset, PostgreSQL, SQLAlchemy, Pandas, and Google Colab.

## Dataset

- Source: [NYC TLC Trip Record Data](https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page)
- File: `yellow_tripdata_2024-01.parquet`
- Selected records: 100,000
- Selected columns: 11
- Cleaned records: 99,999

The project uses the first 100,000 records from the January 2024 dataset, not a random sample of the full month.

## Technologies

- Python
- Pandas and PyArrow
- PostgreSQL 16
- SQLAlchemy
- psycopg 3
- pixeltable-pgserver
- Google Colab

## ETL Pipeline

1. Download the NYC Yellow Taxi Parquet dataset.
2. Select 11 columns and export 100,000 records to CSV.
3. Create a PostgreSQL staging table with TEXT columns.
4. Load the CSV using `COPY FROM STDIN`.
5. Transform records using `INSERT INTO ... SELECT`.
6. Apply data types, primary key, NOT NULL, and CHECK constraints.
7. Validate data quality and perform exploratory SQL analysis.

## Data Quality

- 100,000 staging records
- 99,999 cleaned records
- 1 rejected record with invalid trip duration
- 0 duplicate groups
- 1,047 trips with zero passengers
- 1,811 trips with zero distance
- 1,586 trips with negative total amounts

Potential anomalies were retained for further investigation.

## Exploratory Data Analysis

The project includes descriptive statistics, categorical distributions, outlier detection, and 10 SQL queries addressing business questions.

Key findings:

- Average trip distance: 4.20 miles
- Median trip distance: 2.00 miles
- Average total amount: $30.04
- Average trip duration: 16.45 minutes
- Most common payment type: 1

## How to Run

1. Open the project notebook in Google Colab.
2. Select **Runtime → Run all**.
3. The notebook installs dependencies, starts an embedded PostgreSQL server, downloads the dataset, builds the tables, and executes the analysis.

No external PostgreSQL server or local database credentials are required.

## Limitations

The analysis uses the first 100,000 records from the source file. Results should not be interpreted as representative of all January 2024 taxi trips.

## Conclusion

The project demonstrates data ingestion, SQL transformations, integrity constraints, data quality validation, and reproducible exploratory analysis using PostgreSQL.
# Amazon Products Data Pipeline

End-to-end data engineering pipeline built with PySpark and Databricks
implementing the Medallion Architecture.

## Architecture

## Tools
- PySpark
- Databricks Community Edition
- Unity Catalog
- Parquet

## Pipeline Steps
1. Raw CSV ingested into Bronze Volume
2. Silver - cleaned corrupted currency symbols, fixed numeric types,
   handled nulls, split category hierarchy
3. Gold - aggregated product metrics by category
4. SQL - queried Gold table via Databricks SQL Editor

## Dataset
Amazon Products dataset - 1465 rows, 16 columns
Real-world data quality issues: corrupted encoding, comma-separated
numbers, pipe-delimited categories, malformed rows

## Key Transformations
- regexp_replace to clean currency symbols and special characters
- cast to convert string columns to float/integer
- dropna to remove unrecoverable corrupted rows
- split to extract main_category and sub_category
- groupBy + agg for Gold layer business metrics

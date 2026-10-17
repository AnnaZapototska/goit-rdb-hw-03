# GoIT RDB — Homework 2: Data Loading and SQL DQL

## Overview

This project explores the UCI Bank Marketing dataset using PostgreSQL and SQL. The goal is to practice data loading, data cleaning, data quality validation, and exploratory data analysis (EDA) through SQL queries.

## Dataset

- **Source:** [UCI Machine Learning Repository — Bank Marketing](https://archive.ics.uci.edu/dataset/222/bank+marketing)
- **Records:** 45,211
- **Original features:** 16
- **Target variable:** `y` — whether the client subscribed to a term deposit.

The dataset contains information about clients, their financial situation, previous marketing campaign outcomes, and contact details.

## Tools and Technologies

- Python
- Google Colab
- PostgreSQL
- SQLAlchemy
- pandas
- `pgserver`
- UCI ML Repository (`ucimlrepo`)

## Project Workflow

1. Download the Bank Marketing dataset.
2. Export the data to CSV.
3. Create a raw staging table in PostgreSQL.
4. Load CSV data using PostgreSQL `COPY`.
5. Create a typed table and transform raw values using `INSERT INTO ... SELECT`.
6. Validate row counts, duplicates, missing values, categorical values, and numeric ranges.
7. Perform exploratory data analysis using 10 SQL business queries.
8. Document findings and reflect on data quality and potential data leakage.

## Database Tables

- `hw3_bank_staging` — raw data loaded from CSV, with source columns stored as text.
- `hw3_bank_clean` — transformed data with appropriate data types, Boolean fields, constraints, and a generated primary key.

Missing categorical values are preserved as SQL `NULL`. The special value `pdays = -1` is retained to represent the absence of previous contact.

## SQL Analysis

The analysis explores subscription rates in relation to:

- Month of contact
- Contact type
- Housing loan status
- Client balance
- Age group
- Number of contacts during the campaign
- Previous campaign outcome
- Credit default status
- Call duration

The notebook also includes data quality checks and a short reflection on the results.

## How to Run

1. Open the notebook in Google Colab.
2. Install or import the required dependencies.
3. Start the PostgreSQL server using `pgserver`.
4. Download the dataset and generate the CSV file.
5. Execute the notebook cells in order to create the tables, load the data, run validation checks, and perform the SQL analysis.

The notebook creates its database tables and data during execution.

## Key Findings

- The overall subscription rate is approximately **11.70%**.
- Subscription rates vary considerably across months and customer groups.
- Clients with a successful previous campaign outcome have a higher observed subscription rate.
- Call duration is strongly associated with the subscription outcome, but it may cause target leakage if used to predict subscription before a call begins.

These findings describe associations in the dataset and do not establish causal relationships.

## Limitations

The analysis is exploratory. Missing values are retained as `NULL`, and the results depend on the available dataset and selected grouping criteria. Further analysis would be needed before using these findings for business decisions or predictive modeling.

## Author

GoIT RDB course — Homework 2.

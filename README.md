# Applied-Case-Study-II-Automated-Payment-Reconciliation

### 📊 Notebook Summary: Automated Payment Reconciliation

#### 📌 Overview
This notebook is a structured python-based assignment focusing on **Automated Payment Reconciliation** using the `pandas` and `numpy` libraries. It simulates internal ledgers and payment gateway logs to detect discrepancies, analyze transactions, and compute a data health metric.

---

#### 📂 Notebook Structure & Progress

| Section / Problem | Title | Status / Output Summary | Key Concepts Used |
| :--- | :--- | :--- | :--- |
| **Section 0** | Setup & Data Generation | **Completed** (100 internal transactions, 97 gateway transactions) | `pandas.DataFrame`, `numpy.random`, Synthetic Data Generation |
| **Problem 1** | Explore the Data | **Completed** | `.head()`, `len()`, `.columns` |
| **Problem 2** | Payment Method Analysis | **Completed** (Highest total value: UPI with ₹81,948) | `.value_counts()`, `.groupby()`, `.idxmax()` |
| **Problem 3** | Find Transactions Missing in Gateway | **Completed** (5 transactions missing, ₹7,795 at risk) | Python `set` subtraction (`-`), `.isin()` |
| **Problem 4** | Find Transactions Missing in Ledger | **Completed** (2 transactions missing: TXN99901, TXN99902, ₹4,598 total) | Reverse set subtraction, Boolean filtering |
| **Problem 5** | Find Amount Mismatches | **Completed** (3 mismatches found, totaling ₹250 discrepancy) | Set intersection (`&`), `pd.merge()` |
| **Problem 6** | Find Status Mismatches | **Completed** (2 status mismatches: `SUCCESS` vs `FAILED`) | Column comparisons, filtering |
| **Problem 7** | Build Final Reconciliation Report | **Completed** (10 total issues consolidated and sorted by impact) | `pd.concat()`, sorting by absolute values with `.abs()` |
| **Problem 8** | High-Value Issue Filter | **Completed** (Filtered issues with absolute difference > ₹1,000) | Advanced filtering, Sorting |
| **Problem 9** | Day-wise Discrepancy Analysis | ⏳ *Pending Implementation* | Datetime operations (`.dt.date`), Groupby aggregation |
| **Problem 10**| Reconciliation Health Score | ⏳ *Pending Implementation* | Logical operations (`&`), percentage metrics |

Assignment: Fintech APIs and Data Ingestion
Overview

This notebook is a comprehensive, hands-on assignment focused on working with APIs, parsing JSON payloads, cleaning datasets, and constructing standard ETL (Extract, Transform, Load) pipelines in Python.

Notebook Summary
Setup
Imports standard data-engineering libraries: requests, json, and pandas.
Problems
Problem 1: Basic API Call
Implements API GET requests to query user profiles.
Problem 2: Nested JSON Navigation
Extracts attributes from deeply nested JSON schemas.
Problem 3: Query Parameter Queries
Applies server-side filters to restrict API results.
Problem 4: JSON-to-DataFrame Flattening
Normalizes nested records using pandas.json_normalize().
Problem 5: Data Standardization
Renames columns to maintain consistent naming conventions.
Problem 6: Iterating Collections
Extracts specific elements from structured lists.
Problem 7: Temporal Formatting
Converts Unix epoch timestamps into structured datetime64 data types.
Problem 8: Resilient Exceptions
Implements structured try/except blocks to handle errors during external API requests.
Problem 9: Grouping and Aggregations
Uses groupby().size() to calculate grouped summaries.
Problem 10: Merging Pipelines
Integrates data from multiple sources using relational pandas.merge() operations.
Bonus Task
User TODO Completion Rates
Includes a placeholder for calculating user TODO completion rates.
Learning Objectives

By completing this assignment, students will learn how to:

Make API requests and retrieve data from external sources.
Navigate and extract information from nested JSON structures.
Filter, flatten, clean, and standardize datasets.
Convert timestamps into appropriate datetime formats.
Handle API errors using exception handling.
Perform grouping, aggregation, and data merging operations.
Build structured ETL pipelines using Python and pandas.

---

#### 🛠️ Key Takeaways
- **Reconciliation Workflow**: Employs Python sets to perform structural audits (finding missing rows in either source) and merges/joins to audit differences in specific attributes (amounts and statuses).
- **High Financial Impact Audits**: Sorts discrepancies by absolute value to prioritize high-value issues for operational teams.

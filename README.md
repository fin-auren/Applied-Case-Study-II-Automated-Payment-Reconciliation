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

---

#### 🛠️ Key Takeaways
- **Reconciliation Workflow**: Employs Python sets to perform structural audits (finding missing rows in either source) and merges/joins to audit differences in specific attributes (amounts and statuses).
- **High Financial Impact Audits**: Sorts discrepancies by absolute value to prioritize high-value issues for operational teams.

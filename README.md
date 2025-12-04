# 🛡️ Automated Internal Audit System (Expense Fraud Detection)

![Status](https://img.shields.io/badge/Status-Completed-success)
![Python](https://img.shields.io/badge/Python-3.x-blue)
![Focus](https://img.shields.io/badge/Focus-Internal%20Audit%20%7C%20Automation-green)

> **⚠️ DISCLAIMER: DATA PRIVACY & COMPLIANCE**
> * This repository demonstrates the **technical architecture and logic** of the Automated Audit Engine deployed in a real-world corporate environment.
> * Due to strict **Non-Disclosure Agreements (NDA)** and data privacy regulations, the actual production dataset cannot be shared publicly.
> * Therefore, the input data (`Raw_Expense_Data.csv`) in this project has been **synthesized using the `Faker` library** to simulate real-world fraud patterns (Structuring, Duplicate Claims, Weekend Violations) for demonstration purposes only.

---

## 📋 Executive Summary

In modern corporate governance, manual auditing of T&E (Travel & Expense) reports is inefficient and prone to errors. This project replaces manual sampling with an **End-to-End Python Audit Engine** capable of reviewing **100% of transactions**.

**Key Achievement:**
* **Speed:** Reduced audit cycle from 3 days to < 10 seconds.
* **Coverage:** Increased risk detection coverage from 10% (sampling) to 100% (population).
* **Output:** Auto-generated interactive Excel Dashboards and PDF Executive Reports.

---

## 🔍 Audit Logic (How it works)

The engine applies forensic data analytics rules to detect:

1.  **🚫 Weekend Violations:** Identifies "Meals" or "Entertainment" expenses incurred on Saturday/Sunday.
2.  **💸 Structuring (Split POs):** Detects attempts to bypass approval limits (e.g., splitting a $10k invoice into two $5k transactions on the same day).
3.  **🔄 Duplicate Claims:** Flags double-dipping where the same amount is claimed multiple times across different reports.

---

## 💻 How to Run This Project

This project is separated into **Data Generation** (Internal Simulation) and **Audit Engine** (Production Logic).

### Step 1: Generate Simulation Data (Optional)
If you don't have your own dataset, run the generator to create a dummy `Raw_Expense_Data.csv`.
```bash
python data_generator.py

### Step 2: Run the Audit Engine
This script reads the CSV, processes the audit rules, and outputs the reports.
```bash
python audit_engine.py

### Step 3: Check Output
📄 Audit_Report_Final_Professional.pdf: Executive summary for management.

📊 Audit_Report_Dashboard.xlsx: Detailed log for field auditors.
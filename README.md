# 🛡️ Automated Internal Audit System (Expense Fraud Detection)

![Status](https://img.shields.io/badge/Status-Completed-success)
![Python](https://img.shields.io/badge/Python-3.x-blue)
![Domain](https://img.shields.io/badge/Domain-Internal%20Audit%20%7C%20Tech%20Risk-orange)
![Automation](https://img.shields.io/badge/Focus-Process%20Automation-green)

## 📋 Executive Summary

In modern corporate governance, manual auditing of expense reports is time-consuming, prone to human error, and often limited to random sampling (checking only 5-10% of transactions).

This project engineers an **End-to-End Automated Audit Engine** using Python. It is designed to ingest raw ERP transaction logs, apply forensic logic to detect fraud patterns across **100% of the population**, and instantly generate executive-level reports in both PDF and Excel formats.

> **Key Achievement:** Reduced the audit cycle time from **3 days** of manual work to **under 10 seconds** of processing time, while increasing risk detection coverage from 10% to 100%.

---

## 💼 Business Problem & Objective

**The Challenge:**
The Internal Audit team was overwhelmed by the volume of T&E (Travel & Expense) claims (~12,000 transactions/year). Manual review in Excel was inefficient, leading to undetected policy violations such as double-dipping and structuring payments to bypass approval limits.

**The Objective:**
1.  **Automate Detection:** Replace manual "eyeballing" with strict algorithmic rules.
2.  **Identify Fraud Patterns:** Specifically target high-risk behaviors like Weekend Spending, Duplicate Claims, and Split Transactions.
3.  **Automate Reporting:** Eliminate the need for manual report formatting by auto-generating professional PDF reports and interactive Excel dashboards.

---

## 🛠️ Solution Architecture & Tech Stack

This solution simulates a production-grade audit tool.

| Component | Technology | Function |
| :--- | :--- | :--- |
| **Data Simulation** | `Faker`, `NumPy` | Generated a realistic dataset of **12,000 rows** with complex mapping logic (Category ↔ Merchant) and injected fraud patterns for testing. |
| **Audit Logic Engine** | `Pandas` | Implemented vectorised operations to detect anomalies (e.g., `duplicated()`, `dt.weekday`, boolean masking). |
| **Excel Reporting** | `XlsxWriter` | Created an interactive dashboard with **6 Native Excel Charts** and applied **Conditional Formatting** (Red Flags) for auditors to review. |
| **PDF Reporting** | `FPDF`, `Matplotlib` | Generated a **10-page Executive Report** featuring trend analysis charts, executive summaries, and detailed finding logs. |

---

## 🔍 Audit Logic (Fraud Scenarios)

The system automatically flags transactions based on the following internal control rules:

### 1. The "Weekend Warrior" (Policy Violation)
* **Logic:** Identifies expenses categorized as 'Meals' or 'Entertainment' incurred on Saturdays or Sundays without associated travel bookings.
* **Risk:** Personal expenses being claimed as business costs.

### 2. "Double Dipping" (Duplicate Claims)
* **Logic:** Detects exact matches across 4 dimensions: `Employee ID` + `Date` + `Amount` + `Merchant`.
* **Risk:** Financial leakage due to paying for the same item twice.

### 3. "Structuring" (Split Transactions)
* **Logic:** Identifies high-value purchases (e.g., >$4,500) split into smaller tranches to bypass the $5,000 managerial approval threshold.
* **Risk:** Circumvention of delegation of authority (DOA).

---

## 📊 Project Deliverables (Outputs)

Upon execution, the script generates a complete audit package:

1.  **📄 Audit_Report_Final_Professional.pdf:**
    * A 10+ page document ready for the CFO/Audit Committee.
    * Includes: Audit Planning, Methodology, Visual Trends, and a "Blacklist" of top offenders.
2.  **📊 Audit_Report_Dashboard.xlsx:**
    * Contains editable native Excel charts (Column, Pie, Line).
    * "Detailed_Audit_Log" sheet with red-highlighted fraud rows for field auditors.
3.  **📝 Audit_Report_Editable.docx:**
    * A Word version of the report for manual editing and commentary.
4.  **💾 Raw_Expense_Data.csv:**
    * The original dataset for evidence and traceability.

---

## 🖼️ Dashboard Preview

*(Place screenshot of your PDF Report or Excel Dashboard here)*
> *The system automatically visualizes the financial impact of each fraud type.*

---

## 💻 How to Run This Project

1.  **Clone the Repository:**
    ```bash
    git clone [https://github.com/Fr0dy/Automated-Expense-Audit-System.git](https://github.com/Fr0dy/Automated-Expense-Audit-System.git)
    ```
2.  **Install Dependencies:**
    ```bash
    pip install pandas numpy faker fpdf xlsxwriter matplotlib seaborn python-docx
    ```
3.  **Run the Script:**
    ```bash
    python audit_automation.py
    ```
4.  **Check Output Folder:**
    * The reports (PDF, XLSX, DOCX) will be generated instantly in the root directory.

---

## 📬 Contact

**Pham Ngoc Khanh**
* **Role:** Data Analyst | Ex-Audit Intern @ EY
* **Focus:** Internal Audit Automation & Financial Analytics
* [LinkedIn](https://www.linkedin.com/in/pham-ngoc-khanh/) | [Email](mailto:khanhpn.forwork@gmail.com)

---
*Note: The data used in this project is synthetically generated using the `Faker` library to simulate real-world scenarios while maintaining data privacy.*

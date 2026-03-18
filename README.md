# Surgical Instrument Delivery — Operations Analytics

> **Portfolio project** by Kantapit Malee · Data Analyst Transition Portfolio  
> Dataset anonymized: hospital names → `HOSP_XXX`, doctor names → `DR_XXX`, internal IDs masked

---

## Project Overview

This project analyzes **14,128 surgical instrument delivery records** from a medical device distribution company in Thailand, spanning **April 2023 to March 2026**.

The dataset covers the end-to-end logistics workflow: instrument set booking, dispatch, hospital delivery, case usage, and return tracking — across **785 hospitals** in Bangkok (BKK) and upcountry (UPC) regions.

The goal is to surface operational KPIs, identify delivery performance trends, and support data-driven decisions in inventory and logistics management.

---

## Key Findings

| Metric | Value |
|--------|-------|
| Total cases tracked | 14,128 |
| Valid cases (2023–2026) | 12,272 |
| On-time delivery rate | **99.2%** |
| Case utilization rate | **68.6%** |
| Hospitals served | 785 |
| Top brand by volume | Sigma 3.5 (2,442 cases) |
| YoY growth (2023→2025) | +58% avg monthly volume |

---

## Dataset Structure

**File:** `MDC_Surgical_Instrument_Delivery_Anonymized.csv`  
**Rows:** 14,128  **Columns:** 28

| Column | Description | Anonymized? |
|--------|-------------|-------------|
| `helper` | Instrument brand helper category | No |
| `function` | Instrument function type | No |
| `date` | Record entry date | No |
| `area` | Region (BKK / UPC) | No |
| `sales_area` | Sales territory code | Yes → `SALES_XXX` |
| `hospital` | Hospital identifier | Yes → `HOSP_XXX` |
| `doctor` | Surgeon identifier | Yes → `DR_XXX` |
| `brand` | Instrument brand (e.g. Sigma 3.5, Stryker T8) | No |
| `product` | Product/procedure type | No |
| `case_date` | Scheduled surgery date | No |
| `sending_date` | Dispatch date | No |
| `courier` | Logistics provider | No |
| `recipient` | Recipient staff code | Yes → `STAFF_XXX` |
| `case_used` | Case outcome (used / returned / cancelled) | No |
| `status` | Current delivery status | No |
| `status_date` | Status update date | No |
| `remark` | Notes (personal names removed) | Partial |

---

## Analysis Highlights

### 1. Monthly Volume Trend
Case volume grew from ~230/month (mid-2023) to ~430/month (late 2025), representing a **~87% increase** over 2.5 years — indicating strong business growth and increasing operational complexity.

### 2. On-Time Delivery Performance
- **12,174 out of 12,270** trackable cases were dispatched on or before the surgery date
- On-time rate: **99.2%** — a critical KPI for surgical instrument logistics where late delivery means cancelled operations

### 3. Brand Distribution
Top 5 brands account for **79% of all cases**:
1. Sigma 3.5 — 19.9%
2. Sigma Nail — 16.7%
3. Sigma 5.0 — 10.9%
4. Stryker T8 — 9.6%
5. Sigma 2.7/3.5 — 7.7%

### 4. Case Outcome
- **Used:** 68.6% — instrument sets confirmed used in surgery
- **Returned complete:** 22.5% — sets returned without use (surgery rescheduled, etc.)
- **Not used:** 1.3% — sets dispatched but not used
- **Other / unrecorded:** 7.6%

### 5. Regional Split
- **Bangkok (BKK):** 64.4% of cases
- **Upcountry (UPC):** 35.5% of cases

---

## Tools Used

| Tool | Purpose |
|------|---------|
| Python (pandas, csv) | Data cleaning, anonymization, EDA |
| SQL | Dataset design, end-to-end query building |
| Power BI | Operational dashboard (internal use) |
| AI-Assisted Analytics | Prompt engineering for SQL query generation and troubleshooting |
| GitHub | Version control and portfolio hosting |

---

## How to Use

```bash
# Clone the repo
git clone https://github.com/kantapit-malee/surgical-instrument-delivery-analytics

# Install dependencies (if running Python analysis)
pip install pandas matplotlib

# Open the CSV
import pandas as pd
df = pd.read_csv('MDC_Surgical_Instrument_Delivery_Anonymized.csv', encoding='utf-8-sig')
df.head()
```

---

## Files

```
surgical-instrument-delivery-analytics/
├── MDC_Surgical_Instrument_Delivery_Anonymized.csv   # Main dataset (anonymized)
├── README.md                                          # This file
└── analysis/
    └── (Power BI / Python notebooks — coming soon)
```

---

## Privacy & Ethics

All personally identifiable information has been removed or anonymized:
- Hospital names → `HOSP_001` ... `HOSP_778`
- Doctor/surgeon names → `DR_001` ... `DR_2245`
- Sales representative codes → `SALES_001` ... `SALES_036`
- Internal reference IDs → masked (`REF_MASKED`)
- Remarks field → personal names removed

No patient data is included in this dataset. All records represent instrument set logistics only.

---

## About

**Kantapit Malee**  
Inventory Control & Data Analyst  
MDC Thailand · Bangkok  

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=flat&logo=linkedin)](https://www.linkedin.com/in/kantapit-malee-928b18268)

> Transitioning from logistics operations to data analytics, leveraging 5+ years of hands-on experience with inventory systems, SQL datasets, and BI dashboards.

# Sales Data Cleaning and Analysis Project

## Project Overview
This project demonstrates the complete process of transforming a messy sales dataset into a clean, analysis-ready dataset using Microsoft Excel and Power Query. 

The dataset contained 2,000 records and suffered from common data quality issues such as: missing values, duplicate records, invalid region names, inconsistent formatting, data entry errors, and mixed date formats. The primary goal was to build a repeatable, scalable data-cleaning workflow while generating meaningful business insights from the finalized data.

## Tools Used
* **Microsoft Excel** (Core Analysis, Pivot Tables, Pivot Charts, Dashboarding)
* **Power Query** (ETL - Extract, Transform, Load processes)
* **Data Validation & Named Ranges** (Data entry quality controls)

## Data Cleaning Process

### 1. Data Assessment
The raw dataset was rigorously reviewed to identify:
* Missing values in numeric columns (e.g., Amount)
* Exact duplicate entries skewing transaction counts
* Formatting inconsistencies (e.g., text-as-numbers, mixed date systems)
* Invalid categorical entries (e.g., typos like "Eeast" and wildcards like "???")

### 2. Data Transformation
To address the discovered anomalies, a systematic transformation workflow was implemented:
* **Find and Replace (`Ctrl + H`):** Cleared out stubborn data entry artifacts. Escaped literal wildcard characters (like targeting `???` string sequences via `~?~?~?`) to prevent accidental bulk-deletion of clean records.
* **Remove Duplicates:** Scanned transactional records to strip out exact redundant rows, establishing a strict baseline of unique operational inputs.
* **Handling Missing Values:** Evaluated missing metrics strategically. Handled blank numerical fields securely via Power Query or targeted bulk-fills (`Ctrl + G` > Blanks) to preserve calculation integrity and protect mathematical averages.
* **Standardizing Text Fields & Dates:** Enforced universal case matching and converted broken text strings into formal Date and Currency data types.
* **Power Query Recipes:** Centralized these cleaning steps into an automated script pipeline. This ensures that any new messy raw data appended to the source table can be instantly cleaned by executing a simple dataset **Refresh**.

### 3. Data Quality Controls
To ensure the dataset remains clean over time and to bulletproof future manual data entry, proactive governance structures were set up:
* **Data Validation Lists:** Enforced strict dropdown restrictions on critical input columns (Region, Product, Status), transforming standard cells into controlled fields with custom input messages and error alerts.
* **Named Ranges:** Abstracted configuration lists into cleanly referenced variables (e.g., `=RegionList`), making validation models highly dynamic.
* **Circle Invalid Data:** Configured post-entry auditing arrays to draw immediate visual indicators around legacy errors or non-conforming entries.
* **System Protection & Visibility Management:** Separated the operational data entry layer from the validation reference layer. Source lists were isolated onto a hidden sheet, which was set to an advanced structural visibility state (`xlSheetVeryHidden`) via the VBA Editor (`Alt + F11`) and password-protected to prevent unauthorized modification.

## Key Business Insights

### Sales Performance
* **Total Sales:** \$324,400
* **Total Orders:** 1,417
* **Average Order Value (AOV):** \$228.93

### Product Analysis
* **Top Performer:** *Widget B* generated the highest raw revenue share.
* Operational metrics showed significant variance across secondary categories, highlighting product optimization opportunities.

### Regional Analysis
* **Top Region:** The *East Region* recorded the highest overall sales numbers.
* Geographic granular grouping showed clear breakout performance at the state level, identifying key expansion opportunities.

### Order Status Analysis
* **Completed Orders:** Contributed the largest percentage share of overall revenue.
* The processing funnel identified minor operational bottlenecks within pending and in-transit order statuses.

## Interactive Dashboard
The fully transformed data table serves as the single source of truth for an interactive, dynamic Excel Dashboard. 

### Features Included:
* Main Sales KPI summary metrics
* Categorized Product Performance charts
* Spatial Regional Sales Distribution breakdowns
* Functional Order Status breakdowns
* **Interactive Slicers:** Allows stakeholders to instantly segment visual components by time, region, or product lines with a single click.


## Lessons Learned
This project underscores the core data engineering tenet: *reliable business intelligence requires strict data governance*. Analytics are entirely dependent on the structural integrity of underlying records. By chaining automated extract-transform-load (ETL) tools like Power Query together with preventive measures like Sheet Protection and Data Validation, organizations drastically reduce manual rework while establishing data trust.

***

### Author
**Jonathan Ogana** *Data Analytics | Excel Expert | Power Query Specialist | Dashboard Developer*

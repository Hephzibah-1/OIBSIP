# OIBSIP Data Analytics – Level 1

## Task 3: Data Cleaning – Dirty Cafe Sales Dataset

### Project Overview

This project focuses on cleaning and preparing a deliberately messy cafe sales dataset containing 10,000 transaction records. The objective was to transform raw, inconsistent data into a clean and analysis-ready dataset while documenting and justifying every cleaning decision.

The project involved identifying missing values, handling hidden missing-value indicators, correcting data types, recovering missing numerical values where possible, investigating outliers and preserving incomplete records where deleting them would result in unnecessary data loss.

The emphasis was on maintaining data accuracy and integrity rather than forcing every column to appear complete.

### Project Objectives

- Inspect the dataset and identify data quality issues.
- Detect both actual missing values and hidden missing-value indicators.
- Correct inappropriate data types across numerical, categorical and date columns.
- Recover missing numerical values using verifiable mathematical relationships.
- Handle unrecoverable missing values without introducing misleading information.
- Identify and investigate duplicate records.
- Detect and evaluate outliers using the Interquartile Range (IQR) method.
- Produce a clean, analysis-ready dataset.
- Document and justify every data cleaning decision.

### Dataset Description

The dataset contains 10,000 cafe sales transactions and 8 original columns.

| Column | Description |
|---|---|
| Transaction ID | Unique transaction identifier |
| Item | Name of the purchased cafe item |
| Quantity | Number of items purchased |
| Price Per Unit | Price of one unit |
| Total Spent | Total amount spent per transaction |
| Payment Method | Method used for payment |
| Location | Location of the transaction |
| Transaction Date | Date of the transaction |

**Dataset inspection results:**

- Original records: 10,000
- Original columns: 8
- Missing values: Present across every column except Transaction ID.
- Hidden missing values: `ERROR` and `UNKNOWN` were stored as text rather than recognised as missing values.
- Hidden missing-value indicators: 3,256 cells.
- Data types: All 8 columns were initially stored as text.
- Payment Method had approximately 32% missing values.
- Location had approximately 40% missing values.
- No duplicate rows were identified.
- No impossible numerical values, such as negative quantities, were found.

### Tools and Technologies

- **Python:** Primary programming language.
- **Google Colab:** Cloud-based development environment.
- **Pandas:** Data inspection, cleaning, manipulation and analysis.
- **NumPy:** Numerical operations and missing-value handling.
- **Jupyter Notebook:** Documentation of the cleaning process, code and outputs.

### Project Methodology

**1. Data Loading and Inspection**

- Imported the original Dirty Cafe Sales dataset into Google Colab.
- Examined the first few records, dataset dimensions and column information.
- Investigated missing values across all columns.
- Identified inconsistencies in data types and hidden missing-value indicators.
- Examined the extent of missing information in Payment Method and Location.

**2. Handling Hidden Missing Values**

- Identified `ERROR` and `UNKNOWN` as invalid text entries representing missing information.
- Replaced these values with proper `NaN` values.
- This allowed Pandas to recognise and handle them as missing data rather than treating them as valid categories.

**3. Data Type Correction**

- Converted Quantity, Price Per Unit and Total Spent into numerical data types.
- Converted Transaction Date into datetime format.
- Converted Transaction ID into string format because it serves as an identifier rather than a numerical measurement.
- Ensured all columns had appropriate data types for subsequent analysis.

**4. Recovering Missing Numerical Values**

- Used the mathematical relationship:

  `Total Spent = Quantity × Price Per Unit`

- Recovered missing numerical values where the remaining two values were available.
- Filled missing unit prices using the fixed price associated with each item.
- Recovered some missing item names using prices that uniquely corresponded to specific items in the dataset.
- Avoided guessing values where sufficient information was unavailable.

**5. Handling Unrecoverable Records**

- Removed 26 rows (0.26% of the original dataset) where essential numerical values could not be reliably recovered.
- Preserved the remaining valid transactions.
- Labelled missing Item, Payment Method and Location entries as `Not Recorded`.
- Avoided deleting valid transactions or using the mode to fill categorical values, as this would introduce unsupported information.

**6. Handling Missing Transaction Dates**

- Identified 460 records with missing transaction dates.
- Left these dates blank because transaction IDs did not follow a chronological sequence.
- Avoided assigning estimated dates that could distort time-based analysis.
- Retained these transactions for non-date-based analysis.

**7. Duplicate Detection**

- Checked the dataset for duplicate records.
- Confirmed that no duplicate rows were found.
- Verified that all Transaction IDs were unique.

**8. Outlier Detection**

- Applied the Interquartile Range (IQR) method to investigate potential outliers in Total Spent.
- Identified 268 potential outliers.
- Investigated the flagged transactions and established that they were valid orders involving five Salads at 5.00 each.
- Retained the outliers because they represented legitimate transactions rather than data entry errors.

### Key Findings

**1. Data Quality Issues**

- The original dataset contained 10,000 rows and 8 columns.
- Missing values were present in every column except Transaction ID.
- A total of 3,256 cells contained hidden missing-value indicators (`ERROR` and `UNKNOWN`).
- All 8 columns were initially stored as text, requiring appropriate type conversions.

**2. Missing Data Recovery**

- Recovered missing numerical values using the relationship between quantity, unit price and total spent.
- Used item-specific pricing relationships to recover some missing prices and item names.
- Removed only 26 records where essential numerical information could not be recovered.
- Preserved valid transactions with incomplete categorical information by assigning `Not Recorded`.

**3. Before and After Comparison**

| Metric | Before Cleaning | After Cleaning |
|---|---:|---:|
| Total Rows | 10,000 | 9,974 |
| Blank (NaN) Cells | 6,826 | 460 |
| ERROR/UNKNOWN Cells | 3,256 | 0 |
| Not Recorded Labels | 0 | 7,594 |
| Duplicate Rows | 0 | 0 |
| Columns with Appropriate Data Types | 4 of 8 | 8 of 8 |

**4. Outlier Investigation**

- Identified 268 potential outliers in Total Spent using the IQR method.
- Confirmed that all flagged transactions were valid orders.
- Retained the outliers to preserve genuine sales information.

**5. Final Dataset**

- Final dataset size: 9,974 rows and 8 columns.
- All columns were converted to appropriate data types.
- Hidden missing-value indicators were eliminated.
- Only 460 blank cells remained, all relating to unrecoverable transaction dates.
- The cleaned dataset was prepared for subsequent analysis.

### Data Cleaning Decisions and Justifications

| Cleaning Action | Justification |
|---|---|
| Replaced ERROR and UNKNOWN with NaN | These were invalid entries representing missing information. |
| Corrected data types | Appropriate types support calculations, date analysis and accurate identification. |
| Recovered numerical values mathematically | Existing relationships allowed values to be calculated without guessing. |
| Recovered prices and some item names | Each item had a fixed price in the dataset, allowing certain missing values to be identified reliably. |
| Removed 26 unrecoverable rows | Essential numerical information was unavailable, making reliable recovery impossible. |
| Replaced missing categorical values with Not Recorded | Preserved valid transactions without inventing categorical information. |
| Left 460 missing dates blank | Transaction IDs could not reliably establish transaction dates. |
| Checked duplicates | Confirmed that no duplicate records required removal. |
| Retained valid outliers | Flagged transactions represented legitimate sales rather than errors. |

### Limitations

- Missing Payment Method, Location and Item values could not all be recovered, so analyses involving these columns will include a `Not Recorded` category.
- The 460 records without transaction dates cannot be included in date-based analysis.
- The dataset does not provide additional information that could reliably recover all missing categorical values.
- Although the dataset was cleaned, some missing information remains. This was intentional to preserve data integrity rather than introduce assumptions.

### Conclusion

The data cleaning process transformed a deliberately inconsistent cafe sales dataset into a more reliable and analysis-ready dataset.

Through systematic inspection, missing-value handling, data type correction, mathematical recovery of numerical values, duplicate checks and outlier investigation, the dataset was reduced from 10,000 to 9,974 records.

An important lesson from this project is that data cleaning is not simply about eliminating missing values or making a dataset appear complete. It requires understanding the nature of each problem, investigating whether information can be recovered and making evidence-based decisions about what should be retained, corrected or removed.

Overall, the project strengthened my understanding of data quality management and the importance of maintaining accuracy and integrity throughout the data preparation process.

### Project Information

- **Programme:** Oasis Infobyte Internship (OIBSIP)
- **Domain:** Data Analytics
- **Level:** 1
- **Task:** 3 – Cleaning Data
- **Project:** Dirty Cafe Sales
- **Environment:** Google Colab
- **Language:** Python

**Author:** Hephzibah Ajala

**LinkedIn:** [Hephzibah Ajala](https://www.linkedin.com/in/hephzibah-ajala-a21a0135a/)

**GitHub:** [Hephzibah-1](https://github.com/Hephzibah-1)

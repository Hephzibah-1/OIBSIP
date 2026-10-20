# Data Cleaning: Dirty Cafe Sales

**Oasis Infobyte Internship | Data Analytics Track | Level 1, Task 3: Cleaning Data**

## Objective
Take a deliberately messy cafe sales dataset (10,000 rows) and turn it into a clean, analysis-ready dataset, documenting and justifying every cleaning decision.

## Dataset
- **Source:** "Dirty Cafe Sales" dataset from Kaggle
- **Size:** 10,000 rows, 8 columns
- **Columns:** Transaction ID, Item, Quantity, Price Per Unit, Total Spent, Payment Method, Location, Transaction Date

## Tools Used
- Python
- pandas and numpy
- Jupyter Notebook (Google Colab)

## Data Quality Problems Found
- Missing values in every column except Transaction ID
- Hidden missing values: the words `ERROR` and `UNKNOWN` were stored as if they were real data (3,256 cells)
- Every column was stored as text, including numbers and dates
- Payment Method (about 32%) and Location (about 40%) were missing for a large share of rows
- No duplicate rows and no impossible values (for example, negative quantities)

## Cleaning Steps and Decisions

| Step | Action | Why |
|---|---|---|
| 1 | Converted `ERROR` and `UNKNOWN` to true blanks (NaN) | They are not real values, and pandas could not detect them as missing |
| 2 | Converted Quantity, Price Per Unit and Total Spent to numbers, Transaction Date to datetime, and Transaction ID to string | Correct types allow calculations, date analysis and unambiguous identifiers |
| 3 | Recovered missing numbers using Total Spent = Quantity × Price Per Unit | The values could be calculated, so nothing was guessed |
| 4 | Filled missing prices from each item's fixed price, and recovered some missing items from prices that belong to only one item | Every item has exactly one price in this dataset |
| 5 | Removed 26 rows (0.26%) where the numbers could not be recovered | Too few to affect results, and imputing sales figures would invent sales that never happened |
| 6 | Labelled missing Item, Payment Method and Location as "Not Recorded" | Deleting rows would discard valid sales, and filling with the most common value would invent data |
| 7 | Left 460 missing dates blank | Transaction IDs are not in date order, so dates cannot be inferred, and a single filled date would distort trends |
| 8 | Checked for duplicates | None found; all Transaction IDs are unique |
| 9 | Checked outliers using the IQR method | 268 outliers in Total Spent, all valid orders of 5 Salads at 5.00 each, so they were retained |

## Before vs. After

| Metric | Before | After |
|---|---|---|
| Rows | 10,000 | 9,974 |
| Blank (NaN) cells | 6,826 | 460 |
| ERROR/UNKNOWN cells | 3,256 | 0 |
| "Not Recorded" labels | 0 | 7,594 |
| Duplicate rows | 0 | 0 |
| Columns with correct data type | 4 of 8 | 8 of 8 |

## Repository Contents
- `OIBSIP_DataAnalytics_Level_1_Task_3_CleaningData.ipynb`: full notebook with code, outputs and written explanations
- `dirty_cafe_sales.csv`: original raw data
- `cleaned_cafe_sales.csv`: cleaned dataset
- `screenshots/`: key outputs (data quality report, before-vs-after table, final data types)

## How to Run
1. Upload `dirty_cafe_sales.csv` to your Google Drive (My Drive).
2. Open the notebook in Google Colab.
3. Click Runtime, then Run all, and allow Drive access when prompted.
4. The cleaned file is saved to your Drive as `cleaned_cafe_sales.csv`.

## Limitations
- Missing Payment Method, Location and Item values could not be recovered, so analyses on these columns will include a "Not Recorded" group.
- The 460 rows without a date are excluded from any date-based analysis, but remain in revenue totals.

## Key Learnings
The project deepened my understanding of data cleaning and emphasized the importance of thorough investigation before handling blank columns or cells. It also reinforced a key principle: when missing data cannot be recovered through further investigation, maintaining accuracy is more valuable than presenting a seemingly complete data.

## Author
Hephzibah Ajala
Data Analytics Intern, Oasis Infobyte
www.linkedin.com/in/hephzibah-ajala-a21a0135a | https://github.com/Hephzibah-1

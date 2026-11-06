# OIBSIP Data Analytics – Level 1
## Task 1: Exploratory Data Analysis (EDA) on Retail Sales Data

### Project Overview
This project focuses on performing Exploratory Data Analysis (EDA) on a retail sales dataset to uncover meaningful insights into sales performance, customer demographics, product categories, pricing patterns and purchasing behaviour.

The analysis involved inspecting, cleaning and preparing the dataset, conducting descriptive and statistical analysis, identifying trends, and creating visualisations to support data-driven business recommendations.

### Project Objectives
- Understand the structure and quality of the retail sales dataset.
- Examine sales performance across different months and quarters.
- Analyse customer demographics, including age and gender.
- Evaluate revenue and sales volume across product categories and price tiers.
- Identify relationships between numerical variables through correlation analysis.
- Explore differences in product category preferences across age groups.
- Derive actionable business insights and recommendations.

### Dataset Description
The dataset contains 1,000 retail transactions and 9 original columns.

| Column | Description |
|---|---|
| Transaction ID | Unique transaction identifier |
| Date | Date of transaction |
| Customer ID | Unique customer identifier |
| Gender | Customer gender |
| Age | Customer age |
| Product Category | Category of purchased product |
| Quantity | Number of units purchased |
| Price per Unit | Price of one unit |
| Total Amount | Total transaction value |

**Dataset inspection results:**
- Total records: 1,000
- Original columns: 9
- Missing values: 0
- Data types: 5 integer columns and 4 object columns
- Date column converted from object to datetime for time-series analysis.
- Additional Month, Quarter and Age Group features were created.

### Tools and Technologies
- **Python:** Primary programming language.
- **Google Colab:** Cloud-based development environment.
- **Pandas:** Data loading, manipulation and analysis.
- **NumPy:** Numerical operations.
- **Matplotlib:** Data visualisation.
- **Seaborn:** Statistical visualisation.

### Project Methodology

**1. Data Loading and Inspection**
- Imported the dataset into Google Colab.
- Examined the first few records, dataset dimensions and data types.
- Checked for missing values and duplicates.
- Identified the need to convert the Date column into datetime format.

**2. Data Preparation**
- Converted the Date column to datetime.
- Extracted Month and Quarter for time-series analysis.
- Created Age Group categories for demographic analysis.

**3. Descriptive Statistics**
- Calculated mean, median, mode and standard deviation for numerical variables.
- Examined the distribution of customer ages, quantities, unit prices and transaction amounts.

**4. Time-Series Analysis**
- Analysed monthly and quarterly sales trends.
- Identified the strongest and weakest sales periods.
- Excluded two January 2024 transactions from the 2023 trend analysis to maintain a consistent reporting period.

**5. Customer Demographic Analysis**
- Examined customer distribution across age groups.
- Analysed gender distribution and spending patterns.
- Compared revenue contributions across age groups.

**6. Product and Pricing Analysis**
- Compared revenue, units sold, transaction counts and average order values across product categories.
- Analysed five price tiers to identify their contributions to sales volume and revenue.

**7. Correlation Analysis**
- Examined relationships between age, quantity, price per unit and total amount.
- Excluded Transaction ID because it is an identifier rather than a meaningful numerical measure.

**8. Additional Analysis**
- Created an age-group and product-category comparison using a pivot table and heatmap to identify differences in customer preferences.

### Key Findings

**1. Sales Performance**
- May recorded the highest monthly sales at approximately 53,150.
- September recorded the lowest monthly sales at approximately 23,620.
- Q4 was the strongest quarter, generating approximately 126,190.
- Q3 was the weakest quarter, with approximately 96,045 in sales.

**2. Customer Demographics**
- Female customers accounted for approximately 51% of transactions, while male customers accounted for 49%.
- The 46–55 age group was the largest, with 229 customers.
- This age group also generated the highest revenue, approximately 100,690.
- Average spending per transaction was nearly identical across genders.

**3. Product Category Performance**
- Electronics generated approximately 156,905 in revenue.
- Clothing followed closely with approximately 155,580.
- Beauty generated the lowest overall category revenue, despite having the highest average order value of approximately 467.48.

**4. Pricing and Revenue Patterns**
- The 500 price tier accounted for approximately 54% of total revenue.
- The 300 and 500 price tiers combined contributed approximately 88% of revenue.
- Units sold were relatively similar across the five price tiers.
- This suggests that higher-priced purchases contribute disproportionately to revenue.

**5. Correlation Analysis**
- Price per Unit had a strong positive correlation with Total Amount (0.85).
- Quantity had a moderate positive correlation with Total Amount (0.37).
- Age showed almost no correlation with the other numerical variables.

**6. Customer Preferences by Age**
- Clothing recorded its highest revenue among customers aged 26–35.
- Electronics performed strongest among customers aged 36 and above.
- Beauty revenue was considerably lower among customers aged 56–64.

### Business Recommendations

1. **Prioritise premium products:** Give greater visibility to products in the 300 and 500 price tiers, which account for approximately 88% of revenue.

2. **Adopt age-based marketing:** Tailor Clothing campaigns towards customers aged 26–35 and Electronics campaigns towards customers aged 36 and above.

3. **Plan for seasonal demand:** Prepare for increased demand ahead of Q4 and consider targeted promotions during weaker periods, particularly September.

4. **Maintain gender-neutral marketing:** Since average transaction spending is nearly identical across genders, there is little evidence to justify gender-specific pricing or campaigns.

5. **Improve Beauty category reach:** Investigate opportunities to increase transaction volume in the Beauty category, which has the highest average order value but the fewest transactions.

6. **Strengthen customer retention:** Maintain engagement with the 46–55 age group while exploring opportunities to attract younger customers.

### Limitations
- The dataset contains only 1,000 transactions covering one year.
- Individual product names were unavailable; analysis was therefore limited to three product categories and five unit-price tiers.
- Store locations and other geographical variables were not available.
- The findings represent observed patterns and should be validated with additional data before major business decisions are made.

### Conclusion
The exploratory analysis revealed that retail revenue is influenced more strongly by product pricing than sales volume, while customer preferences vary across age groups.

The analysis also identified seasonal sales fluctuations, differences in category performance and opportunities for more targeted marketing strategies.

Overall, the project demonstrates how Python-based exploratory data analysis can transform raw retail transaction data into meaningful business insights that support informed decision-making.

### Repository Structure
```text
OIBSIP/
│
├── Task_1_EDA_Retail_Sales/
│   ├── README.md
│   ├── OIBSIP_DataAnalytics_L1_EDA_RetailSales.ipynb
│   ├── retail_sales_dataset.csv
│   └── visualisations/
│
└── README.md
```

### Project Information
- **Programme:** Oasis Infobyte Internship (OIBSIP)
- **Domain:** Data Analytics
- **Level:** 1
- **Task:** 1 – Exploratory Data Analysis on Retail Sales Data
- **Environment:** Google Colab
- **Language:** Python

**Author:** Hephzibah Ajala

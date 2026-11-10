# Predicting House Prices with Linear Regression

**Oasis Infobyte Internship | Data Analytics Track | Level 2, Task 1**

## Objective
Build and evaluate a linear regression model that predicts house sale prices from features such as size, quality, age and location, covering the full workflow from data exploration and cleaning to model interpretation.

## Dataset
- **Source:** "House Prices: Advanced Regression Techniques" (Ames Housing data) on Kaggle, `train.csv`
- **Size:** 1,460 houses, 81 columns
- **Target:** SalePrice
- The dataset is not included in this repository. Download it from Kaggle (link below).

## Tools Used
- Python
- pandas, numpy
- matplotlib, seaborn
- scikit-learn
- Jupyter Notebook (Google Colab)

## Workflow
1. **Exploration:** checked missing values and duplicates, and examined the price distribution. Prices are right-skewed (skewness 1.88): mean about 180,921 against a median of 163,000.
2. **Feature selection:** chose 12 predictors from 81 columns and explained the reasoning for each:
   - Size and space: GrLivArea, TotalBsmtSF, LotArea, LotFrontage, BedroomAbvGr, FullBath, GarageCars
   - Quality: OverallQual, KitchenQual, CentralAir
   - Age: HouseAge (calculated as year sold minus year built)
   - Location: Neighborhood
3. **Missing values:** LotFrontage was the only selected column with blanks (259, about 18%), filled with the median. Columns such as PoolQC and Alley were excluded because a blank in them means the feature does not exist, not that data is missing.
4. **Encoding:** one-hot encoded Neighborhood, KitchenQual and CentralAir, giving 37 input features.
5. **Correlation heatmap:** identified OverallQual (0.79) and GrLivArea (0.71) as the features most strongly related to price.
6. **Train/test split:** 80/20 (1,168 training and 292 test houses), with a fixed random seed for reproducibility.
7. **Model:** trained a Linear Regression model with scikit-learn.
8. **Evaluation and diagnostics:** MSE, RMSE and R², an actual-vs-predicted scatter plot, and a residual plot.
9. **Interpretation:** analysed coefficients and compared them fairly using the effect of a typical change in each feature.
10. **Bonus:** compared against a Ridge regression model.

## Results

| Measure | Value |
|---|---|
| MSE | 1,186,869,434 |
| RMSE | 34,451 |
| R² (test) | 0.8453 |
| R² (training) | about 0.825 |

The model explains about 85% of the variation in prices on houses it had not seen, with typical errors of about 34,000 (average price about 179,000). Training and test scores are similar, so the model is not overfitting.

### Ridge Comparison

| Model | RMSE | R² |
|---|---|---|
| Linear Regression | 34,450.97 | 0.8453 |
| Ridge Regression (alpha = 10) | 34,447.39 | 0.8453 |

Performance was practically identical, so the simpler linear model was kept.

## Key Findings
- **Largest positive effects (numeric features, for a typical change):** living area (about +23,300) and overall quality (about +17,000), followed by garage capacity (about +8,500).
- **Largest negative effect (numeric features):** house age, about -6,800 for a typical change, or about 222 per year.
- **Location matters:** compared with the reference neighbourhood, a house in NoRidge is worth about 74,700 more.
- **Kitchen quality matters:** an excellent kitchen is worth roughly 46,000 to 54,000 more than other kitchen grades.
- **Bedrooms:** the coefficient is slightly negative (about -3,000 per bedroom). With living area already in the model, an extra bedroom means smaller rooms.

## Limitations
- The model underestimates expensive houses. Residuals widen as predicted price rises: typical errors are about 20,000 below 120,000 but about 85,000 above 300,000.
- Only 12 of 81 features were used, and the model assumes straight-line relationships.
- Coefficients show association, not cause and effect.
- The data covers one city and period.

## Possible Improvements
- Predict the logarithm of price to reduce skew and uneven errors
- Add interaction features or more predictors
- Compare with tree-based models such as Random Forest
- Use cross-validation

## Repository Contents
- `OIBSIP/DataAnalytics-L2-PredictingHousePricesWithLinearRegression.ipynb`
- `train.csv file`

## How to Run
1. Download `train.csv` from Kaggl.
2. Upload it to your Google Drive (My Drive).
3. Open the notebook in Google Colab, click Runtime, then Run all, and allow Drive access when prompted.

## Key Learnings
The biggest thing I learned was how to read coefficients: each one shows how much the predicted price changes when that feature increases by one unit, with all other features held constant. For example, the bedroom coefficient was about -3,000, even though bedrooms and price are positively correlated. This is because once living area is held fixed, an extra bedroom simply means smaller rooms. It also taught me that coefficients show association, not cause and effect.

## Author
Hephzibah Ajala
Data Analytics Intern, Oasis Infobyte
www.linkedin.com/in/hephzibah-ajala-a21a0135a | [GitHub profile link]

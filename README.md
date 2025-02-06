# Commodity Prices Forecasting

## Overview
This project focuses on developing a statistical learning solution to predict the S&P 500 index using historical economic indicators, particularly commodity prices such as crude oil, natural gas, and other macroeconomic factors. By leveraging machine learning models, this analysis aims to uncover key patterns that influence the movements of the S&P 500.

## Research Questions
1. **Primary Research Question**: How accurately can the S&P 500 index be predicted using historical data on commodity prices and other macroeconomic indicators?
2. **Secondary Research Questions**:
   - Which predictors, including lagged variables and commodity prices, are most influential in explaining the variability of the S&P 500 index?
   - How do different statistical learning approaches, such as Random Forest and Linear Regression, compare in terms of predictive accuracy and interpretability?

## Dataset
- The dataset is sourced from **Kaggle's Commodity Prices (1960-2021)** and enriched with **monthly closing prices of the S&P 500 index** from Yahoo Finance.
- It consists of **62 rows and 32 columns**, where the **SP500_Price** serves as the target variable.

## Methodology
### Data Preprocessing and Feature Engineering
- Imputed missing values using the **mean of the respective variable**.
- Applied **Pearson correlation** to measure linear relationships between variables.
- Addressed **multicollinearity** by removing highly correlated features (correlation > 0.9).
- Standardized numeric features using **z-score normalization**.
- Introduced **1-year lagged features** to capture temporal dependencies.
- Removed predictors with low absolute correlation (< 0.3) to enhance model performance.

### Machine Learning Models
1. **Linear Regression** - A simple, interpretable model assuming a linear relationship between predictors and target.
2. **Random Forest (100 trees)** - A non-parametric ensemble model that captures complex, non-linear relationships.

### Model Evaluation Metrics
- **Mean Squared Error (MSE)** - Measures average squared prediction errors.
- **R-squared (R²)** - Indicates the proportion of variance explained by the model.

## Results
| Model           | MSE    | R²    |
|----------------|--------|-------|
| Linear Regression | 0.0955 | 0.8769 |
| Random Forest | 0.0311 | 0.9599 |

- **Random Forest outperformed Linear Regression** in terms of both **MSE and R²**, demonstrating higher predictive accuracy.
- Feature importance analysis revealed that **lagged commodity prices significantly impact S&P 500 movements**.

## Key Findings and Future Work
- The study confirms that **commodity prices and macroeconomic indicators influence the S&P 500 index**.
- The inclusion of **lagged variables improved model accuracy** by capturing time-based dependencies.
- Future improvements could include:
  - Adding external economic indicators (e.g., exchange rates, interest rates, inflation).
  - Implementing **regularized regression** (Ridge, Lasso) to handle multicollinearity.
  - Exploring **ensemble methods** like Gradient Boosting or stacking models.
  - Applying a **rolling forecasting strategy** for real-world financial applications.

## Team Contributions
The project was developed collaboratively with contributions in data collection, feature engineering, modeling, analysis, and report writing. Regular meetings and discussions ensured smooth coordination and integration of all workstreams.

## Repository Structure
```
├── data/			# Contains raw and processed datasets
├── scripts/			# Python/R scripts for data preprocessing and modeling
├── results/			# Output files, plots, and model evaluation reports
├── Final Project 3.Rmd	# R Markdown file for analysis
├── IS507_Final Report.pdf	# Final project report
├── README.md		# Project documentation
```

## How to Run the Project
1. Clone this repository:
   ```sh
   git clone https://github.com/yourusername/commodity-prices-forecasting.git
   ```
2. Run the R Markdown file for analysis:
   ```sh
   Rscript -e "rmarkdown::render('Final Project 3.Rmd')"
   ```
3. Check the **results/** directory for model outputs and visualizations.

## Acknowledgments
This project was completed as part of the **IS 507 Final Project** at the University of Illinois, Urbana-Champaign.

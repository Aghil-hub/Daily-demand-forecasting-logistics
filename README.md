# Daily Demand Forecasting for a Logistics Firm

This project builds a daily demand forecasting model for a logistics company using the UC Irvine Daily Demand Forecasting Orders dataset. The objective is to predict total daily orders and compare model performance across repeated train-test splits using RMSPE.

## Results / Key Findings

- Non-urgent and Urgent orders are the dominant predictors of total daily demand, confirmed by both 
  correlation analysis and Random Forest feature importance.
- Day-of-week effects were explored (Day 2 showed significantly higher demand, p < 0.001) but added 
  no meaningful improvement to RMSPE once order volumes were included.
- Linear Regression outperformed Random Forest across all 1,000 iterations, achieving 3× lower mean 
  RMSPE (0.05 vs 0.13), suggesting the demand-volume relationship is largely linear.
- The parsimonious two-variable linear model is recommended as the primary forecasting tool, offering 
  the best balance of accuracy, stability, and interpretability.

## Approach

- Exploratory data analysis
- Correlation and feature selection
- Linear regression baseline
- Random forest benchmark
- 1000 repeated 80/20 train-test splits
- Evaluation using RMSE and RMSPE

## Visual Preview

Full EDA, residual diagnostics, feature importance plots, and model comparison are available in the 
notebook.

![Correlation Heatmap](images/correlation_heatmap.png)
![Feature Importance](images/feature_importance.png)

## Results
| Model | Mean RMSE | SD RMSE | Mean RMSPE | SD RMSPE |
|------|----------:|--------:|-----------:|---------:|
| Linear Regression | 18.68 | 15.58 | 0.05 | 0.03 |
| Random Forest | 40.58 | 16.89 | 0.13 | 0.06 |

## Dataset

- **Source:** [UCI Daily Demand Forecasting Orders](https://archive.ics.uci.edu/dataset/409/daily+demand+forecasting+orders)
- **Reference:** Ferreira et al. (2016), *IEEE Latin America Transactions*, 14(3), pp. 1519–1525
- **Observations:** 60 daily records
- **Target:** Total Orders

## Tools

Python, Pandas, NumPy, Statsmodels, Scikit-learn, Matplotlib, Seaborn, Google Colab

## How to Run

- Open `Demand_Forecasting.ipynb` directly in Google Colab or clone the repo and run locally in 
  Jupyter / VS Code.
- No additional data setup is needed; the dataset is loaded directly from the UCI repository in 
  the first notebook cell.
- Run all cells from top to bottom.

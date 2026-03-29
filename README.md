# Daily Demand Forecasting for a Logistics Firm

This project builds a daily demand forecasting model for a logistics company using the UC Irvine Daily Demand Forecasting Orders dataset. The objective is to predict total daily orders and compare model performance across repeated train-test splits using RMSPE.

## Objective
- Forecast total daily orders
- Identify the most important demand drivers
- Compare linear regression and random forest performance
- Recommend a model based on accuracy, stability, and interpretability

## Dataset
- Source: UC Irvine's ML Repo: Daily Demand Forecasting Orders dataset
- Observations: 60 daily records
- Target: Total Orders

## Approach
- Exploratory data analysis
- Correlation and feature selection
- Linear regression baseline
- Random forest benchmark
- 1000 repeated 80/20 train-test splits
- Evaluation using RMSE and RMSPE

## Key Findings
- Non-urgent order and urgent order were the strongest predictors of total orders.
- Day-of-week effects were explored, but did not materially improve RMSPE in the final model.
- Linear regression outperformed random forest on average across 1000 iterations.
- The final model achieved lower average RMSPE with better interpretability and stability.

## Results
| Model | Mean RMSE | SD RMSE | Mean RMSPE | SD RMSPE |
|------|----------:|--------:|-----------:|---------:|
| Linear Regression | 18.68 | 15.58 | 0.05 | 0.03 |
| Random Forest | 40.58 | 16.89 | 0.13 | 0.06 |

# Stock Market Predictor

## Overview

This project aims to predict whether the S&P 500 index will close higher the next day using historical stock market data and machine learning techniques. The model is trained on decades of financial data and incorporates technical indicators and trend-based features to improve prediction accuracy.

## Data Source

- **Yahoo Finance**: Historical daily data for the S&P 500 index (`^GSPC`) is fetched using the `yfinance` Python library. This includes open, high, low, close, and volume data from the earliest available date.

## Methodology

The analysis follows these key steps:

1. **Data Collection**: Uses `yfinance` to download full historical data for the S&P 500 index.
2. **Feature Engineering**: Constructs meaningful features like:
   - Rolling average ratios (2, 5, 60, 250, 1000-day)
   - Momentum trends (count of recent "up" days)
3. **Target Creation**: Binary target variable indicating if the market closed higher the next day.
4. **Modeling**: A Random Forest Classifier is trained to predict the target.
5. **Backtesting**: A custom walk-forward validation framework is used to simulate real-world usage and avoid lookahead bias.
6. **Evaluation**: Model performance is evaluated using precision and visual comparisons of actual vs. predicted market direction.

## Key Findings

- Technical indicators and trend-based features help capture meaningful signals in market movement.
- The model shows good precision in identifying days when the market is likely to rise.
- The walk-forward validation approach provides a more realistic picture of live trading performance.

## Future Work

- **Hyperparameter Tuning**: Use `GridSearchCV` or `Optuna` for optimal model settings.
- **Additional Indicators**: Add MACD, Bollinger Bands, or sector-based signals.
- **Portfolio Simulation**: Integrate with a basic trading strategy to test real-world profitability.
- **Web App**: Build a simple dashboard for interactive predictions.

## Conclusion

This project demonstrates how machine learning can be applied to financial time series to predict market direction. With carefully engineered features and robust validation, it's possible to uncover trends that inform short-term investment decisions.

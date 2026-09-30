# Spotter Freight Rate Prediction Assessment

## Overview

This project predicts freight rates using historical load data.

The development dataset was evaluated using time-based validation because the final validation data represents future dates relative to the training data.

## Approach

The main steps were:

1. Exploratory data analysis
2. Data quality checks
3. Missing-value handling
4. Feature engineering
5. Time-based validation
6. Model comparison
7. Final model training
8. Validation and December predictions

## Data Cleaning

- Negative weight values were treated as sign errors and converted to positive values.
- Missing weight values were filled using the median weight from the training data.
- Missing market_index values were filled using the training median.
- Dates were converted to datetime format.

## Feature Engineering

Date features:
- month
- day_of_month
- day_of_week

A route feature was also created:

pickup + delivery

## Models Tested

- Linear Regression
- Random Forest Regressor
- Gradient Boosting Regressor
- CatBoost Regressor

CatBoost provided the strongest validation performance and was selected for the final predictions.

## Validation Strategy

A time-based split was used rather than a random split.

Rolling validation periods were used:

- May-Jun
- Jul-Aug
- Sep-Oct

This better represents the real assessment scenario where historical data is used to predict future freight rates.

## Install Dependencies

```bash
pip install -r requirements.txt
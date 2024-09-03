# Fuel Consumption Forecasting for U.S. Electricity Generation

## Overview
This repository presents a comprehensive study on fuel consumption forecasting crucial for electricity generation in the United States. It covers data from 2015 to 2022 and employs advanced statistical and machine learning techniques to forecast future trends. This analysis supports policymakers, industry stakeholders, and academic researchers by providing insights into energy trends, promoting sustainable and efficient energy management.

## Table of Contents
- [Introduction](#introduction)
- [Data Sources](#data-sources)
- [Methodology](#methodology)
  - [Seasonality Analysis](#seasonality-analysis)
  - [Autocorrelation Analysis](#autocorrelation-analysis)
  - [Forecasting Models](#forecasting-models)
- [Results](#results)
  - [Model Performance](#model-performance)
  - [Key Findings](#key-findings)
- [Discussion](#discussion)
- [Contributions](#contributions)
- [Citation](#citation)

## Introduction
This project undertakes an in-depth analysis of fuel consumption data, focusing on major fuels like coal, natural gas, and petroleum products used in U.S. electricity generation. The dynamic nature of the energy sector, influenced by policy changes, market conditions, and technological advancements, requires robust forecasting models that can adapt and predict with high accuracy.

## Data Sources
Data for this analysis was sourced from the U.S. Energy Information Administration (EIA), which provides detailed records of monthly and annual fuel consumption across various sectors. The dataset includes several fuel types and spans from January 2015 to December 2022, providing a solid foundation for historical analysis and future forecasting.

## Methodology

### Seasonality Analysis
We first conducted a detailed analysis of seasonal consumption patterns for each type of fuel. Using graphical methods and statistical tests, we identified specific months where fuel consumption peaks due to factors such as heating demand in winter or cooling demand in summer. Seasonality effects are crucial for accurate forecasting, influencing the selection and configuration of subsequent models.

### Autocorrelation Analysis
Autocorrelation was analyzed using ACF (Autocorrelation Function) and PACF (Partial Autocorrelation Function) plots to identify the presence of any time-dependent structure in the data. This analysis helps in choosing the right parameters for ARIMA and other time-series models, ensuring that they accurately capture the dynamics of the data.

### Forecasting Models
Several models were employed to forecast future fuel consumption:

#### STL (Seasonal and Trend decomposition using Loess)
STL is a versatile and robust method for decomposing time series into seasonal, trend, and residual components. We used STL to handle non-linear trends and changing seasonality in the data, which is common in energy consumption data due to evolving market and regulatory environments.

#### ETS (Exponential Smoothing State Space Model)
ETS models were used to forecast based on error, trend, and seasonal components. These models are particularly useful when data exhibit consistent seasonal patterns and non-linear trends. We experimented with various forms of ETS models (additive and multiplicative) to find the best fit for each fuel type.

#### ARIMA (AutoRegressive Integrated Moving Average)
ARIMA models are fitted based on the results from the autocorrelation analysis. We determined the optimal order of differencing (d), the number of lagged forecast errors in the prediction equation (q), and the size of the lagged observations (p) for each model.

#### Benchmark Methods
- **Mean:** Uses the average historical data to forecast future values.
- **Naïve:** Forecasts future values as equal to the last observed value.
- **Drift:** Assumes that the future values have a trend (drift) that is the same as the trend observed in the past.
- **Seasonal Naïve:** Assumes that the future will resemble the past seasonally adjusted data.

## Results

### Model Performance
Each model's performance was evaluated based on RMSE (Root Mean Squared Error), MAE (Mean Absolute Error), and other relevant metrics. Comparisons were made not only within the same fuel type but also across different models to ascertain their effectiveness under various conditions.

### Key Findings
- **Natural Gas:** ETS models provided the best forecasts with the lowest RMSE, reflecting their strength in handling the series’ trend and seasonal components.
- **Coal:** STL models outperformed others, especially in capturing the coal consumption's decline over the study period.
- **Petroleum Products:** ARIMA models excelled, indicating complex autoregressive behaviors in these data series.

## Discussion
The discussion section delves into the implications of our findings, discussing how accurate forecasts can influence policy-making, investment decisions, and operational strategies in the energy sector.

## Contributions
Details on how to contribute to this project are available here. We encourage contributions from data scientists, economists, and energy experts.

## Citation
Please cite this work using the following format:

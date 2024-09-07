# ⚡ Fuel Consumption Forecasting for U.S. Electricity Generation ⚡

## 🔍 Overview
This repository presents a comprehensive study on fuel consumption forecasting crucial for electricity generation in the United States. It covers data from 2015 to 2022 and employs advanced statistical and machine learning techniques to forecast future trends. This analysis supports policymakers, industry stakeholders, and academic researchers by providing insights into energy trends, promoting sustainable and efficient energy management.

## 📑Table of Contents
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

## 📘Introduction
This project undertakes an in-depth analysis of fuel consumption data, focusing on major fuels like coal, natural gas, and petroleum products used in U.S. electricity generation. The dynamic nature of the energy sector, influenced by policy changes, market conditions, and technological advancements, requires robust forecasting models that can adapt and predict with high accuracy.

### 📈Overall Trend Analysis of Fuel Consumption 
The trends observed in fuel consumption over time, as depicted in Figure 1 shows the dynamics of various fuel types utilized in U.S. electricity generation. Natural gas consumption exhibits a 
consistent upward trajectory from January 2016 to January 2022, with occasional fluctuations [6,11]. This notable increase, supported by statistical evidence [11] is attributed to several factors, including the growing preference for natural gas as a cleaner alternative, increased efficiency in gas‐powered plants, and a shift towards renewables in the energy mix. In contrast, coal consumption displays a fluctuating trend with distinct periods of growth and decline, reaching a significant trough in January 2020. 

<div align="center">
    <img src="https://github.com/user-attachments/assets/a970c1dc-cf66-4d53-b77d-4cb8849bfa4f" width="700">
</div>

## 🛠️Data Sources
Data for this analysis was sourced from the U.S. Energy Information Administration (EIA), which provides detailed records of monthly and annual fuel consumption across various sectors. The dataset includes several fuel types and spans from January 2015 to December 2022, providing a solid foundation for historical analysis and future forecasting.

## 📊Methodology

### ⏳Seasonality Analysis
We first conducted a detailed analysis of seasonal consumption patterns for each type of fuel. Using graphical methods and statistical tests, we identified specific months where fuel consumption peaks due to factors such as heating demand in winter or cooling demand in summer. Seasonality effects are crucial for accurate forecasting, influencing the selection and configuration of subsequent models.

![image](https://github.com/user-attachments/assets/462cb9f3-bc7b-4538-b1f9-a37ed75b1e53)


<!-- 
#### Seasonality Analysis of Fuel Consumption 

<div align="center">
    <img src="https://github.com/user-attachments/assets/d24ce6a1-8593-45ae-8076-11d422d179e0" width="700">
</div>


#### Seasonality Analysis of NG Consumption 

<div align="center">
    <img src="https://github.com/user-attachments/assets/ce42bd6a-6fcc-486d-ab4b-03eeff88c41a" width="700">
</div>

#### Seasonality Analysis of Petroleum Coke Consumption 

<div align="center">
    <img src="https://github.com/user-attachments/assets/1532c4de-70b1-433f-938e-26769d439870" width="700">
</div>

#### Seasonality Analysis of Petroleum Liquids Consumption 

<div align="center">
    <img src="https://github.com/user-attachments/assets/2247aaf1-aeb6-4d91-b20a-d2189d3554e0" width="700">
</div>
-->

### 🔄Autocorrelation Analysis
Autocorrelation was analyzed using ACF (Autocorrelation Function) and PACF (Partial Autocorrelation Function) plots to identify the presence of any time-dependent structure in the data. This analysis helps in choosing the right parameters for ARIMA and other time-series models, ensuring that they accurately capture the dynamics of the data.

![image](https://github.com/user-attachments/assets/c23d5e4e-4796-45b1-b9c8-fa4dad26103c)


<!-- 
#### Autocorrelation Analysis of NG Consumption 
<div align="center">
    <img src="https://github.com/user-attachments/assets/81c7ecf5-cd4b-4fda-bc67-423063ee74bf" width="700">
</div>

#### Autocorrelation Analysis of Coal Consumption 
![image](https://github.com/user-attachments/assets/9a944dcf-64aa-4296-9578-c1e0ea95f0bd)
<div align="center">
    <img src="https://github.com/user-attachments/assets/81c7ecf5-cd4b-4fda-bc67-423063ee74bf" width="700">
</div>
-->

### 🧠Forecasting Models
Several models were employed to forecast future fuel consumption:

#### STL (Seasonal and Trend decomposition using Loess)
STL is a versatile and robust method for decomposing time series into seasonal, trend, and residual components. We used STL to handle non-linear trends and changing seasonality in the data, which is common in energy consumption data due to evolving market and regulatory environments.

#### ETS (Exponential Smoothing State Space Model)
ETS models were used to forecast based on error, trend, and seasonal components. These models are particularly useful when data exhibit consistent seasonal patterns and non-linear trends. We experimented with various forms of ETS models (additive and multiplicative) to find the best fit for each fuel type.

#### ARIMA (AutoRegressive Integrated Moving Average)
ARIMA models are fitted based on the results from the autocorrelation analysis. We determined the optimal order of differencing (d), the number of lagged forecast errors in the prediction equation (q), and the size of the lagged observations (p) for each model.

#### Forecasting Models for Natural Gas Consumption

Figure 10 serves as a visual representation of the forecasted NG consumption for the years 2023 and 2024, employing diverse forecasting methodologies. The benchmark methods, STL decomposition, ETS method, and ARIMA method each contribute to a multifaceted analytical approach, offering a nuanced understanding of the varied strategies employed in forecasting. This rigorous methodology adheres to industry standards and contributes valuable insights to the realm of energy planning and policy formulation. 

<div align="center">
    <img src="https://github.com/user-attachments/assets/92f85531-821f-42ea-a0c8-c1fc17b64cc6">
</div>

<!--
####  Forecasting Models for Coal Consumption 

<div align="center">
    <img src="https://github.com/user-attachments/assets/7c76525e-b3dd-4c4c-b313-3da1a8de494b">
</div>

#### Forecasting Models for Petroleum Coke Consumption

<div align="center">
    <img src="https://github.com/user-attachments/assets/8c5daeda-32e7-4733-8919-d7174962d462">
</div>

#### Forecasting Models for Petroleum Liquids Consumption

<div align="center">
    <img src="https://github.com/user-attachments/assets/4c7809b8-98b8-4168-b104-1c6b5ed1fbc2">
</div>
-->

## 🎯Results

### 📊Model Performance
Each model's performance was evaluated based on RMSE (Root Mean Squared Error), MAE (Mean Absolute Error), and other relevant metrics. Comparisons were made not only within the same fuel type but also across different models to ascertain their effectiveness under various conditions.

<!--
#### Natural Gas
<div align="center">
    <img src="https://github.com/user-attachments/assets/6502c990-133f-4f69-ad1f-75143295ad88">
</div>

#### Coal
<div align="center">
    <img src="https://github.com/user-attachments/assets/da0b921b-1551-4e92-ad2d-3dba4a2ab1eb">
</div>

#### Coak
<div align="center">
    <img src="https://github.com/user-attachments/assets/7f186c88-3b2a-4277-b175-e9c8c286822f">
</div>

#### Petroleum Liquid
<div align="center">
    <img src="https://github.com/user-attachments/assets/23885392-2a05-41c7-9b65-eba9355ad35e">
</div>
-->

### 🔍Analysis of forecasting trends for different energy streams

<div align="center">
    <img src="https://github.com/user-attachments/assets/c81f3e13-d2bb-4956-b0f6-3c8cdbcbad95" height="250">
</div>

The projected consumption patterns for electricity generation in the USA from September 2023 to December 2024 highlight fluctuations in natural gas usage, with peaks in July and August 2024 due to increased cooling demand. Coal consumption shows minor variations, rising in December 2023, likely due to winter energy needs. Coke demand remains stable, with a slight peak in December 2023, reflecting consistent industrial use. Petroleum liquids maintain a steady consumption rate throughout the period, indicating a stable role in the energy mix. The forecast suggests that natural gas and coal are more affected by seasonal and market factors, while coke and petroleum liquids show stability, likely due to long-term contracts or stockpiling. Corroborating these projections with external sources is crucial for strategic energy planning and future demand management.

### 📊Key Findings
- **Natural Gas:** ETS models provided the best forecasts with the lowest RMSE, reflecting their strength in handling the series’ trend and seasonal components.
- **Coal:** STL models outperformed others, especially in capturing the coal consumption's decline over the study period.
- **Petroleum Products:** ARIMA models excelled, indicating complex autoregressive behaviors in these data series.

## 💭Discussion
The discussion section delves into the implications of our findings, discussing how accurate forecasts can influence policy-making, investment decisions, and operational strategies in the energy sector.

## 🤝Contributions
Details on how to contribute to this project are available here. We encourage contributions from data scientists, economists, and energy experts.

## 📚Citation
Please cite this work using the following format: Bhuiyan, M.M.H.; Sakib, A.N.; Alawee, S.I.; Razzaghi, T. Fueling the Future: A Comprehensive Analysis and Forecast of Fuel Consumption Trends in U.S. Electricity Generation. Sustainability 2024, 16, 2388

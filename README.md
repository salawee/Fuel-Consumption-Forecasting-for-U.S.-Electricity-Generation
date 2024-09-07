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
   - [Key Findings](#key-findings)
- [Discussion](#discussion)
- [Contributions](#contributions)
- [Citation](#citation)

## 📘Introduction
In the dynamic landscape of electricity generation, forecasting fuel consumption is a key challenge faced by energy planners and policymakers. This repository leverages cutting-edge statistical and machine learning techniques to analyze and predict trends in the consumption of key energy streams such as natural gas, coal, and petroleum products. With data from 2015 to 2022, we use methods like STL decomposition, ETS, and ARIMA models to ensure robust predictions, informed by seasonality and autocorrelation insights. This project focuses on optimizing code for efficient, scalable forecasting, helping developers, researchers, and energy experts generate actionable insights into future energy demands.

By focusing on reproducibility and performance, this repository allows you to explore different forecasting models and assess their effectiveness through code, all while keeping an eye on real-world energy dynamics. Let's code for a more energy-efficient future! 🌱💡

The trends in fuel consumption, as illustrated in Figure 1, highlight the dynamic usage of various energy sources in U.S. electricity generation. From January 2016 to January 2022, natural gas consumption shows a steady upward trend, with some fluctuations. This increase is driven by factors such as the growing adoption of natural gas as a cleaner energy source, enhancements in gas-powered plant efficiency, and the ongoing transition to renewables. On the other hand, coal consumption follows a more irregular pattern, characterized by alternating periods of growth and decline, with a notable drop in January 2020. These patterns underscore the shifting energy landscape and are essential for building predictive models that adapt to changing consumption behaviors over time. By leveraging historical trends through code, we can develop smarter, data-driven solutions to forecast future energy dema

<div align="center">
    <img src="https://github.com/user-attachments/assets/a970c1dc-cf66-4d53-b77d-4cb8849bfa4f" width="700">
</div>

## 🛠️Data Sources
Data for this analysis was sourced from the U.S. Energy Information Administration (EIA), which provides detailed records of monthly and annual fuel consumption across various sectors. The dataset includes several fuel types and spans from January 2015 to December 2022, providing a solid foundation for historical analysis and future forecasting.

## 📊Methodology

This project applies advanced time-series analysis and machine learning techniques to forecast fuel consumption patterns in U.S. electricity generation. The process starts with data preprocessing, where historical fuel consumption data is cleaned and prepared for analysis. We then perform seasonality and trend analysis using methods like STL decomposition to uncover patterns in the data. Autocorrelation and stationarity tests help us select appropriate models such as ARIMA and ETS. To improve model accuracy, we implement cross-validation and perform hyperparameter tuning. Finally, models are evaluated using performance metrics such as RMSE and MAE, and the results are visualized to inform energy strategy and decision-making. This coding-driven approach leverages time-series forecasting to support effective energy planning.

### ⏳Seasonality Analysis
Seasonality analysis is crucial for identifying recurring patterns in fuel consumption, such as increased usage during winter or summer months. By decomposing the time series data into seasonal components, we can observe how consumption fluctuates across different periods. Understanding these patterns allows us to select models that account for these fluctuations, improving forecasting accuracy. We used methods like STL decomposition to isolate the seasonal, trend, and residual components, which helps in understanding how seasonal factors influence the data over time.

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
Autocorrelation analysis helps us understand the degree to which past values in the time series influence future values. By analyzing autocorrelation and partial autocorrelation plots (ACF and PACF), we identify dependencies between time lags and determine the appropriate lag structure for models like ARIMA. This step is critical to ensure our models effectively capture the underlying temporal relationships in the data. Autocorrelation analysis allows us to fine-tune forecasting models to account for patterns in lagged data, making the predictions more reliable and data-driven.

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
Several models were utilized to accurately forecast future fuel consumption, each tailored to address different characteristics of the time series data:

STL (Seasonal and Trend Decomposition using Loess)
STL is a highly flexible method for decomposing time series data into its seasonal, trend, and residual components. This approach is particularly valuable in energy consumption forecasting because it can effectively manage non-linear trends and dynamic seasonal patterns. Given the complexity of energy markets and the influence of regulatory changes, STL allows us to isolate these factors and better understand the underlying behaviors of fuel consumption, making it a powerful tool for handling evolving consumption patterns.

ETS (Exponential Smoothing State Space Model)
The ETS model focuses on three key components: error, trend, and seasonality. It is especially useful when the data demonstrates consistent seasonal patterns alongside non-linear trends. By experimenting with different forms of ETS (both additive and multiplicative), we were able to identify the most suitable model for each type of fuel consumption. The strength of ETS lies in its ability to capture smooth transitions in trends and seasonality, which are crucial for forecasting energy consumption that fluctuates predictably over time.

ARIMA (AutoRegressive Integrated Moving Average)
ARIMA is another essential forecasting method, particularly effective when data shows significant autocorrelation or dependencies between time lags. Based on autocorrelation analysis, ARIMA models are configured by determining the optimal values for the lagged observations (p), the degree of differencing required for stationarity (d), and the lagged forecast errors (q). ARIMA is well-suited for datasets where past consumption values are strongly correlated with future values, making it a reliable model for long-term energy forecasting.

By leveraging these models, we ensure that various aspects of the time series, such as seasonality, trend shifts, and autocorrelation, are accurately captured, enabling precise and robust fuel consumption forecasts.

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

The results from our forecasting analysis reveal distinct trends and performance differences across various fuel types used in U.S. electricity generation. By comparing models like STL, ETS, ARIMA, and benchmark methods, we gain insight into their effectiveness based on key metrics like Root Mean Squared Error (RMSE).

Natural Gas Consumption
Natural gas consumption displayed clear seasonal peaks, particularly in the summer months of 2024, driven by increased demand for electricity for cooling. The ETS model provided the most accurate forecasts for natural gas, achieving the lowest RMSE at 20,687.46. This result indicates ETS’s strength in capturing both trend and seasonality in the data, making it the most reliable model for forecasting natural gas consumption.

Coal Consumption
Coal consumption exhibited a fluctuating trend, with a notable drop coinciding with the onset of the COVID-19 pandemic in January 2020. The STL model performed best for coal consumption forecasting, with an RMSE of 5,936.20. The STL model effectively captured the decline in coal usage as the industry shifts towards cleaner energy sources, reflecting the broader transition away from coal.

Petroleum Coke Consumption
Petroleum coke consumption demonstrated variability, with notable peaks in the summer months. The Seasonal Naïve (SNaïve) model outperformed others for forecasting petroleum coke consumption, yielding an RMSE of 99.49. This model's ability to replicate the recurring seasonal peaks made it particularly effective in capturing the regular patterns in petroleum coke demand.

Petroleum Liquids Consumption
Petroleum liquids showed less volatility compared to other fuels, with consumption remaining relatively stable. Surprisingly, the Mean method had the lowest RMSE of 287.34, outperforming more complex models like ARIMA. This suggests that the consistent nature of petroleum liquids consumption makes simpler methods more effective in forecasting this fuel type.

Overall, these results highlight the importance of using a variety of forecasting models to accurately capture the diverse consumption patterns of different fuels. The best-performing models—ETS for natural gas, STL for coal, and SNaïve for petroleum coke—each provided valuable insights for energy planning and policy formulation.

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
Natural Gas Consumption: The ETS model provided the most accurate forecasts for natural gas, with a strong ability to capture seasonal peaks, particularly in the summer and winter months. This highlights the importance of seasonality in energy consumption for natural gas.

- Coal Consumption: The STL model performed best for coal, effectively capturing the overall declining trend and erratic fluctuations in coal usage. The results reflect the broader transition from coal to cleaner energy sources, especially around the 2020 period.

- Petroleum Coke Consumption: The SNaïve model was the most successful for forecasting petroleum coke, showing that simple models can be highly effective when there are consistent seasonal patterns. This model replicated predictable peaks in petroleum coke demand.

- Petroleum Liquids Consumption: The Mean method surprisingly outperformed more complex models for petroleum liquids, due to the stable and consistent consumption pattern. This suggests that simpler approaches can be more effective when the data exhibits low volatility.

These key findings emphasize the importance of tailoring forecasting models to the specific characteristics of each fuel type, ensuring accurate predictions that support strategic energy planning and policy development.

## 💭Discussion

The results of this project demonstrate the power of applying a range of machine learning and time-series analysis techniques to forecast fuel consumption for U.S. electricity generation. By leveraging models like ETS, STL, and ARIMA, we were able to capture the complex patterns present in the data, including seasonality, trends, and autocorrelations, across different fuel types. Each model proved effective for different characteristics of the time series, highlighting the importance of selecting the right approach based on data behavior.

The ETS model was particularly strong in handling seasonal fluctuations in natural gas consumption, while the STL decomposition excelled at identifying long-term trends and irregular changes in coal consumption. Simpler models like SNaïve and the Mean method outperformed more complex models in cases where fuel consumption remained stable, demonstrating that complexity is not always necessary for accurate forecasting.

The use of cross-validation and performance metrics like RMSE and MAE ensured that our models were both accurate and reliable, making the forecasts valuable for strategic decision-making. This work emphasizes the value of combining machine learning techniques with robust time-series analysis to develop precise forecasts in dynamic sectors like energy.

Moving forward, these models can be further refined or adapted to incorporate additional external factors, such as economic shifts or policy changes, to improve predictive power. The insights gained from this project can guide energy policy, resource management, and operational efficiency in the energy sector, helping stakeholders plan for future energy demands with confidence.

## 🤝Contributions

We welcome contributions from developers, data scientists, and energy analysts who are interested in improving and expanding this project. Contributions can range from enhancing existing models, adding new forecasting methods, optimizing the code for performance, or incorporating additional datasets to improve the accuracy of the forecasts.

We encourage collaboration from those who are passionate about machine learning, time-series analysis, and the energy sector. Together, we can build more advanced tools for accurate fuel consumption forecasting and drive innovation in energy planning.

## 📚Citation
Please cite this work using the following format: Bhuiyan, M.M.H.; Sakib, A.N.; Alawee, S.I.; Razzaghi, T. Fueling the Future: A Comprehensive Analysis and Forecast of Fuel Consumption Trends in U.S. Electricity Generation. Sustainability 2024, 16, 2388

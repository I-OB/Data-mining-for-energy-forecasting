# Data mining for energy forecasting

## Overview
This project focuses on energy consumption forecasting using the Northern Illinois Hub dataset, publicly available on [Kaggle.](https://www.kaggle.com/datasets/robikscube/hourly-energy-consumption) The primary goal is to predict energy consumption trends based on temporal features and identify influential factors affecting energy usage.

## Literature Survey
A comprehensive literature survey titled "Data Mining for Energy Forecasting" is included in this repository. This survey provides an in-depth exploration of existing research, methodologies, and key findings in the field of data mining for energy forecasting, offering valuable insights into the broader context of this project.

### Keywords
Data mining, Literature survey, Regression

## Table of Contents
1. [Dataset](#Dataset)
2. [Visualization of Average Consumption](#Visualization-of-Average-Consumption)
3. [Initial model training](#Initial-model-training)
4. [Preprocessing-Outlier removal](#Preprocessing-Outlier-removal)
5. [Model reevaluation after preprocessing](#Model-reevaluation-after-preprocessing)
6. [Observations](#Observations)
7. [Conclusions](#Conclusions)

## 1. Dataset <a name="Dataset"></a>
The selected dataset consists of two columns: datetime information and energy consumption in megawatts. With a total of 58,450 instances, the dataset spans hourly consumption data from 2004 to 2011 and requires no preprocessing as it contains continuous values without missing entries.

## 2. Visualization of Average Consumption <a name="Visualization-of-Average-Consumption"></a>
### 2.1 Peak Demand Hours
Higher energy consumption from 5 pm to 10 pm is attributed to peak demand, coinciding with people returning home from work and simultaneous operation of residential and commercial establishments.

### 2.2 Seasonal Variation
June, July, and August exhibit consistently high energy consumption due to increased HVAC usage in the summer months.

### 2.3 Yearly Trends
The dataset shows a stable trend in average energy consumption over the years, except for a slight decline in the last year, indicating a potential shift in usage patterns.

## 3. Initial model training <a name="Initial-model-training"></a>
Before preprocessing, an XGBoost regressor model was trained, revealing key features: hour, day of the week, day of the year, month, and year. A Random Forest model was also built, showing similar influential features but with lower performance than XGBoost.

## 4. Preprocessing - Outlier removal <a name="Preprocessing-Outlier-removal"></a>
The dataset required minimal preprocessing, involving the removal of outliers. Instances outside calculated bounds were identified and removed, resulting in a cleaner dataset.

## 5. Model reevaluation after preprocessing <a name="Model-reevaluation-after-preprocessing"></a>
### 5.1 XGBoost Model
After removing outliers, the XGBoost model achieved improved performance, emphasizing the importance of temporal features.

### 5.2 Random Forest Model
Despite a performance increase post-preprocessing, the Random Forest model still trailed behind the XGBoost model.

### 5.3 Cross-Validated XGBoost Model
The cross-validated XGBoost model emerged as the best-performing model, showcasing the effectiveness of outlier removal in enhancing predictive accuracy.

## 6. Observations <a name="Observations"></a>
### 6.1 Effect of Outlier Removal
Outlier removal significantly improved model performance across all models, with the XGBoost regressor benefiting the most.

### 6.2 Feature Importance
Hour, day of the week, day of the year, month, and year consistently emerged as influential features, emphasizing their role in capturing temporal patterns in energy consumption.

## 7. Conclusions <a name="Conclusions"></a>
This project demonstrates the importance of outlier removal in enhancing the accuracy of energy consumption forecasting models. The XGBoost regressor, with its emphasis on temporal features, proved to be the most effective model in predicting energy usage patterns. The insights gained from this project can inform better resource allocation and decision-making in energy management scenarios.

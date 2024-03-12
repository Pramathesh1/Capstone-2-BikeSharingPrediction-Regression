# Bike Sharing Demand Prediction - Regression
The Seoul Bike Sharing Prediction dataset is a dataset that contains information about the rental bikes in the city of Seoul, South Korea. The dataset includes hourly bike rental data over a period of two years, from 2017 to 2018. It contains features such as the date and time of the rental, the weather conditions, the temperature, the humidity, and the wind speed. The target variable is the number of bikes rented for each hour.

This dataset is used to build machine learning models for predicting the number of bikes that will be rented in a given hour, based on the weather conditions and other features. This has practical applications for bike sharing companies, as it can help them to optimize their operations and better meet the demand for bike rentals.

## Business Problem Overview

Currently Rental bikes are introduced in many urban cities for the enhancement of mobility comfort. It is important to make the rental bike available and accessible to the public at the right time as it lessens the waiting time. Eventually, providing the city with a stable supply of rental bikes becomes a major concern. The crucial part is the prediction of bike count required at each hour for the stable supply of rental bikes.

## Summary
This regression project was conducted on the Seoul Bike Sharing dataset to predict the hourly count of bike rentals based on various features such as temperature, humidity, wind speed, and hour of the day. The project involved several steps, including preliminary data exploration and data wrangling, exploratory data analysis and data visualization, hypothesis testing, feature engineering, model implementation, and use of explainability tool.

### EDA
The dataset was explored to identify any missing or erroneous data points, and data wrangling techniques were employed to clean the dataset. Exploratory data analysis was then conducted to identify any patterns or trends in the data. The analysis revealed that the number of bike rentals was highest during rush hours, i.e., 7-9 am and 5-7 pm, and during the summer season.

### Hypothesis testing
Hypothesis testing was conducted to determine whether there was a significant difference in the number of bike rentals between weekdays and weekends, morning and evening and whether rainfall has any effect. The results showed that the number of bike rentals was significantly higher on weekdays than on weekends, higher in evening than morning and rainfall decreases the rental count.

### Data Preprocessing
Feature engineering was performed to remove redundant features, to create new features and modify existing features that would improve the predictive performance of the model. The new features included dummy variables, which represented categorical variables such as season and weather conditions. Power transformation was applied on rainfall and snowfall to make it more normal. Then the features were separated into dependent and independent variables to make easier for model implementation. Finally the data was scaled for linear regression.

### Implementing ML Algorithms
Four different regression models were trained and evaluated on the dataset, namely Linear Regression, Decision Tree, Random Forest and XGBoost. The evaluation metrics used were Mean Absolute Error (MAE), Mean Squared Error (MSE), Root Mean Squared Error (RMSE), R-squared and Adjusted R-squared score. The results showed that XGBoost outperformed the other 3 models, achieving the lowest MAE, MSE, and RMSE and highest R-squared and Adjusted R-squared score.

The hyperparameters of each model were also tuned using grid search to identify the optimal hyperparameters. The XGBoost model was also tuned using grid search on hyperparameters of maximum depth, and number of estimators. The results showed that the XGBoost model achieved an Adjusted R-squared value of 0.9067, indicating that the model can explain 90.67% of the variance in the target variable. After using grid search to identify the optimal hyperparameters on XGBoost, the model's performance improved by a very small margin. However, the tuning process was found to be time-consuming and computationally expensive. So its upto the user to use the regular XGBoost or tuned XGBoost as both have almost similar performance.

### ShAP explainers
To gain insights into the factors that influenced bike rentals, feature importance analysis was conducted using the SHapley Additive exPlanations (SHAP) method. The analysis revealed that temperature was the most important feature in predicting bike rentals, followed by humidity, Solar Radiation, and whether the hour was a 6PM or not. The SHAP values for temperature showed a positive correlation, indicating that as the temperature increases, the number of bike rentals also increases.

## Conclusion
1.	Xgboost model performs the best regression on the data explaining more than 90% of the variation in the data, followed by Random Forest which explains around 88% of the variations in the data. Decision Tree and Gradient Boosting performed descently explaining around 82% variation in the data. Linear Regression along with all regularization techniques failed to perform well.
2.	Most of the algorihtms consider Temperature as the most important feature according to their feature importance plot. However, the best performing algorithm (XGBoost) considers the evening hour variables as the most important feature. Further XGBoost is the only algorithm which has given such a less (15%) importance to its most important feature whereas other algorithms have more than 35% importance to its most important features. Another thing to note is that XGBoost's feature importance plot is fairly distributed meaning the lowest important features have also been given importance.
3.	From EDA we conclude that, people rent bikes mostly on working days, mainly during the office hours of morning and evening hours as it touches peak in around 6 PM. People avoided using bikes in winter and summer had most bikes rented with peak in the month of June.

Finally, we can conclude that in predicting the rental bike count, its important to focus on the time of booking and the weather condition. Most of the bookings done during the office hours, particulary evenings, that too on weekdays. However, if the weather is chilly or rainy or snowy, bookings will be low and so less bookings in winter season during the months of December, January and February.

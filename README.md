# Seoul_Bike_Sharing_Demand_Prediction
-----------------------------------------------------------------------------------------------------------------------------------------

# <u>Problem Statement<u>
The goal is to have rental bikes ready for people whenever they need them, so they don't have to wait. But a big challenge is figuring out how many bikes should be available at different times of the day.
To do this, we need to predict how many bikes will be needed each hour. This way, we can make sure there are enough bikes for everyone. This prediction is really important for keeping a steady supply of rental bikes in the city. So, the main job is to guess how many bikes people will want at different times of the day to make sure there are always enough for everyone.

# <u>Dataset<u>
 The dataset contains weather information (Temperature, Humidity, Windspeed, Visibility, Dewpoint, Solar radiation, 
 Snowfall, Rainfall, the number of bikes rented per hour and date information.
 
 Attribute Information:
 
 Date : year-month-day
 
 Rented Bike count - Count of bikes rented at each hour.
 
 Hour - Hour of the day
 
 Temperature-Temperature in Celsius
 
 Humidity - %
 
 Windspeed - m/s
 
 Visibility - 10m
 
 Dew point temperature - Celsius
 
 Solar radiation - MJ/m2
 
 Rainfall - mm
 
 Snowfall - cm
 
 Seasons - Winter, Spring, Summer, Autumn
 
 Holiday - Holiday/No holiday
 
 Functional Day - NoFunc(Non Functional Hours), Fun(Functional hours)
 
 The dataset contains weather information (Temperature, Humidity, Windspeed, Visibility, Dewpoint, Solar radiation, 
 Snowfall, Rainfall, the number of bikes rented per hour and date information.
 
 # <u>Data Cleaning and Data Preprocessing<u>
  [1] Handling Duplicate Values
 - Dataset having 0 duplicated values.
 [2] Handling Null / Missing Values
 - Dataset having 0 null values.
 [3] Removing Outliers
 - Interquartile Range in the skew symmetric curve used to remove outliers found in the Rented Bike Count, Wind speed (m/s) and Solar Radiation (MJ/m2) variables.
 [3] Data Wrangling and Feature Engineering
 - The variables day, month, and year were created from the variable Date, and the original variables deleted.
 - Datatype of the variable Date was transformed from object datatype to datetime64.
 - From above, variables 'year','Dew point temperature(°C)', and 'Humidity(%)' have a high variance inflation factor, so we can remove them to reduce VIF
[4] Features encoding
 - Label encoding used to encoding variables Seasons, Holiday, and Functional Day.
[5] Data Scaling
 - MinMaxScaler preserves the shape of the original distribution. It doesn't meaningfully change the information embedded in the original data. So we used MinMaxScaler for scaling the dataset.

# <u>Exploratory Data Analysis<u>
 These following graphs and plots were primarily created using Matplotlib and the Seaborn package.
 - Bar plot
 - Line plot
 - Box plot
 - Heatmap

 Performed EDA and reached the following conclusions:
* People like renting bikes all year round, regardless of the season.

* Bikes are popular during working hours and less used at night.

* Biking is more common during office commute times.

* Evening hours are when most people use rented bikes.

* Humidity between 10% and 18% is preferred for bike rentals.

* People consistently rent bikes when the wind speed is around 3.2 m/s.

* Dew point temperatures of 12°C to 18°C are ideal for bike rentals.

* Solar radiation doesn't significantly impact bike rentals.

* Biking is preferred when it's not raining or snowing heavily.

* Early and late in the month are popular times for bike rentals.

* Summer and autumn are the peak seasons for bike rentals.

* Visibility doesn't affect bike rentals much, except when it's very high.

* More bikes are rented on non-holiday days.
Bikes are used the most during their operational hours.

* Bike rentals tripled from 2017 to 2018.
  
# <u>Model Building<u> 
 We implemented the following machine learning models:
 - Linear Regression
 - Polynimial Regression
 - Lasso (L1) Regression
 - Ridge (L2) Regression 
 - KNN
 - Decision Tree 
 - Random Forest
 - XGBoost
   
# <u>Models Evaluation<u>
 - We used the R-squared score, Root Mean Squared Error, and the Mean of Residuals for the evaluation of each model.
   
# <u>Model Explainability<u>
 - A higher feature importance score for features : Functioning Days, Rainfall (mm), and Seasons, respectively, indicates that those specific features have a larger influence on the model used to forecast a certain variable, respectively.
 - High values from the Hour, Temperature (°C), Solar Radiation (MJ/m2), and Functioning Day features have a positive impact on the model, while low values have a negative impact.
 - High values of the variables for Wind speed (m/s), Holidays, Snowfall (cm), Visibility (10m), Seasons, and Rainfall (mm) have a negative impact on the model, while low values have a positive impact.
 
# <u>Conclusion<u>
 - The XGBoost regression model has the highest R-squared score, the lowest Root Mean Squared Error (RMSE), and has very close to having zero mean of residuals. Achieved high R-squared score of 0.91% using XGBoost.
 - As a result of the model's high accuracy, low error, and zero mean of residuals, the XGBoost regression model is the ideal and well-trained model for forecasting the number of rented bikes required per hour.

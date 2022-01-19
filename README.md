## Weather_Forecast_Kaggle_Dataset

Blog post: -https://medium.com/@joshi.abhay.m/weather-forecast-using-machine-learning-model-69db2fb0ae29
## Table of contents
* [General info](#general-info)
* [Technologies](#technologies)
* [Setup](#setup)
* [Dataset](#dataset)
* [Results](#ModelResult)
## General info
The Rain in Australia dataset contains 10 years of weather data that is recorded daily from different weather stations. The same of the data set
![](https://i.imgur.com/5QNJvir.png)
>
> As a data scientist at the Bureau of Meteorology, we are tasked with creating a fully-automated system that can  weather data for a given location to predict whether it will rain at the location tomorrow. 
>
>
> ![](https://i.imgur.com/KWfcpcO.png)
> Identify the features that can predict the weather forecast,
> Plot the charts to find the relationship between independent variables
	
## Technologies
Project is created with:
* Juypiter notebook	
## Setup
To run this project, install it locally using conda install:

```
pip install matlplotlib
pip install sklearn
pip install seaborn
pip install pandas numpy
```
## Dataset
https://www.kaggle.com/jsphyg/weather-dataset-rattle-package?select=weatherAUS.csv

weatherAus.csv: File contains set of records which will help us understand how rain records are affected with features created. This data contains numeric and categorical information. Based on the approach we need to clean the data or transformt the features.

Number of columns: 23
Number of rows: 145460
Number of Independent Columns: 22
Number of Dependent Column: 1

PLease see below the list of features and its definition

Date	-The date of observation\
Location	-The common name of the location of the weather station\
MinTemp	-The minimum temperature in degrees celsius\
MaxTemp	-The maximum temperature in degrees celsius\
Rainfall	-The amount of rainfall recorded for the day in mm\
Evaporation	-The so-called Class A pan evaporation (mm) in the 24 hours to 9am\
Sunshine	-The number of hours of bright sunshine in the day.\
WindGustDir	-The direction of the strongest wind gust in the 24 hours to midnight\
WindGustSpeed	-The speed (km/h) of the strongest wind gust in the 24 hours to midnight\
WindDir9am	-Direction of the wind at 9am\
WindDir3pm	-Direction of the wind at 3pm\
WindSpeed9am	-Wind speed (km/hr) averaged over 10 minutes prior to 9am\
WindSpeed3pm	-Wind speed (km/hr) averaged over 10 minutes prior to 3pm\
Humidity9am	-Humidity (percent) at 9am\
Humidity3pm	-Humidity (percent) at 3pm\
Pressure9am	-Atmospheric pressure (hpa) reduced to mean sea level at 9am\
Pressure3pm	-Atmospheric pressure (hpa) reduced to mean sea level at 3pm\
Cloud9am	-Fraction of sky obscured by cloud at 9am. This is measured in "oktas", which are a unit of eigths. It records how many eigths of the sky are obscured by cloud. A 0 measure indicates completely clear sky whilst an 8 indicates that it is completely overcast.\
Cloud3pm	-Fraction of sky obscured by cloud (in "oktas": eighths) at 3pm. See Cload9am for a description of the values\
Temp9am	Temperature (degrees C) at 9am\
Temp3pm	Temperature (degrees C) at 3pm\
RainToday	-Boolean: 1 if precipitation (mm) in the 24 hours to 9am exceeds 1mm, otherwise 0\
RainTomorrow	-The amount of next day rain in mm. Used to create response variable RainTomorrow. A kind of measure of the "risk".\

## Result

# Business Problem

**Identify the features that can contribute to predict rain tomorrow** 

 Plotting the Location vs Rainy days to understand the distribution
 ![image](https://user-images.githubusercontent.com/15306750/150061100-5d3ef1ff-9d8e-404b-9f9d-ff97ef8aed2d.png)

 Location can be the factor for the correlation with rain today feature ( one of the solution to business question)
 
 Temperature at 3PM versus Rain Tomorrow
 ![image](https://user-images.githubusercontent.com/15306750/150061186-83aef8da-5a3f-48ca-a0d3-af3a840c16b5.png)

 One quick observation we can carry from the chart is lower temperature will forecast rain for tomorrow as per the historical data
 
 Temp 3PM vs Humidity 3PM

 ![image](https://user-images.githubusercontent.com/15306750/150061267-ed726a2c-76b4-48b4-a992-c2b18d417031.png)

 Low temperature and high humidity suggest that it will rain tomorrow and also it will be true for rain today.
 
Prepare the model with best accuracy and reduce overfitting

 **Using logistic regression**
 ![image](https://user-images.githubusercontent.com/15306750/150061592-6576ccf3-e8d1-4bc9-926d-1755edff335b.png)
 
 We have calculated the accuracy score on Training and Test set 
 
 Training accuracy : 85.15%
 
 ![image](https://user-images.githubusercontent.com/15306750/150061644-7178469e-3102-4c75-ba2f-99ad903520d4.png)

 Validation accuracy : 85.41%
 
 ![image](https://user-images.githubusercontent.com/15306750/150061702-1c2f6ad9-b82c-4367-855d-b06abc620d90.png)
 
 Logistic regression identifies the best fit using all the features, we can try to fine tune the model by using ovarious standardization techniques .

 **Important Features calculated from the model**
 
 {'MinTemp': 0.98302,
 'MaxTemp': -1.61356,
 'Rainfall': 3.25713,
 'Evaporation': 0.7388}



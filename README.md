# NOAA-Weather-Data-Analysis-and-Prediction
This project is part of the IBM Data Science course. Which is focuses on analyzing and forecasting weather patterns using the NOAA Weather Dataset collected from JFK Airport in New York. This notebook teaches the user to extract, clean and analyze sample weather data and predict weather trends to help airports schedule better flight times.
This project involves the basic concept of Data Analysis and working with Time series analysis for Temperature prediction
# 01 ETL (Extract Transfrm and Load)
Dataset was extracted from the weather station of New York, using this below link: https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/fJKLoMKtgpDAl5MkA6rf2A/jfk-weather.csv 
After extacting the dataset, multiple techniques are applied to transform and clean the dataset and then it is ready for the Load for further analysis. The pre-processed CSV file is also attached in the repo.
# 02 Exploratory Data Analysis
we visualize a few sections of the data, using matplotlib's pyplot module.
<img width="1777" height="725" alt="image" src="https://github.com/user-attachments/assets/61a844ac-bb0d-4782-b981-e9a849988fe9" />
Feature Dependencies are also explored using correlation matrix 
<img width="829" height="729" alt="image" src="https://github.com/user-attachments/assets/c27d3d19-e185-4719-96d3-cf999df1a70f" />
As we are interested to forecast the temperature therefore the Monthly(All dataset) and Daily Temperature (only for 2017) was ploted. 
<img width="1533" height="703" alt="image" src="https://github.com/user-attachments/assets/085db2d7-fbf3-4021-b15e-511b7f68f251" />
Finally we apply some smoothing to the data in the form of a rolling/moving average. This is the simplest form of de-noising the data.
<img width="2384" height="1103" alt="image" src="https://github.com/user-attachments/assets/1c3e0249-86c8-4735-a740-94eb23199536" />
# 03 Time Series Forecasting
We have split the dataset as 80% of the data for the training set and 10% each for validation and test sets.we have create a few simple predictive models of temperature, using shifting and rolling averages. These will serve as a baseline against which we can compare more sophisticated models.
<img width="1006" height="752" alt="image" src="https://github.com/user-attachments/assets/8d5d4b0e-c3aa-45e2-b0ef-c611dd9fda5c" />
Evaluating the baseline model using RMSE:
Baseline t-1 RMSE:            1.370
Baseline t-2 RMSE:            2.130
Baseline 6hr rollavg RMSE:    2.940
Baseline 12hr rollavg RMSE:   4.620
## Train Statistical Time-series Analysis Models
we will explore one called SARIMAX - the Seasonal AutoRegressive Integrated Moving Average with eXogenous regressors model.
<img width="629" height="470" alt="image" src="https://github.com/user-attachments/assets/a84eb0a9-3112-4ea8-a1ac-48431c38795d" />
AR(1) RMSE:                   1.371
Baseline t-1 RMSE:            1.370
Then, we move to more complex model and achinve the following accuracy:
AR(2) RMSE:                   1.341
AR(1) RMSE:                   1.371
Baseline t-1 RMSE:            1.370
Then, we Incorporated moving averages
<img width="630" height="470" alt="image" src="https://github.com/user-attachments/assets/4689af02-a061-41e7-b3b5-37a1f8ccbd5a" />
AR(2) MA(1) RMSE:             1.313
AR(2) RMSE:                   1.341
AR(1) RMSE:                   1.371
Baseline t-1 RMSE:            1.370









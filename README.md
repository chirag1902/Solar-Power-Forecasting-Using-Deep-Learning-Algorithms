# Solar-Power-Forecasting-Using-Deep-Learning-Algorithms

## Abstract

Solar energy is an enticing alternative to traditional forms of energy since it is both a renewable and clean energy source. Conventional forms of energy are known to contribute to the emission of greenhouse gases and environmental degradation. Forecasting the solar power output for a specific period is necessary to anticipate future events. This Project illustrates how forecasting and statistics on solar power can be utilized to predict the amount of solar power produced in the future. It investigates various methods of forecasting as well as the application of deep learning algorithms to predict the generation of solar energy. Data on solar power was collected over one year, while statistics on temperature and humidity were gathered from publicly accessible websites through web scraping. Two datasets were created for the features, namely irradiance, temperature and humidity, based on hourly and daily data. In the later stages, statistical and deep learning methods like ARIMA, LSTM, Bi-LSTM and RNN were employed for forecasting the solar power output, then performed model evaluation based on performance metrics. In, the study it was found that ARIMA performed the best for forecasting power output of the system with an RMSE of 6.04


## Implementation

### Dataset Collection:
A total of 365 data records of both temperature and humidity were scraped from the website "Weather Underground" [11] and for the study average values of both temperature and humidity were considered. In order to construct hourly observation-based dataset a total of 8736 records of both temperature and humidity were scraped from the same website. During scraping, redundant values were removed and in case of multiple values of same record an average was taken in account.
### Data Preprocessing:
Data files for power and irradiance were cleaned using python library os and some of the files were also manually cleaned in case of presence of miscellaneous or improper format.
During scaling, data is re-scaled to fall within a predetermined range of values. Data scaling is a crucial step for developing the forecasting system because of the wildly disparate ranges and units of the data set. To transform numerical features between a spectrum of 0 and 1, this project employs min-max scaling. Python's Sci-kit library's MinMaxScaler class was utilized to carry out this function. After these null values in the dataset were imputed using the feature mean.
### Feature Engineering:
Data was reshaped using reshaped in order to fit to the model using pandas library and train and test split of the dataset were created using both pandas and tensorflow inbuilt libraries. A custom function was implemented in order to produce lag in the data with the aid of pandas library. Statsmodel built in function adfuller was also used to perform Agumented Dickey-Fuller test to check for stationary feature before implementing ARIMA and it was concluded that all the features were stationary.
### Data Visualization:
Data Visualization: To construct visualizations like time series plots, scatter plots, and box plots, Python libraries like Matplotlib and Seaborn are utilised. It was done to analyse the trend of the feature along with sesonality and noise. Visualisation is necessary for time series forecasting as it depicts how and when the data is changing and can indicate various usefult patterns.
![Plot of daily](https://github.com/chirag1902/Solar-Power-Forecasting-Using-Deep-Learning-Algorithms/assets/71887495/3384247a-5cd8-49f5-b05f-e54a4b308bc3)

![Plot of daily 1](https://github.com/chirag1902/Solar-Power-Forecasting-Using-Deep-Learning-Algorithms/assets/71887495/644333be-c64a-4027-8df6-3620140b8c5f)
![Plot of hourly](https://github.com/chirag1902/Solar-Power-Forecasting-Using-Deep-Learning-Algorithms/assets/71887495/c73182ac-1b37-4c59-8260-5b863f2aca65)

From Fig. 2 & 3 it can be inferred that both daily temperature and daily humidity have a little similarity with daily power output pattern whereas it was observed from Fig. 4 & 5 that daily irradiance and daily power show high similarity. Fig. 6 displays the trend analysis of daily power output and it can been that there is a periodic drop in the power out and the daily power output shows strong seasonality which is shown in Fig. 7.
From Fig. 8 & 9 it can be inferred that both hourly temperature and hourly humidity doesn't have much similarity either with themselves or with hourly power output whereas it was observed from Fig. 10 & 11 that hourly irradiance and hourly power show high similarity. Fig. 6 displays the trend analysis of hourly power output and it can been that there is a drop in the power out towards the end of the year

## Result
![Performance](https://github.com/chirag1902/Solar-Power-Forecasting-Using-Deep-Learning-Algorithms/assets/71887495/dddbbb14-1ec5-4f6c-86fb-940b664aad30)

The experimental results of the performance metrics of the different models used in the proposed method are shown in Table 1 and Table 2. We have used Scikit-learn for model evaluation.The results of the experiment showed that for hourly prediction Simple RNN was performing quite well with an R2 score of 0.73, whereas for hourly predictions the results show that the LSTM model is performing the best in predicting the solar power output of the system as it has an R-Squared value of 0.84 and has the lowest RMSE and MSE of 0.84 and 0.09 respectively which explains that the model fits the data well.

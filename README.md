# GBP-USD-Historical-Exchange-Rate-Regression-Analysis
GBP/USD Historical Exchange Rate Regression Analysis 


 # Project Summary: GBP/USD Historical Exchange Rate – Exploratory Data Analysis & Linear Regression
This project focuses on the exploratory analysis and regression modeling of historical GBP/USD foreign exchange (forex) data. Using Python libraries such as pandas, matplotlib, seaborn, and scikit-learn, the project explores historical trends and builds a predictive linear regression model on the daily low prices.

# Exploratory Data Analysis (EDA)
The dataset includes 440 daily observations with the following features:

Date: Date of entry

Open, High, Low, Close: Exchange rate values for the day

Change(Pips): Movement in pips (percentage in points)

Change(%): Daily percentage change

Key EDA steps:
Data Cleaning:

The Date column was initially a string with a timestamp (00:00) attached. This was stripped to retain only the date.

The column was converted to datetime and later mapped to ordinal values for regression modeling.

Time Series Plots:

Line plots of Low and High prices over time were created to visualize market volatility and trend directions.

A comparison plot of Low vs High gave insight into daily spread ranges.

An additional plot of the mean of High and Low prices showed a smoothed average over time, highlighting general market drift and volatility cycles.

Descriptive Statistics:

Measures such as mean, standard deviation, and min/max values were calculated.

Patterns in Change(Pips) and Change(%) helped identify periods of high volatility.


# Insights & Observations
The exchange rate shows mild non-linearity, which may benefit from polynomial regression or advanced time series models (ARIMA, LSTM).

The Change(Pips) and Change(%) columns indicate occasional price shocks, possibly driven by economic or geopolitical events.

Further feature engineering (e.g., rolling averages, volatility bands, economic indicators) could improve model performance.

Incorporating external factors like interest rate differentials, central bank announcements, or inflation

# Regression Analysis
To model the relationship between date and the daily low price, the following steps were performed:

Data Preparation:
The Date was mapped to ordinal values using datetime.toordinal() for compatibility with regression modeling.

The target variable (y) was set to the Low price column.

Train/Test Split:
The dataset was split into training (70%) and test (30%) sets using train_test_split from scikit-learn.

shuffle=False ensured that the time series nature of the data was preserved (no future data in the training set).

Model Training:
A simple linear regression model was trained using LinearRegression() from sklearn.

The model was fit on the training set (X_train, y_train) and predictions were generated.

Results:
R² score (training set): 0.854, indicating that ~85.4% of the variance in the Low price can be explained by the date alone within the training range.

Model Coefficient: -0.00052, indicating a very gradual decline in the low price over time (interpretable as a weak downward trend).

Intercept: 385.47, an offset that aligns the model to actual exchange rate levels when using ordinal dates.

Visualization:
A scatter plot of training data (Low price vs Date) was overlaid with the regression line, showing good fit and predictive consistency over the training period.

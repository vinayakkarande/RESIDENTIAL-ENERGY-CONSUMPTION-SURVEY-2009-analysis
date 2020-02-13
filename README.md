# RESIDENTIAL-ENERGY-CONSUMPTION-SURVEY-2009-analysis
RECS 2009 data analysis using PCR, NN and PLS

Keys Highlights of analysis and stepwise summary

Data preprocessing
Build Model using Principal component analysis followed by Regression (PCA + LR), Neural network (NN) and Partial Least Square (PLS)
Evaluation and recommend best model to predict Electricity consumption
Data preprocessing

Data is extracted from csv file and column 'KWH' is selected as dependent variable. Log transform dependent variable 'KWH' to get normally distributed Y variable.
Imputation indicators are discarded, and all categorical variables are converted numeric using one hot encoding. Normalize all column data in feature variable.
Build Models using PCR, NN and PLS

PCA + LR - Since we have 754 input features after one hot encoding, we will first reduce dimensionality of input features and consider top principal components. This will allow us to get highly variant group of features and we hope to explain Y variable using them.
NN - NN is default method in such cases as we have huge number of input parameters and we don’t have to worry about feature engineering and get a best fit model just feeding all the input variables to the model
PLS - Since we had very good results for first model, which was reducing dimensionality without considering Y variable, we will now reduce dimensionality considering Y variable.
Evaluation and recommend best model

For all the models, I have considered 10 fold cross validation, this allows me to consider all the available data for prediction. Models are evaluated based on 'mse'.
PLS method performs perfectly well to get mse of 0.064. Hence PLS is the recommended model to predict Electric consumption with R2 of 0.87
Models and MSE

PCA + LR - 0.077
NN - 0.106
PLS - 0.064

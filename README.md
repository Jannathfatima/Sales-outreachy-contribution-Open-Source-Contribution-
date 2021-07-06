# Sales-outreachy
Advance housing price 

The variables are a mix of 43 categorical (nominal and ordinal), continuous(basement, main living area measurements) and discrete types(like number of kitchens, bedrooms, and bathrooms).

Removing Outleirs

Using z-score to filter outliers that are three standard deviations alway from the mean resulted in a huge loss of data.
Hence, based on analysis of the dataset above and the most important features that describes the SalesPrice, I can use scatter plot for the most important features to understand the outliers and then just remove them.


Performed feature engineering
Feature Selection
I have choosen 43 predictors/variables to predict the Sale Price of a house
It is a combination of 26 categorical and 17 numerical variables.
Reducing number of features from 80 to 43 could reduce the chances of overfitting without loss of important information
Feature selection includes:

Selecting features that are highly correlated to SalePrice like OverallQual, neighbourhood, livingArea etc -> determined by using spearman correlation, mutual information scores, visual analysis of scatter and box plots
Removal of collinear variables that negatively affects model performance and decrease generalization performance on the test set
Dropping columns that have more than 95% missing values and those that have no influence on the SalePrice
Three newly engineered features - Total Bathrooms in basement and above grade, house age.
I believe that the Ridge Regression model fits the data well.

The Stacked Ensemble, Gradient Boost Regressor model overfits the data as indicated by low RMSE in training dataset but, high RMSE in test set.

I have used simple models which generalizes well in most cases while can perform poorer in some extreme cases.
Using Regularization(Ridge), dropping certain non-linear features, log transformation of skewed features and removal of outliers has reduced overfitting of data in Ridge Regression model.

The RMSE of predicted SalePrice of the Ridge Regression model is ~19k which I believe is considerable given that median SalePrice is $164k, hence I believe the model fits well.
It has a R² score of 0.92 which indicates that the model can explain 92% of the variation in the dataset and a cross validated score of 0.91, which is good at predicting the house price.

Hence, I would use the Ridge Regression model to predict the salePrice of any new house.

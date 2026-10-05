#PROJECT OVERVIEW

A linear regression model, built with scikit-learn, that predicts the median house value of a California district.

This project uses the California housing dataset to predict median_house_value from features like median income, house age, number of rooms, population, and location. It covers a standard machine learning workflow: cleaning the data, splitting it into training and test sets, scaling features, training a model, and evaluating it with several metrics.

#Dataset
The data is in california_housing.csv. Each row describes one district in California.

Target: median_house_value
Features used: longitude, latitude, housing_median_age, total_rooms, total_bedrooms, population, households, median_income
Not used: ocean_proximity (a text column, dropped for now; see Future Improvements)

#How It Works
1. Load and clean: Read the CSV and drop rows with missing (NaN) values.
2. Split: Divide the data into 80% training and 20% test sets.
3. Scale: Standardize the features with StandardScaler. The scaler is fitted on the training set only, then applied to the test set, so no information leaks from the test data.
4. Train: Fit a LinearRegression model on the scaled training data.
5. Evaluate: Predict on the test set and measure performance.
6. Interpret: Print each feature's coefficient to see which features influence the price most. Because the features are standardized, the coefficients can be compared with each other.

#Limitations
1. Rows with missing values were removed rather than filled in.
2. Ocean_proximity column was dropped instead of 'one-hot encoding'(turning categories like inland, near bay, etc. into values between 0 and 1.)
3. Linear regression assumes a straight-line relationship between features and price. Real housing prices, especially with respect to location, are more complicated.

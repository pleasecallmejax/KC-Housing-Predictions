## King County Housing Predictions

This repo contains the materials used to predict house prices in King County, WA. Ultimately, a model was developed with a root mean square error of ~$141,000 for the training data.

This repo contains:

a jupyter notebook detailing EDA and inference process: Bakeoff_Final.ipynb.
a jupyter notebook for feature engineering and model development: Bakeoff_Final.ipynb.
a jupyter notebook to predict on holdout data: Predict_holdout.ipynb.
a folder containing pickled items:Pickle_Jar
a folder containing CSVs:Data
a an inference presentation as PDF in Data folder

Exploratory Data Analysis (EDA): Generated multiple visualizations. Box plots to identify outliers, scatter plots to determine shape of relationship (linear or otherwise), histograms to see distribution shape, and folium to view points at a glance.

Features: Generated dummy variables for zip, and observed sqft and view interactions with most expensive and most populated KC zipcodes. Created median build year and . Performed non_linear transforms where necessary.

Statistical Tests: T_test for independence between houses with bathrooms/bedrooms and those without (P < alpha 0.05). ANOVA testing on significant zipcodes (P = 0). OLS between price and sqft multiplied.

Linear Regression Model: All features: RMSE of $188,967. Test-train split: Test RMSE $.44% smaller than train RMSE - the model is not overfit. Add degree_2 polynomial features for top 50 features by Pearson Corr Coeff - this causes model to overfit. Utilised SelectKBest to reduce features to 80 - achieved test RMSE of ~$141,000 . Assessed largest residuals to iterate back through engineered features and adjust. Additionally increased number of features passed to poly_2 to 70. Eventually achieved test RMSE of ~$141,000.

Holdout predictions

Pickled model and other pertinent data (including SelectKBest columns), engineered matching features for holdout data (kc_house_data_holdout_features.csv), generated 4322 predictions for house prices in King County. Test distribution, mean and median of these prices against train data to avoid glaring errors.

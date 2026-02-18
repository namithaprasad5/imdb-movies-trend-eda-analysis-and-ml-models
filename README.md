# imdb-movies-trend-eda-analysis-and-ml-models
To develop a regression model that accurately predicts IMDb ratings and analyze which movie features most influence audience scores.
📌 Project Overview

This project builds an end-to-end machine learning pipeline to predict IMDb movie ratings using structured movie metadata such as metascore, release year, runtime, vote count, gross revenue, and certificate.

The workflow includes data cleaning, exploratory data analysis (EDA), feature engineering, model comparison, and final prediction generation.
🧹 Data Preprocessing

Handled missing values using median imputation

Created gross_missing indicator for missing box office data

Removed genre column due to 100% missing values

Cleaned numeric columns (votes, gross) by removing commas and converting to numeric

Applied log transformation to skewed features (votes, gross_millions)
📊 Exploratory Data Analysis

Ratings are concentrated between 6 and 8

Metascore shows strong correlation (0.58) with IMDb rating

Popularity features (votes, gross) have weak correlation with rating

Older movies tend to have slightly higher ratings in this dataset

Correlation heatmap guided feature selection
🧠 Feature Engineering

Log features: log_votes, log_gross

One-hot encoding for categorical variable (certificate)

Built a leakage-safe preprocessing pipeline using
ColumnTransformer and Pipeline
🤖 Models Trained

Linear Regression

Random Forest Regressor

XGBoost Regressor

Gradient Boosting Regressor

Tuned XGBoost Regressor

Linear Regression Model Explanation¶
Linear Regression was selected as the final model because the exploratory data analysis showed predominantly linear relationships between the predictors and the target variable. In particular, metascore demonstrated a strong positive linear correlation with IMDb rating, while other features such as year and log-transformed vote counts showed weaker but still linear trends.

Tree-based models such as Random Forest and XGBoost did not outperform Linear Regression, indicating the absence of strong non-linear feature interactions in the dataset. Additionally, the dataset size was relatively small, which further favored a simpler linear model.

Evaluation Metrics
The model achieved:

Mean Absolute Error (MAE): 0.584
R² Score: 0.393
The MAE indicates that, on average, the predicted ratings differ from the actual ratings by approximately 0.58 points, which is acceptable for subjective rating data. The R² score shows that the model explains 39.3% of the variance in IMDb ratings. The remaining variance is likely due to qualitative factors such as storytelling, acting quality, and audience preferences that are not captured in the available features.

Kaggle Notebook

Kaggle project link: [(add your Kaggle link here)](https://www.kaggle.com/code/namithaprasad04/imdb-movies-trend-eda-analysis-and-ml-models)

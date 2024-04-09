# Ad Click Prediction

## Source:
https://www.kaggle.com/datasets/pavansanagapati/ad-displayclick-data-on-taobaocom

## About:

This project focused on the Click-Through Rate (CTR) prediction task in the scenario of display advertising, sampled 1140000 users from the website of Taobao for 8 days of ad display / click logs (26 million records). Through comprehensive insight, data preparation, modeling, and evaluation.

## Result Summary:

Achieved an Area Under the Curve (AUC) score of 0.7 through extensive data preprocessing and feature engineering. Detailed findings are organized into four Jupyter notebooks, each focusing on distinct phases of the project - Insight, Data Preparation, Machine Learning Predictive Modeling, and Evaluation.

Result table :

![image](https://github.com/Shahla9/Ad-click-prediction/assets/114596964/fd9ccd25-dff4-45e0-8c9a-ce65ecb7f64e)



## Steps:

### Insight:

In the initial phase, the "Insight" notebook outlines the steps taken to fetch, clean, profile, and prepare ad record data sourced from taobao's website. Key steps included:

#### Data Fetching and Cleaning:
Removing date outliers and cleaning the dataset to ensure accuracy.
#### Data Profiling:
Analyzing the dataset to understand its characteristics.
#### Click Rate Counts:
Counting click rates of different categories.
#### Feature Extraction:
Creating lag features capturing temporal dependencies in click rate.
#### Null Handling:
Addressing missing values to maintain dataset integrity.

### Data Preparation:

In the "Data Preparation" notebook outlines feature engineering.

### Model:

In the "Model" notebook the aim was to employ two different methods of Random Forest Classifier and XGboost Classifierfocuses on machine learning models, though since it is BigData, Random Forest Classifier could not handle it and xgboost applied on three models based on the folliwing features . The features included are:

FEATURES = [
    'pvalue_level', 'shopping_level', 'price', 'age_level',
    'final_gender_code','user_ad_count', 'user_ad_clk_count',
    'adgroup_count','adgroup_clk_count', 'campaign_count',
    'campaign_clk_count','cate_count', 'cate_clk_count',
    'cat_gender_ad_count','cat_gender_ad_clk_count', 'cat_age_ad_count',
    'cat_age_ad_clk_count','gender_age_ad_count', 'gender_age_ad_clk_count'
]

AD_FEATURES = [
    'price', 'adgroup_count','adgroup_clk_count', 'campaign_count',
    'campaign_clk_count','cate_count', 'cate_clk_count'
]
USER_FEATURES = [
    'pvalue_level', 'shopping_level', 'age_level',
    'final_gender_code','user_ad_count', 'user_ad_clk_count'
]

The label for prediction is set as:

LABEL = ['clk']

For the model's train-test split, data from the first seven days are used for training, while the day is reserved for testing.

#### Machine Learning:

This phase employs XGBoost algorithms to predict click rates. The selection of these models is based on their ability to handle non-linear data and provide insights into the importance of different features affecting taxi demand.


### Evaluation:

The "Evaluation" notebook delves into the performance assessment of the predictive models using Root Mean Square Error (RMSE) and Mean Absolute Percentage Error (MAPE) metrics. A table summarizing the residuals of various methods is presented, demonstrating the superior accuracy of the Random Forest model.



#### The project utilizes a range of libraries to facilitate data manipulation, analysis, and modeling:

##### Geopandas: For geographic data processing.
##### Numpy: For numerical computations.
##### Pandas: For data manipulation and analysis.
##### Math: For mathematical functions.
##### Tabulate: For formatting tables in the output.

This project serves as a comprehensive guide to predicting taxi demand in New York City, showcasing the application of machine learning techniques to real-world transportation data.



# Ad Click Prediction

## Source:
https://www.kaggle.com/datasets/pavansanagapati/ad-displayclick-data-on-taobaocom

## About:

This project focuses on predicting Click-Through Rate (CTR) in display advertising, using data sampled from Taobao's website. The dataset comprises 26 million records over 8 days, representing 1,140,000 users. The project involves comprehensive data analysis, preparation, modeling, and evaluation.

## Result Summary:

The project achieved an Area Under the Curve (AUC) score of 0.7 after extensive data preprocessing and feature engineering. Detailed findings are organized into four Jupyter notebooks, each dedicated to a distinct phase of the project: Insight, Data Preparation, Machine Learning Predictive Modeling, and Evaluation.

Result table :

![image](https://github.com/Shahla9/Ad-click-prediction/assets/114596964/fd9ccd25-dff4-45e0-8c9a-ce65ecb7f64e)



## Steps:

### Insight:

The "Insight" notebook initiates the project by outlining steps to fetch, clean, profile, and prepare ad record data from Taobao's website. Key activities include:

#### Data Fetching and Cleaning:
Removing date outliers and ensuring dataset accuracy.
#### Data Profiling:
Analyzing dataset characteristics.
#### Click Rate Counts:
Calculating click rates for different categories.
#### Feature Extraction:
Creating lag features capturing temporal dependencies in click rate.
#### Null Handling:
Addressing missing values to maintain dataset integrity.

### Data Preparation:

The "Data Preparation" notebook focuses on feature engineering.

### Model:

In the "Model" notebook, Random Forest Classifier was initially considered but due to limitations with handling Big Data, XGBoost Classifier was applied for its speed and performance. XGBoost was trained on three models based on various features including ad-related and user-related attributes.

The features included are:

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

The label for prediction is set as 'clk'. Data from the first seven days were used for training, while the eighth day was reserved for testing.

#### Machine Learning:

XGBoost algorithm was employed due to its speed and efficiency with large datasets.


### Evaluation:
The "Evaluation" notebook assesses model performance using ROC curve and AUC metrics. It demonstrates superior accuracy of Model 3, trained with all features, achieving AUC = 0.7.



#### The project utilizes a range of libraries to facilitate data manipulation, analysis, and modeling:

##### Pyspark: For processing large datasets.
##### Pandas: For data manipulation and analysis.
##### Matplotlib: For visualizations.
##### Scikit-learn: For implementing machine learning models.

This project serves as a comprehensive guide to predicting ad clicks, showcasing the application of machine learning techniques to real-world advertising data.



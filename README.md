# **Food Sales Predictions**
This is a sales prediction for food items sold at various stores. The goal of this is to help the retailer understand the properties of products and outlets that play crucial roles in increasing sales.

**Author**: Belandy Gard

![image](https://user-images.githubusercontent.com/123032319/231050414-8f868f76-fd14-43ff-9e04-d602644acc20.png)


# **Cleaning**
Before machine learning preprocessing, the data was cleaned with the following steps:

- Rows and columns were calculated
- THe data tpe of each variable was checked
- Duplicate rows were dropped
- Spelling inconsistencies were fixed
- Categorical ordinal data was numerically encoded
- High-cardinality feature was dropped ('Item_Identifier')


# **Exploratory Visualization**
To understand the data statistical analyses Exploratory Visualization was completed to explain, or model the data. This was done by each of thed following:

- Histogram to view the distributions of various features in your dataset.
- Boxplot to view statistical summaries of various features in your dataset.
- Heatmap of the correlation between features.

This histogram shows the relationshiop of Item_Outlet_Sales and Outlet location. This can give a better understanding of which outlet produces the best sales.

![image](https://user-images.githubusercontent.com/123032319/230794220-6470ade3-05a6-442f-a220-561dd3580a0e.png)

This heatmap can be used to see which features are highly correlated with eachother.

![image](https://user-images.githubusercontent.com/123032319/230794673-5865c88f-fd36-467f-a64a-293007c5091d.png)


# **Explanatory Visualization**
Explanatory visualizations was used to communicate the results of data analyses. This will convey the results of the data analsis in a clear and concise manner. The goal of explanatory data visualization is to communicate findings and inspire action.

The following Barplot can be used to help determine which product type produces the best Outlet sales

![image](https://user-images.githubusercontent.com/123032319/230795142-0291d32d-952e-47af-9803-80a58da35899.png)


This Barplot can be used to help determine which Outlet Location had the least and most amount of Item sales

![image](https://user-images.githubusercontent.com/123032319/230795979-98237b66-cb5f-45e3-8649-55336458620d.png)



# **Machine Learning**

The data was preprocessed before fitting and testing machine learning models with the following steps:

Missing numerical values were imputed with the mean
Numerical features were scaled
Missing nominal values were imputed with the most frequent value
Nominal features were one-hot encoded

# **Linear Regression Model** 

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
The linear regression model was able to account for about 57% of the variation in the testing data (coefficient of determination / R2). In monetary terms, the model was able to predict the sales amount within a range of +/-804 rupees from the actual sales amount on the testing data (mean absolute error).

![image](https://github.com/BelandyG/Food-Sales-prediction-project/assets/123032319/4470b191-05f5-467d-9980-1423ee994ba7)


The three largest coefficients plotted above are all one-hot encoded categorical features. This means their coefficients can be interpreted as how much the target changes if the observation belongs to that category. For the three categories above (largest to smallest):

If the observation belongs to 'Outlet_Type_Supermarket Type 1', then the target sales will increase by 1006.523 rupees.

If the observation belongs to 'Outlet_Type_Supermarket Type 2', then the target sales will increase by 849.785 rupees.

If the observation belongs to 'Outlet_Identifier_OUT027', then the target sales will increase by 849.785 rupees.

# **Random Forest Regression Model** 

A random forest regression model was fit on the training data and then tested on the reserved testing data.

The random forest regression model was able to account for about 60% of the variation in the testing data (coefficient of determination / R2). In monetary terms, the model was able to predict the sales amount within a range of +/-728 rupees from the actual sales amount on the testing data (mean absolute error).

![image](https://github.com/BelandyG/Food-Sales-prediction-project/assets/123032319/a0036476-d711-4d26-8956-d43a8cc99e55)

For an interpretation, we keep in mind that built-in feature importances are biased toward valuing features with high-cardinality (like 'Item_MRP') over others. We also don't know the relationship of the feature to the target unless we do more EDA or employ additional tools.

With those caveats aside, we can see that the most important feature for our random forest regressor model is 'Item_MRP', with a feature importance of about 0.5. Because feature importances add up to 1, this means that the model heavily relied on 'Item_MRP' to make its decisions to split nodes (about half the time).

Our other top features were 'Outlet_Type_Supermarket Type 1', 'Outlet_Identifier_OUT027', 'Outlet_Type_Supermarket Type 2', and 'Outlet_Establishment_Year'. Three of these four (all save 'Outlet_Establishment_Year') were in the top 3 largest coefficients for our linear regression model.

Here are the SHAP summary plots (bar and dot versions), which show the most important features to the model's prediction and a deeper dive into those features and how the values of those features are driving the model's predictions.

![image](https://github.com/BelandyG/Food-Sales-prediction-project/assets/123032319/43668eb0-eac0-4c6f-b736-36ade391387e)

The SHAP bar summary plot identified the same top five features that the random forest model relied on.

![image](https://github.com/BelandyG/Food-Sales-prediction-project/assets/123032319/a342894a-fd74-46c7-8b1b-7d4d35a9949b)

The top three most important features identified by the SHAP dot plot above are:

'Item_MRP': High prices (identified in red) are driving the SHAP values for rows up, meaning that they are pushing up the total sales number in that row. The reverse is true for low prices (in blue). There looks to be a very orderly spread of high-, mid-, and low-value items directing the final sales.

'Outlet_Type_Supermarket Type1': The rows that belong to this categorical variable (in red) all show up on the positive side, meaning they are driving up final sales numbers. The rows that belong to other values in this category contribute to lower final sales.

'Outlet_Identifier_OUT027': This particular outlet, with rows identified in red, is associated with higher final sales. Other outlets have lower sales.

# **Final Recommendations**

The random forest regression machine learning model is better able to predict sales data than the linear regression model, so going forward the random forest regression model should be used.



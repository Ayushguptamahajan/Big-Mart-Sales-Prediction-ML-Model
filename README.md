# Big-Mart-Sales-Prediction-ML-Model
Machine Learning project for prediction of Sales of Mart

# **The summary of the steps executed in ML model are:**
**1. Data collection and overview of the dataframe:**
- The data was extracted from csv file downloaded from kaggle.
- Data consist of 8523 rows and 12 columns.
- Intuition of the data was gained via calling the first five and last five rows.
- There were 17% data missing in Item_weight and 28% data missing in Outlet_Size.
- Check for duplicated value of Dataframe was done. Luckily there was no duplicated data/row present in Dataframe.
- Info of the Dataframe was reviewed.
- Function to get value_counts corresponding to unique categories was created.
- Item_identifier feature was dropped since it doesnot matter the tag of product with that to sales price.

**2. Feature Engineering:**

Pipeline was created for all the feature engineering works for the dataframe for ease of deployment of model.Step of same is as follow:
- **Step1 Missing Value Imputation**: The missing value in the item_weight was imputed with the mean of the item_weight feature and the missing value of Outlet_size was imputed with the mode of the Outlet_size feature. 
- **Step2 Encoding of categorical columns**: Columntransformer object was created for Onehotencoding of Item_Fat_Content, Outlet_size and Outlet_Location_Type. Another Columntransformer object was created for Ordinal encoding of Outlet_Type, Item_type and Outlet_Identifier.   
- **Step3 Scaling**: Scaling of all the columns after encoding was done in order to get efficient end result of the final model.


**Feature Construction:** 
- Item fat count column was having naming issue (same kind of product was having different name- Rectification of categories was done)
- Since the QQ plot of the target column Item_sale_price was right skewed. Function transformer with log1p fuction was performed for target column Item_sale_price. The same led to transformation of Item_sale_price to normall distribution as depicted in QQ plot.  

**5. Model Building:**

- Train test split was performed with test_size as 20% and random state of 0.2.
- Further **eleven** model was fitted for the splitted data set and various accuracy_score/prescission score was fetched. 

**Name of model used are below:**
- Linear Regression
- SGDRegressor
- XGBRegressor
- RandomForestRegressor
- GradientBoostingRegressor

Hyperparameter Tunning was performed through gridsearchcv of all the above mentioned model to get the best hyperparameter tunned Machine Learning program. 

**6. Conclusion:**

- **GradientBoostingRegressor algorithm** outstanded the performance of model with **r2_score of ~73%**

**Note: The dataframe available maximun achieved score in kaggle was 61-62%. Since the r2_score of mine model comes out to be 73%,so i finalised the model for any kind of further prediction of Sales price.**

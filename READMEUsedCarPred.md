ReadMe for Used Car Prediction

 BUSINESS UNDERSTANDING  
What Drives the Price of a Car? 
An application to predict the price of used cars would not only be convenient to use but would also provide confidence in the valuation of these assets. It is also possible to regularly update the model with the latest data to ensure its continuing relevance. 

The features mostly affecting used car prices will be identified using a subset of a dataset from Kaggle. The original dataset contained information on 3 million used cars.  Once the factors that make a car more or less expensive are identified, a predictive model will be constructed to validate these factors.    

At the same time, the weights of these features in the prediction shall be determined. The output of this exercise will be offered for application to a used car dealer.

DATA UNDERSTANDING
Size of dataset 
There are 18 columns or features and 426,880 rows.

Missing Values 
There is quite a lot of missing values (1,215,152 total).      
After some analysis, the missing values will be replaced with the column mode as is suitable for categorical values.

Dropped Columns
Some of the features which will likely not affect the price of the used cars will be dropped as follows:
1. 'id' and 'VIN' - identification only
2. 'region' and 'state' - the analysis will be national in order to simplify the analysis
3. 'fuel' - only vehicles running on gasoline (84% of data) were considered, for simplicity
4. 'title_status' - on vehicles with clean titles (96% of data) were considered, for simplicity
5. 'size' - percentage of missing values (72%) was over the threshold of 60%

Duplicate Rows          
102,476 duplicate rows will be removed.

DATA PREPARATION 
Columns were dropped where they have no bearing on the price of the used vehicle. Some were dropped for simplicity of the analysis.  

Duplicate rows were removed. Missing values were imputed. A column with a high percentage of missing values was dropped. Outliers were removed from the features especially from the price, odometer and year data.


MODELING   
After data cleaning, imputation of missing values, removal of outliers and others, 32,164 rows remained.  Feature predictors were selected using SequentialFeatureSelector which identified 9 features to select out of 69 original features.    

The optimal complexity was determined using PolynomialFeatures to be degree 3. Three models were built using Linear Regression, Ridge and Lasso for comparison of accuracy. The respective optimal Ridge and Lasso alpha values were obtained.

EVALUATION   
Among the three models, the Linear Regression Model provided the lowest mean squared error both on the train and test sets. The coefficients of this model were extracted and a full model equation was built using these coefficients.

DEPLOYMENT
The full model equation would be placed inside a production application like, for example, a web app, API (Application Programming Interface), mobile app and Excel. 

The model was trained on a log transformed 'price', therefore, a transformation would be required to get predictions back on the original scale.
<img width="468" height="645" alt="image" src="https://github.com/user-attachments/assets/88102c3e-d10e-4738-9fd0-15af5882a955" />
